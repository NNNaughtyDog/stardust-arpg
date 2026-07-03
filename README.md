# Isometric Dark ARPG Prototype

> 目标：创建一个“暗黑2精神内核”的原创 2D 等距视角 ARPG 原型项目，用于验证镜头语言、点地移动、刷怪掉落、装备词缀、技能成长和地牢循环。

## 定位

本项目不是对《暗黑破坏神2》的复刻或克隆，不使用其 IP、角色、怪物、地图、UI、音效、剧情、数值表或美术素材。

本项目只借鉴经典等距 ARPG 的通用体验结构：

- 2D 等距/斜 45 度俯视镜头
- 鼠标点地移动与点击攻击
- 城镇补给、野外探索、地牢挑战
- 怪物群战、精英怪、Boss 战
- 随机装备、词缀、稀有度、掉落表
- 职业技能树与 Build 成长
- 暗黑奇幻氛围、低饱和、高对比火光

## 推荐技术方向

- 引擎：Godot 4.x
- 类型：2D 等距视角 ARPG
- 角色：CharacterBody2D
- 动画：AnimatedSprite2D / AnimationTree
- 技能碰撞：Area2D
- 地图：TileMapLayer / 等距瓦片
- 数据：Resource + JSON/CSV
- 存档：本地 SaveGame

## MVP 垂直切片

第一个可玩版本只追求 15 分钟体验闭环：

1. 玩家出生在破败营地。
2. 点击地面移动，点击怪物攻击。
3. 出城进入星尘污染荒野。
4. 击败 5 种怪物，获得装备掉落。
5. 打开背包，装备武器/护甲。
6. 进入一个小型地牢。
7. 击败 Boss，获得稀有装备。
8. 回城整理战利品。

## 初始内容范围

- 1 个职业：流亡剑士
- 3 个核心技能：普通攻击、冲刺斩、星尘爆裂
- 5 种怪物：腐化爬虫、荒野暴徒、星尘射手、精英异化者、裂隙 Boss
- 1 个安全营地
- 1 张野外地图
- 1 个 3~5 房间地牢
- 20 件基础装备
- 30 个随机词缀
- 1 套基础 UI：血量、法力、技能栏、背包、装备栏

## 目录说明

```text
prototypes/isometric-dark-arpg/
├─ README.md
├─ docs/
│  ├─ 00_project_overview.md
│  ├─ 01_game_vision.md
│  ├─ 02_core_loop.md
│  ├─ 03_technical_architecture.md
│  ├─ 04_art_bible.md
│  ├─ 05_system_breakdown.md
│  └─ 06_codex_tasks.md
└─ game/
   ├─ project.godot
   ├─ scenes/
   ├─ scripts/
   └─ data/
```

## 当前阶段

当前阶段只做项目初始化和设计落地。后续由 Codex 按 `docs/06_codex_tasks.md` 逐步实现原型功能。
