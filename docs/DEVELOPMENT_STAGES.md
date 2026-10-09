# Development stages

The existing BLE connection lab was retained. On October 9, 2026, ten later
stages were imported from an existing development history in their original
order, with the same commit messages. The new commit dates record the import;
they do not date the original engineering work. The identifiers below provide
traceability between the earlier history and this repository.

| Stage | Commit in this repository | Original identifier |
| --- | --- | --- |
| Keep firmware build script LF for Codespaces | [12affa1](https://github.com/AnujR17/toki/commit/12affa1ad00087169a921bc5e0e8a323c432a100) | `414c501782a6515389a32f0fecb0c18c5df5f32d` |
| Stage Toki app and integrated firmware source | [8dce7b8](https://github.com/AnujR17/toki/commit/8dce7b89aa28af38b43b5cdb5f1a769bf8a3f09e) | `95fc434c4222581e4e2e5c80b5193e45b4d988ab` |
| Stage I2S firmware correction | [958642e](https://github.com/AnujR17/toki/commit/958642ea3213c6e8be12f45bbfdfa7911de1b147) | `8ba1190e73192b484d161f347e060384843bb3df` |
| Stage final Toki interaction and build fixes | [b6746ba](https://github.com/AnujR17/toki/commit/b6746ba9781fb72a5a691ca8ea994c4310a3c66e) | `113156148da3df06558d89038aa57897aa3d6058` |
| Build Toki companion app and integrated ESP32 firmware | [c27c606](https://github.com/AnujR17/toki/commit/c27c6061952b7f7b2fcae155ea370b0135bc61c3) | `bbc4393ce8baad18bdf5285fe574ac0b888b60e3` |
| Clarify current Toki build and test status | [38c172b](https://github.com/AnujR17/toki/commit/38c172b625e0e56a1b80800ddb8325ff04b9e257) | `f9fbb3618f1b2ff51b30b4a8f5517f0fe343e6b5` |
| Link Toki app to Expo build project | [7fe21db](https://github.com/AnujR17/toki/commit/7fe21db6ca5fd8bc25f28907825e3d010ef8c9f2) | `627f0320adf13cbf335a906fa8c1bb720bd3f3bb` |
| Add simple task flow, protocol 3 and verified Wi-Fi OTA | [a7c8d36](https://github.com/AnujR17/toki/commit/a7c8d36506d11dc6f0e7ee06561cca6be3bd666d) | `806401240f592b420e847b2451ef909a80164c76` |
| Create quiet writing flow and restore device task cues | [13cfeb7](https://github.com/AnujR17/toki/commit/13cfeb7d996170e3bd513b8251835c946ca1f494) | `caf34519253173faecaa890b15195d7cd64b1312` |
| Swap center and right touch pins for enclosure wiring | [fae4dd0](https://github.com/AnujR17/toki/commit/fae4dd0650ce0beb49e32a3596e6a56e4a5a3164) | `725293fe6b7f6616f8c42c3b0a08a4b745a43c9f` |

## Repository configuration

The app identifiers are `com.anujr17.toki` for Android and iOS. New builds install
as a separate app from builds using another identifier. Task data does not
automatically move between these installations.

The existing EAS project configuration was imported. To use a different Expo
account or project, relink from `mobile/` with `npx eas-cli@latest init` before
requesting a build. No new APK or firmware build was submitted during this import.

The temporary source archives in the intermediate stages follow the original
sequence and are removed by the later integrated-source stage. Their app
configuration uses the same repository-specific identifiers.

## Verification during import

- File hashes matched the original content except for the app identifiers,
  corresponding archived configuration, and repository recovery documentation.
  One historical task-screen file was normalized to UTF-8 during transfer; it
  is replaced by the later tab-screen structure.
- Speaker regression, OTA upload-timeout regression, and existing app
  experience tests passed.
- Lint and TypeScript checks could not run: Expo and TypeScript dependencies
  were unavailable, and the workspace network proxy prevented installation.
- No fresh device flashing or physical acceptance test was performed.

The current source contains firmware 3.0.8 and protocol 3. Device pin mapping:
left GPIO 34, center GPIO 21, right GPIO 35. See [recovery instructions](RECOVERY.md)
for the imported protocol-3 baseline.
