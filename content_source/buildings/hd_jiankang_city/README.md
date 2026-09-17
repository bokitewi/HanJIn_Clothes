# 建康城可编辑源场景

`hd_jiankang_city.blend` 是正式可编辑交付；`JIANKANG_CITY` 内每个实例可单独移动、旋转或统一缩放。`SOURCE_PARTS` 为隐藏的素材部件；完整宫殿和院落内部结构保留。`PREVIEW_CAMERAS` 提供离线预览相机。布局与入口说明也嵌入 Blender 文本块。

正式模型位于 `../../../gfx/models/buildings/special/hd_jiankang_city/`。当前保持外墙、宫墙及地图定位，城内建筑已放大并补排完整汉代偏殿配房；皇宫、小城、宗庙比加密前大 25%，皇宫主门朝南。民居最长边 13 参考像素，院落 01／02／03 比例 13，固定西侧 04 院落比例 10。道路规划宽度 3 像素。道路和水面已修正为朝上三角面，并使用原版 `decal_local`／`LocalDecals` 地表通道；隐藏背面的离线预览及导出回读通过，未运行 CK3 验证。

布局、源文件哈希、纹理路径和入口方向分别保存在相邻 `.layout.json` 与 `.sources.json` 中。图示上方为北；原图坐标转换为 Blender 坐标：X=(图X-618)×0.04，Y=(525-图Y)×0.04，Z向上。

复现脚本在两套 mod 的同级 `tools` 中。准备缓存后，依次运行 `jiankang_layout.py`、`jiankang_build.py`（Blender）、`jiankang_asset.ps1`、`jiankang_layout_audit.py`、`jiankang_verify_render.py`（Blender）、`jiankang_traffic.py`（Blender）、`jiankang_acceptance.py`、`jiankang_editable_finalize.py`（Blender）、`jiankang_delivery.py`。每一步完成后再运行下一步。`jiankang_prepare.py` 可从本地原素材和此前已核对的成都源缓存重新准备部件库；缓存路径均在 D 盘。

正式导出仅有 LOD0；没有 CK3 实机性能或显示验证。预览与验收报告在 `D:\codex_checks\hd_jiankang_city`。
