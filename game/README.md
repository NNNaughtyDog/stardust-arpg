# Godot Game Prototype

本目录用于承载 2D 等距暗黑奇幻 ARPG 原型工程。

## 打开方式

1. 使用 Godot 4.x。
2. 打开 `prototypes/isometric-dark-arpg/game/project.godot`。
3. 运行项目。
4. 当前应进入 `scenes/main/Main.tscn`。

## 当前状态

当前仅完成最小工程骨架：

- `project.godot`
- `scenes/main/Main.tscn`
- 初始技能数据
- 初始怪物数据
- 初始装备数据
- 初始词缀数据
- 初始掉落表

还没有实现玩家移动、战斗、背包、掉落实例化等逻辑。

## 后续实现顺序

请按 `../docs/06_codex_tasks.md` 执行：

1. 初始化 Godot 原型工程
2. 玩家点地移动
3. 基础怪物 AI
4. 普通攻击与伤害结算
5. 掉落系统
6. 背包与装备栏
7. 技能系统
8. 野外测试图
9. 地牢与 Boss 房
10. 15 分钟垂直切片

## 工程约束

- 保持 Godot 工程和文档隔离在本目录下。
- 不要污染主项目根目录。
- 不要直接复刻任何现成游戏 IP 或素材。
- 新增系统时同步更新 `docs/`。
