# BOM 表生成

## 生成步骤
1. `Tools → Generate Bill of Materials`
2. 在 `Edit` 选项卡中配置字段、分组、排序
3. 在 `Export` 选项卡中配置输出格式
4. 点击 `Export` 生成 BOM 文件

## BOM 内容
- 包含符号字段表中的所有字段
- 可通过 `Include` 复选框控制显示/隐藏
- 可通过 `Group By` 复选框控制分组
- 支持虚拟字段：`${QUANTITY}`、`${ITEM_NUMBER}`、`${SYMBOL_NAME}` 等

## 属性影响
- `Exclude from BOM`：元件不出现在 BOM 中
- `Do not populate (DNP)`：元件出现在 BOM 中，但标记为不装配
- `Exclude from board`：元件不出现在 PCB 中

## 输出格式
- CSV（逗号分隔）
- TSV（制表符分隔）
- 分号分隔
- 可自定义分隔符、引用分隔符、范围分隔符
- 可保留/删除制表符和换行符

## 预置
- 内置预置：`Grouped By Value`、`Grouped By Value and Footprint`、`Attributes`
- 可创建自定义预置
- 预置存储在工程中

## 变体 BOM
- 支持设计变体
- 每个变体可有不同的字段值和 DNP 状态
- 使用 `${VARIANT}` 变量生成不同文件名
- 命令行支持 `--variant` 参数

## 旧版 BOM 工具
- `Tools → Generate Legacy Bill of Materials`
- 使用外部脚本（Python、XSLT）
- 支持自定义脚本
- 可通过命令行参数 `%I`、`%O`、`%B`、`%P` 传递文件路径

#tool/kicad #domain/pcb