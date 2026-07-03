# 03. 技术架构

## 引擎选择

建议使用 Godot 4.x，以 2D 等距视角方式实现。

## 基础目录

```text
game/
├─ project.godot
├─ scenes/
│  ├─ main/
│  ├─ player/
│  ├─ monsters/
│  ├─ maps/
│  ├─ items/
│  └─ ui/
├─ scripts/
│  ├─ core/
│  ├─ player/
│  ├─ combat/
│  ├─ monsters/
│  ├─ skills/
│  ├─ inventory/
│  ├─ items/
│  ├─ loot/
│  ├─ ui/
│  └─ save/
└─ data/
   ├─ items/
   ├─ affixes/
   ├─ skills/
   ├─ monsters/
   └─ drop_tables/
```

## 代码拆分原则

不要把所有逻辑写进一个 `Player.gd`。

建议拆分为：

```text
Player
├─ InputController
├─ MovementController
├─ CombatController
├─ SkillController
├─ InventoryController
└─ AnimationController
```

## 玩家模块

### PlayerStats

负责保存玩家属性：

- max_hp
- hp
- max_mana
- mana
- attack
- defense
- crit_rate
- crit_damage
- move_speed
- attack_speed
- level
- exp

### MovementController

负责：

- 鼠标点地移动
- 目标点缓存
- 到达目标点停止
- 与导航/碰撞系统交互

### CombatController

负责：

- 普通攻击
- 攻击距离判断
- 攻击冷却
- 伤害结算
- 受击反馈

### SkillController

负责：

- 技能快捷键
- 技能冷却
- 法力/能量消耗
- 技能实例化
- 范围判定

## 怪物模块

每个怪物建议由以下组件构成：

```text
Monster
├─ MonsterStats
├─ MonsterAI
├─ MonsterCombat
├─ LootDropper
└─ AnimationController
```

第一版 AI 状态：

```text
Idle
↓ 发现玩家
Chase
↓ 进入攻击距离
Attack
↓ 玩家离开范围
Chase
↓ 血量归零
Dead
```

## 战斗结算

第一版公式：

```text
base_damage = attacker.attack * skill.multiplier
reduced_damage = max(1, base_damage - target.defense)
crit_damage = reduced_damage * attacker.crit_damage if random < crit_rate
final_damage = round(crit_damage or reduced_damage)
```

后续可以增加：

- 元素伤害
- 抗性
- 命中/闪避
- 暴击独立乘区
- 伤害浮动
- 状态异常

## 装备与数据驱动

装备、词缀、怪物、技能、掉落表优先使用 JSON/CSV 或 Godot Resource 管理。

建议第一版先用 JSON，方便 AI 辅助开发和人工维护时快速生成、检查、修改。

## 存档

第一版只需要本地存档：

- 玩家等级
- 属性
- 背包
- 已装备物品
- 金币
- 已解锁地图

## 开发执行要求

每次实现功能时必须：

1. 保持目录结构清晰。
2. 不把所有代码堆进一个脚本。
3. 新增系统时同步更新对应文档。
4. 尽量用数据配置，不硬编码大量内容。
5. 每次 PR 或提交说明都写清楚测试方式。
