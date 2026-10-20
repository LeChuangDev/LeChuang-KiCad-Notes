# Gerber 导出

## 导出步骤
1. `File → Fabrication Outputs → Gerbers (.gbr)`
2. 选择输出目录
3. 勾选需要的层：
   - 铜层（`.Cu`）
   - 板框（`Edge.Cuts`）
   - 阻焊（`.Mask`）
   - 丝印（`.Silkscreen`）
   - 锡膏（`.Paste`，可选）
4. 配置 Gerber 选项
5. 点击 `Plot` 生成 Gerber 文件
6. 点击 `Generate Drill Files` 生成钻孔文件

## Gerber 选项
| 选项 | 说明 |
|------|------|
| Use Protel filename extensions | 使用 Protel 扩展名（`.GTL`、`.GBL` 等） |
| Generate Gerber job file | 生成 `.gbrjob` 文件，包含层叠信息 |
| Coordinate format | 坐标格式，建议咨询制造商 |
| Use extended X2 format | 使用 X2 格式，包含网络信息 |
| Include netlist attributes | 包含网络属性 |
| Disable aperture macros | 禁用光圈宏，仅用于兼容旧软件 |

## 钻孔文件
- `File → Fabrication Outputs → Drill Files (.drl)`
- 格式：Excellon（默认）或 Gerber X2
- 选项：
  - Mirror Y axis：镜像 Y 轴
  - Minimal header：最小化头文件
  - PTH and NPTH in single file：合并镀通孔和非镀通孔
  - Generate map：生成钻孔图
  - Origin：坐标原点
  - Drill units：单位
  - Zeros：零格式

## 其他制造输出
| 格式 | 说明 |
|------|------|
| IPC-2581 | XML 格式，包含制造和装配数据 |
| ODB++ | 数据库格式，包含完整制造数据 |
| 位置文件 | 元件中心位置和方向，用于贴片机 |
| IPC-D-356 | 网表格式，用于裸板测试 |

## 输出检查
- 使用 Gerber 查看器预览输出文件
- 检查层对齐、线宽、孔径、间距
- 运行 DRC 确保无违规
- 确保敷铜已填充

#tool/kicad #domain/pcb