# Changelog

All notable changes to the AWTRIX WaterLevel app will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.5.0] - 2026-10-28

### Added
- **Hide when Full (100%)** (`hide_full`): New configuration setting allowing the app to automatically skip and hide from the AWTRIX carousel rotation when the water level reaches 100%.
- Integrated native AWTRIX `should_show()` lifecycle hook to cleanly bypass the app in the rotation cycle.
- Added immediate carousel advancement using `rotation.next()` if 100% fill level is reached while the app is currently displayed.

## [1.4.0] - 2026-10-10

### Fixed
- **Constant Bubble Frequency:** Fixed an issue where low water levels caused air bubbles to respawn rapidly in a high-frequency frenzy. Bubbles now follow a constant virtual cycle distance (`height`), ensuring the spawn rate and bubble count remain calm, steady, and identical across all water levels (from 0% to 100%).
- Staggered initial bubble spawn positions across the cycle distance on app initialization.

## [1.3.0] - 2026-10-10

### Added
- **Smooth Subpixel Anti-Aliasing:** Implemented vertical color blending (`blend_colors`) for air bubbles, enabling continuous, fluid upward gliding without discrete pixel-hopping.
- **Organic Horizontal Wobble:** Added subtle sine-wave oscillation to bubbles as they rise through the water.

### Changed
- **52×16 Wave Dynamics:** Restricted wave amplitude to strictly 1 pixel upwards above baseline (`base_y - 1`), eliminating excessive wave height and downward dips.

## [1.2.0] - 2026-10-10

### Added
- Dedicated **32×8 variant** (`WaterLevelV2_32x8.ax`) specifically tailored for Ulanzi TC001 and standard AWTRIX Light matrix displays.

### Changed
- **32×8 Layout:** Replaced waves with a calm, flat horizontal water surface line and rising bubbles for cleaner presentation on 8-pixel display heights.
- **32×8 Font:** Switched to standard AWTRIX font permanently centered horizontally and vertically, eliminating oversized font clipping.
- **32×8 Settings:** Removed redundant alignment options (`big_text`, `pos_x`, `pos_y`) for a streamlined user experience.

## [1.1.0] - 2026-10-10

### Fixed
- **Wave Calculation:** Corrected integer truncation bug in floating-point sine wave calculation by adding proper mathematical rounding.
- **Text Shadow Wave Preservation:** Prevented the text shadow gradient from blacking out the wave crest line (`0x4DD0E1`), keeping the wave surface visible across the entire matrix.

## [1.0.0] - 2026-10-10

### Added
- Initial release of the WaterLevel app for AWTRIX Light / NG.
- Live MQTT subscription supporting raw values and JSON payloads (`percent`, `level`, `value`, `val`).
- Real-time animated water waves and rising bubbles.
- Dynamic text drop-shadow for improved contrast against water pixels.
- Dual display modes: 10px large centered bitmap font and standard font with configurable horizontal/vertical alignment.
- Clear amber `--%` indicator for the initial no-data state.
