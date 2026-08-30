<div align="center">

<p><a href="README.md">English</a> · <strong>简体中文</strong></p>

<h1>HOOZi CS2</h1>

<p><strong>Counter-Strike 2 · DMA · 外部读取</strong></p>

<p>开发中 · 当前阶段免费</p>

</div>

<p align="center">
  <a href="../../releases">
    <img
      src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD-Releases-2EA043?style=for-the-badge&logo=github&logoColor=white"
      alt="下载"
    >
  </a>
  <a href="https://discord.gg/PnfR95ADW">
    <img
      src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"
      alt="Discord"
    >
  </a>
  <img
    src="https://img.shields.io/badge/%E7%8A%B6%E6%80%81-%E5%BC%80%E5%8F%91%E4%B8%AD-F59E0B?style=for-the-badge"
    alt="开发中"
  >
</p>

---

## 状态

已实现的游戏内功能只有 ESP。自瞄、扳机、雷达、物品绘制均未实现。

---

## 功能

### 视觉 › 玩家 —— ESP

```text
ESP
├── 总开关 · 排除队友 · 可视检查
├── 预览排版 —— 元素在 8 个槽位间拖拽、每元素右键设置、字段跨场景链接
├── 元素
│   ├── 盒子（轮廓 / 四角轮廓 · 粗细）
│   ├── 骨骼（连线 / 胶囊 · 粗细）
│   ├── 血条 · 护甲条
│   └── 昵称 · 武器 · 距离
├── 3 套分状态配置（遮挡 / 可见 / 队友）
│   └── 每套独立的颜色与显示范围
└── 尺寸 —— 最大距离 · 条宽度范围 · 绘制字体大小范围 · 绘制字体
```

### 其余菜单页（配置与框架）

| 页面 | 内容 |
| --- | --- |
| **视觉 › 增强** | 空占位，未实现 |
| **杂项** | 水印（DMA · 输入方式 · 配置 · 玩家数 · FPS）、按键绑定列表 |
| **参数管理** | 多配置文件 —— 新建 / 加载 / 保存 / 删除 / 搜索，自动保存，置顶已加载 |
| **用户设置** | 菜单缩放与字体、简体中文 / 繁體中文 / English / 한국어、主题配色、显示器选择、性能面板、开发者工具 |

### 底层

```text
├── FPGA DMA 连接
├── 偏移在进程内自动解析，每次 attach 重新解一遍
│   ├── 特征码扫描 + Source 2 schema 遍历，无需维护偏移文件
│   ├── 特征码每小时自动同步上游
│   └── 按游戏版本缓存，游戏更新后自动重新解析
└── 可视判定用的地图碰撞几何
    ├── 21 张官方地图，hull 与 mesh 都收（木箱、木板、栏杆在内）
    └── 后台线程加载 —— office 49ms，inferno 843ms
```

---

## 开发计划

```text
自瞄        —— 瞄准辅助、扳机、分武器设置
雷达        —— 小地图雷达、全图雷达
物品绘制    —— 掉落武器、投掷物、C4 计时
辉光        —— 穿墙高亮
Lua 脚本    —— 开放 API 的用户脚本系统
```

不承诺时间表。

---

## 使用要求

DMA 环境（FPGA 卡 + 第二台电脑）。外部只读，不注入、不写入游戏进程。

---

<div align="center">

<a href="../../releases">Releases</a>
 •  <a href="https://discord.gg/PnfR95ADW">Discord</a>

</div>
