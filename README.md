# TGAPI 使用手册

TGAPI（图观统一开发 API）是面向数字孪生场景的 3D 可视化 JavaScript SDK，提供端渲染和流渲染两种模式，帮助开发者快速构建三维可视化应用。

## 文档结构

```shell
docs/
├── 01.start/       # 快速入门
│   ├── 01.overview.md           # 产品概述
│   ├── 02.install.md            # 安装部署
│   ├── 03.hands-on.md           # 快速上手
│   ├── 04.event.md              # 事件机制
│   └── 05.history.md            # 版本历史
│
└── 02.manual/      # API 参考手册
    ├── 01.global/               # 全局操作
    ├── 02.overlay/              # 覆盖物层控制
    ├── 03.path/                 # 路径操作
    ├── 04.area/                 # 区域操作
    ├── 05.circular-area/        # 圆形区域
    ├── 06.oblique-photography/  # 倾斜摄影
    ├── 07.gis-map/              # GIS 地图
    ├── 08.terrain-process/      # 地形处理
    ├── 09.wms-layer/            # WMS 图层
    ├── 10.landmark-layer/       # 地标图层
    ├── 11.column-layer/         # 柱状图层
    ├── 12.grid-layer/           # 网格图层
    ├── 13.heatmap-layer/        # 热力图层
    ├── 14.starlight-layer/      # 星光图层
    ├── 15.bubble-layer/         # 气泡图层
    ├── 16.event-layer/          # 事件图层
    ├── 17.trail-layer/          # 轨迹图层
    ├── 18.click-layer/          # 点击交互层
    ├── 19.od-line-layer/        # OD 线图层
    ├── 20.type-area/            # 类型区域
    ├── 21.color-area-layer/     # 颜色区域层
    ├── 22.path-spot-heatmap/    # 路径点位热力图
    ├── 23.path-segment-heatmap/ # 路径分段热力图
    ├── 24.mode-trail-layer/     # 模式轨迹层
    └── 25.model-landmark-layer/ # 模型地标层
```

## 快速开始

### 初始化

```javascript
// 创建应用实例
let appInstance = new TGApp.App();

// 初始化服务
appInstance.initService(
  {
    container: document.getElementById('container'),
    mode: 'scene', // 端渲染模式 或 'streaming' 流渲染模式
    url: 'scene-url',
    token: 'auth-token',
    resourceBasePath: 'https://www.tuguan.net/public/tgapp/scene',
  },
  (result) => {
    // 初始化回调
  }
);
```

### API 调用

所有 API 调用均使用 `uniCall` 方法：

```javascript
appInstance.uniCall('methodName', jsonData, (result) => {
  // 处理回调结果
});
```

## 渲染模式

| 模式                   | 说明                      |
| ---------------------- | ------------------------- |
| **端渲染 (scene)**     | 基于 WebGL 的浏览器端渲染 |
| **流渲染 (streaming)** | 云端渲染 + 视频流传输     |

## 环境要求

- **浏览器**: Chrome 88+、Edge 88+、360 浏览器 13+
- **硬件**: 最低 8GB 内存 + 集成显卡；推荐 8GB 内存 + NVIDIA GTX 960+ 独立显卡
- **框架**: 支持 Vue.js 和 React 集成

## SDK 版本

3.3.x

## 许可证

请参阅项目许可证文件了解详情。
