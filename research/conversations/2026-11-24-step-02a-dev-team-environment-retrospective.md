Written for: the Moderator, as a read-only retrospective on the Development Team's STEP-02A execution environment.

I changed nothing in the repository and ran no install. I did not run `npm ci`, `npm install` or any build or test. I ran `node -v`, `npm -v`, `git` read commands and file reads. My scratch scripts and extracts are in the scratchpad only.

I have no memory of the earlier sessions. This report is reconstructed from six Development Team session transcripts, the surviving logs and task outputs, git history, the lockfile at three commits, and my own `step-02a-evidence.md` and `step-02a-plan.md`.

- **Time zones:** transcript timestamps are UTC, and git commit times are MST (−0700).
- **Sessions covered:** the main implementation session `585baf59`, and the correction sessions `794a4053`, `48612fae`, `84396d71`, `2627eb51` and `0d657fd1`.

## Summary

1. The toolchain was wrong for part of the work. The initial implementation and the entire first gate pass ran on Node v24.13.0 / npm 11.6.2, below Angular's `^24.15.0` requirement. Those results were superseded by a pinned-toolchain rerun.
2. `npm ci` on this machine took 4 to 17 minutes, with more than eight long runs. I found no true hang. Every command eventually returned.
3. There were three confirmed environment or platform interactions:
   - VS Code and orphaned test processes locked the Nx native module.
   - Docker Desktop was stopped at session start.
   - The Windows `.cmd` launcher problem behind `db:snapshot`.
4. The 4th review's lockfile finding is a real dependency defect. It was not purely environmental, but I could not reproduce the reviewer's failure, and my own logs showed the peer warning that I never surfaced.
5. The substantive Tech Lead findings (publication gate, activation revision, HTTPS handling, test-matrix completeness) show no environmental involvement.
6. I found no YAML peer conflict in anything I recorded. The lockfile has one structurally, and it predates STEP-02A.

## 1. Toolchain versions

**Confirmed**

| Where | Evidence | Node / npm |
|---|---|---|
| STEP-01 session | Env dump in `4b52ec83` | v24.13.0 / 11.6.2 |
| Start of 02A (11:27Z Nov 23) | `node -v; npm -v` in `585baf59` | v24.13.0 / 11.6.2 |
| First gate pass, 13:18–14:31Z | 10 gate commands; none had a pinned PATH | v24.13.0 / 11.6.2 |
| From 14:52Z | Portable Node v24.22.1 zip (SHA-256 checked) plus `npm i -g npm@11.21.3` into it; per-command PATH | v24.22.1 / 11.21.3 |
| 794a4053 | fnm Node 24.22.1 plus npm 11.21.3 in a scratch prefix | v24.22.1 / 11.21.3 |
| 84396d71 | Shell reverted to default: `npm ci` at 06:38Z ran on 24.13.0 / 11.6.2. Later `npm ci` and gates used Node 24.22.1 with npm 11.19.1. | mixed |
| 0d657fd1 | Node 24.22.1 with a PATH shim calling npm 11.21.3's CLI | v24.22.1 / 11.21.3 |

- **Pin timeline:** `packageManager: npm@11.21.3` was in the repo from STEP-01 (a5d5787), but `.node-version` was v24.13.0 and there were no `engines`. I added `engines` and bumped `.node-version` to v24.22.1 at 14:54Z Nov 23. It landed in commit 7e552f6.
- **The pin pair is not a stock install:** stock Node v24.22.x bundles npm 11.19.1. In `0d657fd1`, `fnm exec` showed npm 11.21.3 only with Node 26.13.1. Matching the pins requires a manual npm upgrade.
- **Gates in 84396d71:** `format:check`, `lint`, `test` and `build` there ran under npm 11.19.1, not the pinned 11.21.3. This has no lockfile effect, but it deviates from the pin.

## 2. Anomalies encountered

**Confirmed**

