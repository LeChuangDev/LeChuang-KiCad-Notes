# kicad-cli 命令速查

## 简介
`kicad-cli` 是 KiCad 的命令行工具，用于自动化操作。支持 `fp`、`jobset`、`pcb`、`sch`、`sym`、`version` 六个子命令。

## 基本用法
```bash
kicad-cli <子命令> <操作> [选项] <输入文件>
```
## 封装命令 (fp)

### 导出 SVG

bash

kicad-cli fp export svg [选项] <输入文件>

- `-o, --output`：输出目录
    
- `-l, --layers`：层列表
    
- `--fp, --footprint`：封装名称
    
- `--black-and-white`：黑白导出
    

### 升级封装库

bash

kicad-cli fp upgrade [选项] <输入文件>

- `-o, --output`：输出目录
    
- `--force`：强制重新保存
## PCB 命令 (pcb)

### DRC 检查

bash

kicad-cli pcb drc [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--format`：报告格式（report / json）
    
- `--all-track-errors`：报告所有布线错误
    
- `--schematic-parity`：检查原理图一致性
    
- `--severity-all`：报告所有违规
    
- `--exit-code-violations`：有违规时返回非零退出码
    

### 导出 Gerber

bash

kicad-cli pcb export gerbers [选项] <输入文件>

- `-o, --output`：输出目录
    
- `-l, --layers`：层列表
    
- `--no-x2`：禁用 X2 格式
    
- `--no-netlist`：不包含网表属性
    

### 导出钻孔文件

bash

kicad-cli pcb export drill [选项] <输入文件>

- `-o, --output`：输出目录
    
- `--format`：格式（excellon / gerber）
    
- `--drill-origin`：原点（absolute / plot）
    
- `--excellon-units`：单位（mm / in）
    

### 导出 3D 模型

bash

kicad-cli pcb export step [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--subst-models`：替换同名模型
    
- `--board-only`：仅导出板体
    
- `--include-tracks`：包含布线
    

### 导出位置文件

bash

kicad-cli pcb export pos [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--format`：格式（ascii / csv / gerber）
    
- `--units`：单位（in / mm）
    
- `--side`：面（front / back / both）
    

### 渲染 PCB

bash

kicad-cli pcb render [选项] <输入文件>

- `-o, --output`：输出文件（.png / .jpg）
    
- `--width`：宽度
    
- `--height`：高度
    
- `--side`：面（top / bottom / left / right / front / back）
    
- `--quality`：质量（basic / high / user）
    

## 原理图命令 (sch)

### ERC 检查

bash

kicad-cli sch erc [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--format`：报告格式（report / json）
    
- `--severity-all`：报告所有违规
    
- `--exit-code-violations`：有违规时返回非零退出码
    

### 导出 BOM

bash

kicad-cli sch export bom [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--fields`：字段列表
    
- `--group-by`：分组字段
    
- `--sort-field`：排序字段
    
- `--exclude-dnp`：排除 DNP 元件
    

### 导出 PDF

bash

kicad-cli sch export pdf [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--black-and-white`：黑白导出
    
- `--exclude-drawing-sheet`：不包含图框
    

### 导出网表

bash

kicad-cli sch export netlist [选项] <输入文件>

- `-o, --output`：输出文件
    
- `--format`：格式（kicadsexpr / kicadxml / cadstar / orcadpcb2 / spice 等）
    

### 导出 SVG

bash

kicad-cli sch export svg [选项] <输入文件>

- `-o, --output`：输出目录
    
- `--black-and-white`：黑白导出
    
- `--exclude-drawing-sheet`：不包含图框
    

## 符号命令 (sym)

### 导出 SVG

bash

kicad-cli sym export svg [选项] <输入文件>

- `-o, --output`：输出目录
    
- `--symbol`：符号名称
    
- `--black-and-white`：黑白导出
    

### 升级符号库

bash

kicad-cli sym upgrade [选项] <输入文件>

- `-o, --output`：输出文件或目录
    
- `--force`：强制重新保存
    

## 版本命令 (version)

bash

kicad-cli version [选项]

- `--format`：格式（plain / commit / about）
    

## 作业集命令 (jobset)

bash

kicad-cli jobset run [选项] <输入文件>

- `--stop-on-error`：出错时停止
    
- `-f, --file`：作业集文件
    
- `--output`：输出目标
    

## 常用示例

bash

# 导出 Gerber
kicad-cli pcb export gerbers -o gerbers/ board.kicad_pcb
# 导出钻孔文件
kicad-cli pcb export drill -o drill/ board.kicad_pcb
# 导出 STEP 模型
kicad-cli pcb export step -o board.step board.kicad_pcb
# 运行 DRC
kicad-cli pcb drc -o drc_report.txt board.kicad_pcb
# 导出 BOM
kicad-cli sch export bom -o bom.csv schematic.kicad_sch
# 导出 PDF
kicad-cli sch export pdf -o schematic.pdf schematic.kicad_sch
# 渲染 PCB
kicad-cli pcb render -o render.png --side top board.kicad_pcb

#tool/kicad #domain/pcb #cli