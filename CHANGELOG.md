# Changelog

All notable changes to this project are documented in this file.

## 2026-04-26

### Changed
- 表格 tab now always shows all three sections in a fixed order regardless of which map mode (城市/省份) was previously active: 省级覆盖率对比（城市维度）→ 省份访问矩阵 → 城市访问矩阵.
- `renderTable` accepts a target element so each table renders into its own container independently.
- Sort headers in each table control only that table's sort state; province and city tables sort independently.
- Removed dynamic title swapping from `updateModeText` — table section headings are now static.

### Added
- Responsive design for mobile and tablet devices.
  - **Tablet (≤ 900px)**: map height set to `60vh`; `min-height` removed from `.map-panel` so the panel doesn't force excess height on smaller screens.
  - **Mobile (≤ 600px)**: page padding tightened to `12px`; hero title font size uses `clamp(1.15rem, 5vw, 1.5rem)`; `.hero-controls` `min-width` removed and set to `100%` so controls always fill the row; mode-switch buttons stretch to equal width; stat-grid kept as 2-column grid (4 cards fit without overflow); stat value font size reduced to `1.4rem`; map height `52vh` with `min-height: 260px`; bar chart height lowered to `180px`; table rows collapse to a single column for readability.

## 2026-04-18

### Fixed
- Prevented `TypeError: Cannot set properties of null (setting 'innerHTML')` in `updateHeroChips` by guarding missing `#heroChips`.
- Improved favicon compatibility for GitHub Pages by documenting path/caching issues during debugging.

### Changed
- Moved `省级覆盖率对比（城市维度）` chart into the `table` tab.
- Updated view logic so the coverage chart is shown in `table` mode (city dimension only).
- Reordered table tab content so the coverage chart appears above `城市访问矩阵/省份访问矩阵`.
- Hid `足迹统计 👣` panel when `table` tab is active.