| Anomaly | Evidence |
|---|---|
| Slow installs (see table below) | Transcript durations and `npm` summary lines |
| Commands moved to background by the harness timeout | 11:32Z (303s), 14:54Z (61s), 14:57Z (591s), 16:42Z (592s), 22:09Z (601s) |
| `EPERM` unlinking `nx.win32-x64-msvc.node` | 14:56Z Nov 23: two VS Code `Code.exe` processes had the module loaded. 06:31Z and 06:32Z Nov 24: a leftover `run-with-postgres` / nx / vitest chain from my prior session also held it. |
| Partially destroyed `node_modules` after the failed `npm ci` | 47 top-level entries and 0 `.bin` files were left (84396d71); my own caveat says the same |
| Docker Desktop stopped | 11:27Z: "cannot find the file specified" on the Docker pipe; later started locally |
| `PreToolUse hook did not respond ... host client may be unreachable` | 3 failed Reads in `794a4053` (03:22:25, 03:22:26 and 03:32:29Z) |
| Load-sensitive test timeouts | Vitest `Timeout waiting for worker`; `server-persistence` `beforeEach` 5 s; Firefox axe 30 s Playwright timeout |
| `db:snapshot` silent exit 1 on Windows | See section 3 |

`npm ci` durations:

| Time | Toolchain | Duration |
|---|---|---|
| 13:34Z Nov 23 | 24.13.0 / 11.6.2 | 4m31s |
| 14:57Z | 24.22.1 / 11.21.3 | about 17 min (backgrounded at 591s, finished by 15:15Z) |
| 22:09Z | pinned | "16m" in the log |
| Nov 24, `48612fae` | pinned | 8m and 11m |
| 06:38Z, `84396d71` | 24.13.0 / 11.6.2 | 4m |
| 06:42Z | 24.22.1 / 11.19.1 | 533s |
| 06:51Z | via `npx npm@11.21.3` | 565s |

Other long-running steps:
- `npm view` took over 120 s and was backgrounded at 03:07Z in `794a4053`.
- A single `npm install --prefix . npm@11.21.3` took 51 s.
- Nx lint, test, `test:db`, e2e and affected runs took 2 to 7 minutes each.

**Plausible hypotheses (untested)**
- The 4× spread in install time may come from Windows file scanning or concurrent load, such as other Codex and VS Code node processes. The fastest runs were on npm 11.6.2, but that is confounded.
- Idle gaps (15:57→16:37Z, 19:40→20:56Z, 22:09→00:42Z) are probably waiting on the Moderator or the Tech Lead.

**Cannot be reconstructed**
- Why `794a4053` ended at 04:39Z, mid-task and with a background `npm ci` still running. Its correction items were redone in `48612fae`.
- Whether any Codex-style stall occurred on my side. I found none.

Three `Monitor` calls failed with `InputValidationError` because I omitted a required parameter. That was my error, not the environment.

## 3. Failures: environment versus implementation

| Review finding | Classification | Basis |
|---|---|---|
| R1 #5: runner masks Docker errors with a `TypeError` | Implementation defect, triggered by an environment condition | Docker access was denied in the reviewer's environment. The runner code was mine. Fixed and tested. |
| R1 #6: Node outside engine range | Environment, plus a repo pin that predated 02A | `.node-version` was v24.13.0 from STEP-01. The Tech Lead saw `EBADENGINE`. My `tail` and `grep` filters hid it from my own view. |
| R1 #7 and R2 #3: blocking commands not reproducible | Environment | `EPERM` lock, and a reviewer host on 24.13.0 / 11.6.2. R2 #3 also faulted the affected run for covering no uncommitted work. |
| R1 #1–3, R2 #1, R3 #1–2 | Implementation | No environmental involvement in the transcripts. |
| R4 #1: `npm ci` lockfile validation | Dependency defect, with an unexplained environment divergence | See below. |
| R4 #2: `db:snapshot` | Windows platform defect | See below. |
| R4 #3 and R5: test matrix and assertion strictness | Implementation and test work | |

