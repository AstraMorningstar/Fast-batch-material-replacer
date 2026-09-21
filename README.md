Material Batch Replacer | 批量材质替换器

Star it if this helps:) | 如果有帮助请点亮星星：）

Formal Release v1.1 · 正式版 v1.1
By Astra Morningstar / Astra晨星

Batch-replace material shaders while preserving each material’s main image texture.

批量替换材质着色器，同时保留每个材质各自的主图像纹理。

English

Purpose

Models imported from PMX, FBX, and other formats often contain many materials. Editing their shader nodes individually can be repetitive and time-consuming.

Material Batch Replacer lets you build one shader node group and apply it across multiple materials. Each material keeps its own main texture, while the shared group controls the shader.

Features

Replace shaders on selected objects, the active material, or the entire scene.

Create a starter shader group or choose an existing group.

Connect each material’s texture color and alpha to your chosen group inputs.

Preserve UV and texture-mapping nodes.

Save copies of the original materials before replacement.

Alternatively, remove the shader setup and keep only the main texture and Material Output.

Return from group editing with the Back to 3D View (Shift + F5)

Separate English and Simplified Chinese packages.

Compatibility

Minimum version: Blender 3.6

Both language editions passed automated functional tests in:

Blender 3.6

Blender 4.2

Blender 4.5

Blender 5.1

The intended compatibility range is Blender 3.6–5.2. Blender 5.2 has not been verified, and not every intermediate version has been tested. Tests were performed in background mode, rather than through a complete manual interface review.

Installation

Download the EN ZIP for English or ZH_CN ZIP for Simplified Chinese.

Open Edit → Preferences → Add-ons.

Choose Install from Disk, or Install in older Blender versions.

Select the ZIP and enable the add-on.

Open the sidebar with N in the 3D View or Shader Editor.

Select the Material Replacer tab.

Install only one language edition. Both packages use the same add-on module.

When upgrading or switching languages, disable the add-on, install the desired ZIP, save your work, restart Blender, and enable the add-on.

How to Use

Select the model you want to modify.

Choose Active Material to test one material first, or Selected Objects to process the selected models.

Set the action to Replace with Node Group.

Click Create Group, then Edit Group, or select an existing shader group.

Build your shader inside the group:

Use Base Color for the original texture’s color.

Use Alpha for its transparency.

Connect your finished shader to the group’s Shader output.

Check the connection settings in the sidebar:

Texture Color →: the group input receiving texture color.

Texture Alpha →: the group input receiving texture alpha.

Surface ←: the group output connected to Material Output’s Surface input.

Leave Save Material Backups enabled if you want copies of the original materials.

Click Apply to Materials, review the count, and confirm.

The resulting structure is:

Original Image Texture → Shared Shader Group → Material Output

Editing the shared group later updates every material using it. Click (Shift + F5) to get back to 3D View.

Cleanup Mode

Keep Texture + Output Only removes the existing shader setup and leaves the main image texture and Material Output.

These nodes remain disconnected. You must add a shader or apply a replacement group afterward for normal rendering.

With Keep Texture Mapping enabled, the upstream mapping nodes are also retained. Disable it if you want only the texture and output nodes.

Backups and Recovery

With Save Material Backups enabled, each processed material gets a copy named with the suffix [MBR Backup].

To restore a material, select its material slot and choose the backup from the material dropdown. Save your .blend file to retain the backups.

Each application creates new backups. Backup materials still share image and node-group data with their originals; they are not independent copies of every asset.

You can also use Ctrl Z immediately after an operation to undo it.

Notes and Limitations

Main-texture selection is automatic and may be imperfect for complex imported shaders.

Images inside nested node groups are not extracted.

Normal maps, sphere maps, extra textures, and old shader effects are not automatically transferred into the replacement group.

Skip Materials Without Images is enabled by default.

Shared materials change on every object using them, including unselected objects. Make a material single-user first if needed.

Read-only linked materials are skipped.

Existing material transparency settings are preserved. Connecting alpha alone may not be sufficient to enable transparency.

