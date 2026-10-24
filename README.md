# JiuHu Cursor

一只旋转的九尾狐娘，做成 Windows 11 的动画光标。

![preview](preview.gif)

## 包含

17 个标准光标角色，全部使用同一段 27 帧旋转动画：

`Normal` `Help` `Working` `Busy` `Precision` `Text` `HandWriting` `Unavailable` `Vertical` `Horizontal` `Diagonal1` `Diagonal2` `Move` `Alternate` `Link` `Pin` `Person`

## 特性

- **四档尺寸**：32 / 48 / 64 / 128，系统按当前光标大小自动选择
- **热点在左上角**（小方块中心）：动画向鼠标右下方展开，不遮挡瞄准位置
- **27 帧 / 100 ms 一帧**：2.7 秒转完一圈，无限循环
- **像素级清晰**：从 720×720 源动画逐帧重采样，深色背景下有白描边轮廓

## 安装

### 方式 A：INF 安装（推荐）

右键 `Install.inf` → **安装**。需要管理员权限，文件会装到 `C:\Windows\Cursors\JiuHu`。

装完后打开「设置 → 辅助功能 → 鼠标指针和触控 → 其他鼠标指针」，在方案列表里选 **JiuHu**。

### 方式 B：手动

1. 把 17 个 `.ani` 复制到 `C:\Windows\Cursors\JiuHu\`
2. 打开「设置 → 辅助功能 → 鼠标指针和触控 → 其他鼠标指针 → 指针选项卡」
3. 在「自定义」列表里逐个角色点「浏览」，选择对应的 `.ani`，最后「应用」

## 卸载

「设置 → 鼠标指针」里选回「Windows 默认」方案，再删掉 `C:\Windows\Cursors\JiuHu` 即可。

## 技术细节

| 项目 | 值 |
|---|---|
| 格式 | RIFF / ACON 动画光标（`.ani`），每帧内嵌 32bpp BMP |
| 尺寸 | 每帧包含 32 / 48 / 64 / 128 四个尺寸 |
| 帧数 | 27 帧，`anih` JifRate = 6（约 100 ms/帧） |
| 热点 | 每档均为光标图案左上角小方块的中心 |
| 生成 | Python + Pillow，逐帧缩放并对透明边缘做补色处理 |

## 素材与致谢

- 角色动画：`PS2.gif`（720×720，27 帧）
- 安装模板：参考 Firefly Animated B 的 `Install.inf` 结构

## 许可

角色动画素材的版权归原作者所有，本仓库仅作个人使用与学习分发。
如需商用或再分发，请先确认素材来源的授权情况。