**Lockfile (R4 #1)**
- **Confirmed:** `@oxc-parser/binding-wasm32-wasi@0.156.0` pins `@emnapi/core` and `@emnapi/runtime` to `2.0.0-alpha.6`. `@napi-rs/wasm-runtime@1.2.7` has a peer range that excludes it.
- **Confirmed:** my `npm ci` printed `ERESOLVE overriding peer dependency` and still exited 0. That was true before the fix (`794a4053` output and `npmci.log`) and in the 14:56Z failed run.
- **Confirmed:** I did not reproduce the reviewer's exit 1. My `48612fae` summary says so. Plain `npm ci` on Node 24.22.1 with npm 11.21.3 exited 0 at 03:05Z in `794a4053`, on the unmodified committed lock.
- **Unexplained:** why the reviewer's run failed and mine did not.
- **Hypotheses only:** npm cache or registry packument state, or how npm 11.21.3 was installed (the `--prefix` install in one session, the shim in another).
- **After the override:** the Tech Lead's 5th review reports that `npm ci` and `npm install` pass and preserve the lock.

**`db:snapshot` (R4 #2)**
- **Confirmed:** the symptom appeared in my pass-3 evidence as a "silent no-op". I filed it as "out of scope" and "not fixed", and I did not diagnose it.
- **Confirmed:** the Tech Lead later traced it to the runner not shell-spawning `tsx.cmd` on Windows, with the child `error` swallowed into exit 1. The fix is uncommitted.
- **Not observed:** I did not see `EINVAL` in my own logs.
- **Hypothesis:** the `EINVAL` code comes from newer Node's refusal to spawn `.cmd` without a shell.
- **Side effect of the fix:** it now emits a `DEP0190` warning.

**Firefox/axe crash**
- **Confirmed:** it happened between 12:20Z and 13:13Z, during the 24.13.0 era. It was deterministic on one page, and I traced it to axe running on the populated page. It stopped after I removed redundant `aria-labelledby` section landmarks.
- **Cannot be determined:** root cause. The markup change and the later toolchain change are confounded.
- **Hypothesis:** the Node version is an implausible cause, since the browser is a separate process, but I did not test it. The Tech Lead's QA note already requires a rerun in supported Firefox.

## 4. Did the environment drive repeated correction attempts?

Environment- or tool-linked blocking items:

| Review | Count | Items |
|---|---|---|
| R1 | 3 of 8 | #5, #6, #7 |
| R2 | 1 of 4 | #3 |
| R3 | 0 | |
| R4 | 2 of 3 | #1, #2 |
| R5 | 0 | |

- **Pattern:** rounds 1, 2 and 4 contained such items. Rounds 3 and 5 did not.
- **Cost:** correction cycles repeated multi-minute installs and full gate reruns. The 4th round alone included at least six `npm ci` runs, plus building the pinned toolchain.
- **Substantive defects:** the stale re-enable, activation reuse, HTTPS handling and test-matrix defects would have needed correction regardless of environment.
- **Confidence:** this is reconstructed attribution, not measured.

## 5. Evidence to reconsider

1. **First-pass gate results** (13:18–14:31Z, unsupported toolchain): already superseded. The evidence file says it replaces them. Do not cite pass-1 figures such as 106 PostgreSQL tests, the zero-task affected run and e2e 30/30.
2. **"Lock regenerated with npm 11.21.3 (four nested optional `@emnapi` entries; no version change)":** misleading. Those entries are the peer-conflicting pair, and the R4 `npm ci` failure involved them. My logs showed the warning, and I did not report it. The same applies to "`npm ci` exit 0, 0 EBADENGINE". It is literally true on my machine but incomplete.
3. **`npm audit` "14 moderate" versus the Tech Lead's "0":** I saw 14 under npm 11.6.2 (11:37Z) and under the pinned runs. npm version is therefore not the cause. The difference is unexplained, and I only noted that advisory data is time-dependent.
4. **"Seven install scripts skipped, none required"** (plan addendum K): the warning list in my logs matches your note. It is supported by green suites rather than by testing each package individually. Low risk, but it is inference.
5. **84396d71 gate evidence:** the gates ran under npm 11.19.1, not the pinned 11.21.3. The Tech Lead's independent 5th review covers this.
6. **0d657fd1 handoff:** I did not run `npm ci`, e2e or a guard-mutation check, and I disclosed that.

## 6. The YAML conflict

- **Not observed:** I found no YAML or Vite peer conflict in any Development Team transcript or surviving log. My outputs were often truncated with `tail` or filtered with `grep -v`, so absence is not proof.
- **Structural match in the lock:** Vite 8.3.5 and 8.3.8 declare an optional peer `yaml ^2.4.2`. The hoisted `node_modules/yaml` is 1.10.3, which does not satisfy it. A satisfying 2.9.0 is nested under `nx` only.
- **Pre-existing:** the same entries are identical at the initial commit (a74f7dd) and at the STEP-01 commit (1330592).
- **No causal link:** I found no evidence that this conflict caused any stall or failure in my sessions.

## Gaps

- The 4th-review `npm ci` divergence is unexplained.
- The Firefox crash root cause is undetermined.
- I have no visibility into the Codex stall.
- Pass-1 EBADENGINE output can't be recovered, because my commands truncated it.