Blender’s built-in menus and node labels follow Blender’s own language settings.


中文

插件用途

从 PMX、FBX 等格式导入的模型通常包含大量材质。逐个修改着色器节点既重复又耗时。

批量材质替换器可以将同一个着色器节点组应用到多个材质，同时保留每个材质各自的主纹理，方便统一调整模型的渲染效果。

主要功能

支持处理所选物体、当前材质或整个场景。

创建起始着色器节点组，或选择已有节点组。

将各材质的纹理颜色和透明度连接到指定组输入。

保留 UV 和纹理映射节点。

修改前保存原材质备份。

支持清理模式，仅保留主纹理和材质输出。

提供“返回 3D 视图 (Shift + F5)

提供独立的英文和简体中文安装包。

兼容性

最低版本：Blender 3.6

中英文版本均已在以下版本中通过自动化功能测试：

Blender 3.6

Blender 4.2

Blender 4.5 LTS

Blender 5.1

目标兼容范围为 Blender 3.6–5.2。Blender 5.2 尚未验证，也并非所有中间版本都经过测试。测试在后台模式下完成，不等同于完整的人工界面检查。

安装方法

下载 ZH_CN 中文安装包，或 EN 英文安装包。

打开“编辑 → 偏好设置 → 插件”。

选择“从磁盘安装”；旧版本中通常显示为“安装”。

选择 ZIP 文件并启用插件。

在 3D 视图或着色器编辑器中按 N 打开侧栏。

打开“材质替换器”标签。

只需安装一个语言版本。两个安装包使用相同的插件模块。

升级或切换语言时，请先禁用插件，再安装所需 ZIP，保存工作后重启 Blender，最后重新启用插件。

使用方法

选择需要修改的模型。

建议先选择“当前材质”测试效果；批量处理时选择“所选物体”。

将操作设为“使用节点组替换”。

点击“创建节点组”，然后点击“编辑节点组”；也可以直接选择已有节点组。

在组内制作着色器：

使用“基础颜色”输入接收原纹理颜色。

使用“透明度”输入接收原纹理 Alpha。

将最终着色器连接到组的“着色器”输出。

检查侧栏中的连接设置：

纹理颜色 → 组输入：选择接收纹理颜色的输入。

纹理透明度 → 组输入：选择接收纹理透明度的输入。

材质表面 ← 组输出：选择连接到材质输出“表面”的着色器输出。

如需保留原材质，请开启“保存材质备份”。

点击“应用到材质”，核对数量后确认。

替换后的结构为：

原始图像纹理 → 共享着色器节点组 → 材质输出

之后编辑共享节点组，会同步更新所有使用它的材质。点击 (Shift + F5) 返回 3D 视图

清理模式

“仅保留纹理和材质输出”会删除原有着色器结构，只留下主图像纹理和材质输出。

这两个节点不会自动连接。清理后需要添加着色器，或应用替换节点组，才能正常渲染。

开启“保留纹理映射”时，还会保留主纹理上游的映射节点。如果只想保留纹理和输出两个节点，请关闭该选项。

备份与恢复

开启“保存材质备份”后，插件会在修改前复制原材质，并添加 [材质备份] 后缀。

恢复时，选择对应材质槽，再从材质下拉列表中选择备份材质。请保存 .blend 文件，以保留这些备份。

每次应用都会创建新的备份。备份仍与原材质共享图像和节点组数据，并不是所有资源的独立副本。

也可以在操作后立即按 Ctrl Z 撤销。

注意事项与限制

主纹理由插件自动识别，复杂导入材质可能出现识别偏差。

不会提取嵌套节点组内部的图像。

法线贴图、球面贴图、额外纹理及旧着色效果不会自动转移到替换节点组中。

“跳过没有图像纹理的材质”默认开启。

修改共享材质会影响所有使用它的物体，包括未选择的物体。如需隔离，请先将材质设为单用户。

只读链接材质会被跳过。

原有材质透明设置保持不变；仅连接 Alpha 不一定能启用透明效果。



