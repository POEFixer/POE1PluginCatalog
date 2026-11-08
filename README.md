# POE1Fixer plugin catalog

The plugins POE1Fixer can download and install from its **Plugins** tab. The app reads
[`catalog.json`](catalog.json) from this repository over HTTPS and installs only what it lists.

## How the app trusts it

- Every entry pins its release zip by **SHA-256 and size**. The app downloads the zip only from a
  GitHub release of a `POEFixer/` repository, over HTTPS, following redirects only to GitHub's own
  download hosts, and checks size and SHA-256 before it opens the zip.
- It checks every file in the zip (no paths outside the plugin folder, no links, at most 256 files,
  256 MiB unpacked) and the packaged `plugin.json` (id, version and SDK must match the entry).
- An installed plugin runs in its own sandboxed process, like a plugin copied in by hand. Installing
  enables it; permission to send input is never granted by installing.
- Both files here are generated, never edited by hand: `catalog.json` is written from the release
  zips themselves by the POE1Fixer maintainers' packaging tool.

## Plugins

### SDK Example 2.0.0

A guided tour of the plugin SDK: 23 lessons, each with live data, the limits the app enforces and a code snippet to copy. Reads game memory only on its Memory page; sends input only when you arm its safe demo (one mouse move, no click, no key). Uses no network.

- Id `example`, installs into `Plugins\ExamplePlugin`
- Author: POE1Fixer
- Source and release: [POEFixer/POE1ExamplePlugin](https://github.com/POEFixer/POE1ExamplePlugin) ([v2.0.0](https://github.com/POEFixer/POE1ExamplePlugin/releases/tag/v2.0.0))
- Permissions: memory, input; overlay: yes; panel: yes
- Plugin SDK 1; needs POE1Fixer v38 or newer
- Package: [ExamplePlugin.zip](https://github.com/POEFixer/POE1ExamplePlugin/releases/download/v2.0.0/ExamplePlugin.zip), 477953 bytes,
  SHA-256 `e0e013b55115348d5e64091388768e4a2a870213842f4a0637f8ffb5f653215d`

Changes:

- First release in the plugin catalog: a guided tour of the plugin SDK in 23 lessons.
