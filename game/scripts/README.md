# Scripts Directory Guide

建议后续 Codex 按以下结构新增脚本：

```text
scripts/
├─ core/
│  ├─ game_manager.gd
│  └─ scene_loader.gd
├─ player/
│  ├─ player.gd
│  ├─ player_stats.gd
│  ├─ player_input_controller.gd
│  ├─ player_movement_controller.gd
│  ├─ player_combat_controller.gd
│  └─ player_skill_controller.gd
├─ monsters/
│  ├─ monster.gd
│  ├─ monster_stats.gd
│  ├─ monster_ai.gd
│  └─ monster_combat.gd
├─ combat/
│  ├─ damage_calculator.gd
│  ├─ hitbox.gd
│  └─ hurtbox.gd
├─ skills/
│  ├─ skill_data.gd
│  ├─ skill_runner.gd
│  └─ skill_projectile.gd
├─ items/
│  ├─ item_data.gd
│  ├─ item_generator.gd
│  └─ affix_generator.gd
├─ loot/
│  ├─ loot_dropper.gd
│  └─ ground_loot.gd
├─ inventory/
│  ├─ inventory.gd
│  ├─ equipment.gd
│  └─ inventory_ui.gd
├─ ui/
│  ├─ hud.gd
│  ├─ damage_number.gd
│  └─ tooltip.gd
└─ save/
   └─ save_game.gd
```

## 约束

- 单个脚本只负责一个清晰职责。
- 数据加载与战斗表现分离。
- UI 不直接修改核心数据，应通过 Inventory/Equipment 等模块交互。
- 掉落与装备生成优先读取 `data/` 配置。
