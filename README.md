# 中国旅行足迹指挥室

此示例演示了如何使用 ECharts 加载本地 GeoJSON 与 CSV 数据，
在暗色/赛博朋克风格的界面中展示中国地级市与省级的旅行足迹、统计与表格。

## 功能亮点

- 三种视图模式：地级市地图 / 省级地图 / 表格。
- 好友勾选与访问人数过滤会同步驱动地图、统计卡片与图表。
- 统计卡片展示覆盖总数、重合数、独行数与头号出行者。
- 图表：
  - “每位朋友覆盖城市/省份”柱状图。
  - “省级覆盖率对比（城市维度）”长图表（覆盖率与重合率叠加展示）。
- 表格支持城市/省份访问矩阵与列排序。

## 运行方法

1. 确保工作目录下包含以下文件：
   - `index.html` （主页面）
   - `cn_city.geojson` （地级市边界数据）
   - `cn_province.geojson` （省级边界数据）
   - `visits.csv` （访问数据）
   - `avatar/` （头像素材）

2. 由于浏览器的 `fetch` 不能直接读取文件系统，需要通过 HTTP 服务提供文件。
   例如在项目目录运行：
   ```bash
   python3 -m http.server 8000
   ```
   然后在浏览器中打开 `http://localhost:8000/index.html`。
   （也可以使用 VS Code 的 Live Server、Node `serve` 等工具）

## 数据说明

- `visits.csv` 必含字段：
  - `行政区划名称`（地级市名称）
  - `所属省级行政区`（省级名称，用于覆盖率计算）
  - 朋友列（如 `Skipper`、`Kowalski`、`Private`、`Rico`，值为 `Y`/空）
- GeoJSON 来源：`cn_city.geojson` 与 `cn_province.geojson` 均下载自
  [阿里云 DataV 行政区划选择器](https://datav.aliyun.com/portal/school/atlas/area_selector#&lat=31.769817845138945&lng=104.29901249999999&zoom=4)。

## 备注

- 如需更换好友或新增人员，只需在 `visits.csv` 增加列，并在 `index.html` 的 `friendMeta` 中加入对应配置。
