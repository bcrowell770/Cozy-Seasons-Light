# Cozy Seasons Light Changelog

## 1.1.0

- Rolled in the botanical particle rendering from Cozy Seasons 1.4.0.
- Spring petals now have rounded tops and tapered bases.
- Autumn leaves now have pointed, asymmetric silhouettes and short stems.
- Preserved the Light edition's 12 backgrounds per season and two-hour schedule.

## 1.0.0 - initial light edition

- Forked from Cozy Seasons 1.3.0 with a distinct app identity.
- Retains 12 even-hour backgrounds per season; each scene displays for two hours.
- Keeps the existing settings and seasonal particle effects.


All notable changes to this watchface will be documented here.

## [Unreleased]

### 1.3.0 � in review

- Use fractional positions and gradual, independently timed drift for seasonal particles.
- Fix fireflies moving only horizontally; add gentle boundary steering and bounded lifetimes.
- Preserve firefly color and shape, with slower independent blink timing.
- Ignore additional shakes while an animation is running.
- Enlarge all particle types while retaining mixed sizes; add pink, lavender, cream, and white spring petals.
- Redraw summer pollen/seed fluff with fine filaments and a hanging seed, with slower wind-driven drift.
- Keep all 96 hourly backgrounds unchanged pending palette comparison.
- Hardware animation and loading checks remain pending.

---

## [1.2] - 2026-07-18

### Added

- Complete local Pebble SDK project files and resource manifest
- Reproducible local Basalt build support through the Pebble SDK
- Background resource allocation failure logging

### Changed

- Reduced the 24 winter background images from 1,535,595 bytes to 227,863 bytes by converting them to the native Basalt color palette
- Load the initial background before smaller UI allocations to reduce heap fragmentation
- Reduced the unused AppMessage outbox allocation from 256 bytes to 64 bytes

### Fixed

- Retry a failed background allocation on the next minute tick instead of leaving the watchface blank until the following hour
- Detach the bitmap layer before destroying its background bitmap, preventing a stale pointer during image changes

### Validation

- Built locally with Pebble SDK 4.17 and successfully sideloaded and tested on Basalt hardware

---

## [1.1] - 2026-04-11

### Added

- Low Vision Mode with backing panel and improved readability

### Changed

- Split AM/PM into separate layer for better layout control
- Reworked layout system using apply_layout()

### Fixed

- 12-hour time truncation issues
- 24-hour time truncation (ellipses) in worst-case widths
- Date descender clipping (e.g., "p" in Apr)
- Further widened the 12-hour time area to target remaining midnight/near-midnight ellipsis cases
- Rebalanced the 12-hour time and AM/PM line so it sits more naturally after the midnight fit fixes
- Restored a consistent full battery-track display in Low Vision Mode while keeping its thicker bar
- Restored the Bluetooth disconnect icon to a fully visible right-center position in both normal and low vision modes
- Matched the Bluetooth icon layer to the full 30x30 asset size to prevent clipping

---

## [1.0] - Initial Functional Build

### Added

- Seasonal backgrounds with hourly images
- Particle animations (tap/shake triggered)
- Bluetooth disconnect indicator
- Battery bar
- Clay settings system

### Notes

- Initial working version
