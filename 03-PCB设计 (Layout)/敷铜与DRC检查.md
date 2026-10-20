# 敷铜与 DRC 检查

## 敷铜 (Zones)
- 添加：按 `Ctrl + Shift + Z` 或点击右侧工具栏按钮
- 选择网络、层、间隙、最小宽度
- 焊盘连接方式：实心、热焊盘、无
- 热焊盘设置：间隙、辐条宽度
- 支持网格敷铜（用于柔性板等特殊应用）
- 支持圆角平滑
- 支持移除孤岛

## 敷铜优先级
- 在 Zone Manager 中调整优先级
- 高优先级敷铜先填充
- 低优先级敷铜避让高优先级敷铜

## 敷铜管理
- `Tools → Zone Manager`：查看、编辑、排序所有敷铜
- 支持按层、网络筛选
- 支持自动分配优先级
- 支持批量更新

## DRC 检查
- 启动：`Inspect → Design Rules Checker`
- 检查内容：
  - 短路、间隙违规
  - 线宽、环形圈、孔径违规
  - 外框重叠、外框缺失
  - 板框无效
  - 丝印重叠、丝印被阻焊裁剪
  - 未连接项、未布线项
  - 原理图与 PCB 不一致

## DRC 选项
- `Refill all zones before performing DRC`：执行前重新填充敷铜
- `Test for parity between PCB and schematic`：检查原理图与 PCB 一致性
- `Report all errors for each track`：报告每条布线的所有错误

## 违规处理
- 可排除单个违规
- 可忽略某类违规
- 可更改违规严重程度
- 可添加注释说明排除原因

## 间隙和约束解析
- `Inspect → Clearance Resolution`：查看两个对象之间的间隙规则
- `Inspect → Constraints Resolution`：查看对象适用的设计约束

## 常见 DRC 错误及解决
| 错误 | 原因 | 解决方法 |
|------|------|----------|
| Clearance violation | 间隙不足 | 调整布线或修改规则 |
| Track has unconnected end | 布线末端未连接 | 连接或删除 |
| Via is not connected | 过孔未连接 | 检查过孔位置 |
| Board edge clearance violation | 铜到板边间隙不足 | 调整位置或修改规则 |
| Courtyards overlap | 封装外框重叠 | 调整布局 |
| Silkscreen clipped by solder mask | 丝印被阻焊裁剪 | 调整丝印位置 |
| Missing connection | 未连接 | 布线连接 |
| Footprint doesn't match symbol | 封装不匹配 | 更新 PCB 或原理图 |

#tool/kicad #domain/pcb