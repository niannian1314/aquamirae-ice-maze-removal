# 海灵物语冰迷宫移除补丁 / Aquamirae Ice Maze Removal

禁用 [Aquamirae（海灵物语）](https://www.curseforge.com/minecraft/mc-mods/aquamirae) 中 **ice_maze（冰迷宫）群系** 的生成。

- modId：`aquamirae_ice_maze_removal_1788556824`（AutoForge 生成的带数字后缀）
- 版本：`1.0.0`
- 环境：**Minecraft 1.20.1–1.21 / Forge 47.4.10+**
- 必需依赖：`aquamirae`（在其后加载）
- 作者：2046820954@qq.com
- License：**All Rights Reserved**（原 mods.toml 声明）

## 实现方式

1. **生物群系标签**：`data/aquamirae/tags/worldgen/biome/ice_maze.json` 用 `"replace": true` 把标签值设为只有 `aquamirae:ice_maze`，配合 Forge 事件逻辑把这个群系从世界生成中移除。
2. **Mixin Accessor**：`BiomeClimateAccessor` 注入访问 `Biome$ClimateSettings`（`f_47437_`），供事件类在生成阶段判断/处理该群系的气候设置。

## 仓库内容说明

本次通过 GitHub API 提交的是文本资源：`mods.toml`、`MANIFEST.MF`、`pack.mcmeta`、Mixin 配置与 refmap、冰迷宫群系标签 JSON。

> 原 jar 内 `mods.toml` 的 description 仍是 MCreator/AutoForge 默认占位文本（"Example mod description..."），本仓库已替换为真实说明。

以下**编译字节码未包含**（上传通道仅支持文本）：

- `cn/autoforged/aquamirae_ice_maze_removal_1788556824/**/*.class`（3 个 .class）

完整可运行的 `aquamirae_ice_maze_removal-1.0.0.jar` 请通过 GitHub 网页「Add file → Upload files」拖拽上传，或在 Release 中发布。
