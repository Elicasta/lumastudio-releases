# LumaRig Studio Releases

Public distribution repository for **LumaRig Studio**.

This repository contains release artifacts only. Application source remains private in `Elicasta/lumastudio`.

## Channels

- **Test builds**: unsigned development DMGs for internal Mac testing.
- **Stable releases**: signed/notarized DMG plus Tauri updater artifacts.

The desktop app checks this repository for `latest.json` and release assets.


## Automated test DMG builds

The public release repository has a macOS build workflow at:

`.github/workflows/build-test-dmg.yml`

It builds the private `Elicasta/lumastudio` source on a public standard macOS runner, uploads the DMG as a workflow artifact, and publishes an unsigned Beta test release.

### One required repository secret

Create a fine-grained GitHub personal access token with:

- Resource owner: `Elicasta`
- Repository access: **Only select repositories** → `lumastudio`
- Repository permission: **Contents: Read-only**

Then add it to this repository:

`lumastudio-releases → Settings → Secrets and variables → Actions → New repository secret`

Name:

`LUMASTUDIO_SOURCE_TOKEN`

The workflow is manual-only and does not run on pull requests.

### Run a build

Open:

`lumastudio-releases → Actions → Build LumaRig Studio Test DMG → Run workflow`

Default source ref:

`build/v0.2-audio-engine`

After it completes, the DMG is available both as an Actions artifact and as a public Beta release asset.
