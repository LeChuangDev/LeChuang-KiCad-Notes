# ERC 检查与网表导出

## ERC 检查
- 启动：`Inspect → Electrical Rules Checker`
- 检查内容：
  - 未连接引脚
  - 输入引脚未被驱动
  - 电源输入未被驱动
  - 标签冲突
  - 导线未连接
  - 总线连接错误
  - 符号未批注
  - 隐藏电源引脚

## 常见 ERC 错误及解决
| 错误 | 原因 | 解决方法 |
|------|------|----------|
| Input Power pin not driven | 电源网络没有输出电源引脚驱动 | 添加 PWR_FLAG 符号 |
| Pin not connected | 引脚未连接 | 连接引脚或添加 No Connection 标志 |
| Label not connected | 标签未连接到任何对象 | 检查标签位置 |
| Global label only appears once | 全局标签只出现一次 | 检查是否需要全局标签 |
| Duplicate reference designators | 位号重复 | 重新批注 |

## PWR_FLAG
- 在 `power` 库中
- 用于告诉 ERC 某个网络实际由电源驱动
- 常用于 VCC、GND 等网络
- 也可连接任何输出电源引脚到网络

## 网表导出
- `File → Export → Netlist`
- 支持格式：KiCad、OrCAD PCB2、Allegro、PADS、CADSTAR、SPICE、SPICE Model
- 推荐使用 `Tools → Update PCB from Schematic` 直接同步到 PCB

## BOM 导出
- `Tools → Generate Bill of Materials`
- 可配置字段、分组、排序、格式
- 支持 CSV、TSV 等格式
- 可使用虚拟字段：`${QUANTITY}`、`${ITEM_NUMBER}` 等
- 支持排除 DNP 和 Exclude from BOM 的元件

## 设计变体
- 在原理图中定义变体（Design Variants）
- 每个变体可覆盖字段值、DNP 状态、排除标志
- 支持命令行导出变体输出

#tool/kicad #domain/hardware