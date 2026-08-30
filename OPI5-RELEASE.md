# Orange Pi 5 ARM64 compatibility release

This fork publishes an unofficial ARM64 compatibility repack for Armbian on Orange Pi 5-class RK3588 boards.

The release workflow starts from the pinned official DuckStation ARM64 AppImage and matching upstream ARM64 dependency archive. It does not modify DuckStation emulation or rendering source code. The packaging repair places `libshaderc_shared.so`, `libspirv-cross-c-shared.so.0`, and `libsqlite3.so.3` beside `usr/bin/duckstation-qt`, matching DuckStation's Linux bundled-library lookup.

Rolling release tag: `opi5-arm64-preview`.
