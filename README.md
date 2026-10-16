# carnegie-observatories/.github

Shared GitHub Actions for the LCO instrument repos.

- `.github/workflows/macos-app.yml`: reusable build of a macOS instrument app
  (Release, arm64). Call it from the app's `.github/workflows/ci.yml`; the
  "LCO macOS instrument app" template under Actions → New workflow does that.
- Inputs: `app` (required), `pre-build`, `submodules`, `configuration`,
  `runs-on`.
- Callers pin `@v1`. Move the tag after a compatible change; breaking
  changes get `v2`.

Background: lco-ansible `docs/plans/ci-release-builds.md`.
