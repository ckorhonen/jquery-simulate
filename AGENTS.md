# Repository guide

## Sources and commands

`jquery.simulate.js` is the plugin source; `test/unit/simulate.js` and `test/index.html` provide QUnit browser tests; `external/` holds browser dependencies; `Gruntfile.js` owns lint, build, and test tasks. Preserve contribution/license guidance and browser compatibility represented by the fixtures.

Install the historical Node dependencies with `npm install`; there is no npm lockfile. The manifest pins Grunt 0.4.1 and old PhantomJS-era tooling, so report compatibility failures rather than upgrading the stack as an incidental fix. Use an available compatible Grunt CLI; avoid a global install unless it is authorized. `grunt jshint` lints, `grunt qunit` runs browser tests, and `grunt build` generates `dist/`. The default `grunt` runs lint, QUnit, build, and size comparison. Missing external fixtures can be populated with the defined `grunt bowercopy` task after inspecting its downloads; the default task does not include it.

For event behavior changes, run the relevant QUnit cases and inspect them in a real browser via `test/index.html`. PhantomJS or syntax success alone does not establish current browser behavior. No npm test script or CI workflow is tracked. Keep generated distribution artifacts out of unrelated source edits.

## Completion

Check `git status --short`, preserve unrelated changes, and complete authorized local implementation through checks and repairs. Routine reversible choices can proceed directly. TestSwarm contacts an external service; publishing and remote test submission require explicit authorization. Report exact toolchain/browser/fixture blockers while continuing independent work. For prose-only changes, inspect paths and run `git diff --check`; close with actual checks/results and remaining browser gaps.
