# carnegie-observatories/.github

Shared GitHub Actions for the LCO instrument repos.

- `.github/workflows/macos-app.yml`: reusable build of a macOS instrument app
  (Release, arm64). Call it from the app's `.github/workflows/ci.yml`; the
  "LCO macOS instrument app" template under Actions → New workflow does that.
- Inputs: `app` (required), `pre-build`, `submodules`, `configuration`,
  `runs-on`.
- Builds run on the self-hosted Mac labelled `sbs-mac` (sbs-inst1, set up by
  lco-ansible `playbooks/github_runner.yml`). `runs-on: macos-latest` uses a
  GitHub-hosted runner instead, which costs the org's paid minutes.
- Callers pin `@v1`. Move the tag after a compatible change; breaking
  changes get `v2`.

Background: lco-ansible `docs/plans/ci-release-builds.md`.
