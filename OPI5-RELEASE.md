# Orange Pi 5 ARM64 compatibility release

This fork publishes an unofficial ARM64 compatibility repack for Armbian on Orange Pi 5-class RK3588 boards.

The release workflow starts from the pinned official DuckStation ARM64 AppImage and matching upstream ARM64 dependency archive. It does not modify DuckStation emulation or rendering source code. The packaging repair places `libshaderc_shared.so`, `libspirv-cross-c-shared.so.0`, and `libsqlite3.so.3` beside `usr/bin/duckstation-qt`, matching DuckStation's Linux bundled-library lookup.

Rolling release tag: `opi5-arm64-preview`.

## Physical verification

**Status: PASS — physically verified on Orange Pi 5 Pro on 2026-08-30.**

Tested artifact:

- File: `DuckStation-arm64-Armbian-OrangePi5.AppImage`
- SHA-256: `c403f36ceac24e316d55e0d89577ecde593a8b2d868c647131d1fa50bf8cda63`
- DuckStation: `0.1-11828-gb0f7c5c16 [master]`
- Session: KDE Wayland on Armbian
- GPU: `Mali-G610 MC4`
- Vulkan driver: Mesa `26.0.8-1ubuntu0.3` / `panvk`
- Vulkan device API: `1.4.335`

Physical runtime evidence:

- DuckStation launched as native Linux ARM64.
- The previous `libsqlite3.so.3` load failure is resolved; DuckStation created and loaded the achievements database successfully.
- The previous `libshaderc_shared.so` load failure is resolved.
- DuckStation selected `Mali-G610 MC4` through PanVK and created the Vulkan GPU device successfully.
- Fullscreen UI initialized successfully.
- Vulkan pipeline cache was written successfully during shutdown.
- Video thread shut down cleanly.

This verifies the packaging repair on the tested Orange Pi 5 Pro / Armbian configuration. It does not imply endorsement or support by the upstream DuckStation project.
