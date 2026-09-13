<div align="center">

<p><strong>English</strong> · <a href="README.zh-CN.md">简体中文</a></p>

<h1>HOOZi CS2</h1>
<img width="1939" height="811" alt="cs2-header-temp" src="https://github.com/user-attachments/assets/8789c888-3581-495e-b043-534bd19b76da" />

<p><strong>Counter-Strike 2 · DMA · External</strong></p>

<p>In development · free during this phase</p>

</div>

<p align="center">
  <a href="../../releases">
    <img
      src="https://img.shields.io/badge/Download-Releases-2EA043?style=for-the-badge&logo=github&logoColor=white"
      alt="Releases"
    >
  </a>
  <a href="https://discord.gg/PnfR95ADW">
    <img
      src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"
      alt="Discord"
    >
  </a>
  <img
    src="https://img.shields.io/badge/Status-In_Development-F59E0B?style=for-the-badge"
    alt="In Development"
  >
</p>

---

## Status

ESP is the only in-game feature implemented. No aimbot, trigger, radar or item ESP.

---

## Features
<img width="1407" height="807" alt="image" src="https://github.com/user-attachments/assets/f393b061-b244-441e-88da-5249fc61d7ef" />

### Visuals › Player — ESP

```text
ESP
├── Master switch · exclude teammates · visibility check
├── Interactive preview — drag elements between 8 layout slots,
│   per-element settings popup, field linking across scenarios
├── Elements
│   ├── Box (outline / corner · thickness)
│   ├── Skeleton (lines / capsule · thickness)
│   ├── Health bar · Armor bar
│   └── Name · Weapon · Distance
├── 3 per-state scenarios (occluded / visible / teammate)
│   └── Independent color and display range for each
└── Sizing — max distance · bar width range · text size range · font
```

### Other menu pages (configuration and framework)

| Page | Contents |
| --- | --- |
| **Visuals › Enhance** | Empty placeholder, not implemented |
| **Misc** | Watermark (DMA · input mode · config · players · FPS), keybind list |
| **Configs** | Multiple profiles — create / load / save / delete / search, auto-save, pin loaded |
| **Settings** | Menu scale and fonts, English / 简体中文 / 繁體中文 / 한국어, theme colors, monitor selection, performance overlay, dev tools |

### Under the hood

```text
├── FPGA DMA connection
├── Offsets resolved in-process on every attach
│   ├── Pattern scan + Source 2 schema traversal, no offset file to maintain
│   ├── Signatures auto-synced hourly from upstream
│   └── Cached per game build, re-resolved after a game update
└── Map collision geometry for the visibility check
    ├── 21 official maps, hulls and meshes (crates, boards, railings included)
    └── Loaded on a background thread — 49 ms on office, 843 ms on inferno
```

---

## Roadmap

```text
Aimbot        — aim assist, trigger, per-weapon settings
Radar         — mini radar overlay, full-map radar
Item ESP      — dropped weapons, grenades, C4 timer
Glow          — through-wall highlight
Lua scripting — user scripts with an exposed API
```

No dates are promised.

---

## Requirements

A DMA setup (FPGA card + a second PC). External and read-only — nothing is
injected into or written to the game process.

---

<div align="center">

<a href="../../releases">Releases</a>
 •  <a href="https://discord.gg/PnfR95ADW">Discord</a>

</div>
