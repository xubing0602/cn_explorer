# Changelog

All notable changes to this project are documented in this file.

## 2026-04-18

### Fixed
- Prevented `TypeError: Cannot set properties of null (setting 'innerHTML')` in `updateHeroChips` by guarding missing `#heroChips`.
- Improved favicon compatibility for GitHub Pages by documenting path/caching issues during debugging.

### Changed
- Moved `省级覆盖率对比（城市维度）` chart into the `table` tab.
- Updated view logic so the coverage chart is shown in `table` mode (city dimension only).
- Reordered table tab content so the coverage chart appears above `城市访问矩阵/省份访问矩阵`.
- Hid `足迹统计 👣` panel when `table` tab is active.
