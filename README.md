# FPGA PCIE GRAPHIC CARD Hardware Portion

## 摘要

此项目设计一以FPGA为核心的PCIE ADDIN卡，作图像处理硬件加速应用。此文档主要论述硬件方面相关内容，软件部分另有仓库详细介绍。

## 目录



软件部分仓库：

> 引用示例

图片示例

## 1. 主要元器件选型

#### 1.1 FPGA选型
位宽192bit，容量12GB
位宽256bit，容量16GB
位宽384bit，容量24GB
PCIE3.0X16，4bank高速串行信号（32Lane series signals）

在上述三种规格下，分别计算所需bank与io数量。

以256bit为例，每三个bank控制80bit即5个16bit的DDR，9个bank控制240bit，11个bank才能完成符合位宽的设计。所以192bit需要8个bank，256bit需要11个bank，384bit需要15个bank。

所需 HPIO 数量可有如下公式计算得出：bit_width / 8 * 3 + bit_width /80 * ctl_signal。所以192bit需要366个IO，256bit需要484个IO，384bit 需要698个IO。

根据上述bank需求选择合适的FPGA芯片，初步选定为 Virtex_UltraScale 系列的***XCVU3P-2FFVC1517I***。

### 1.2 NOR_Flash选型

#### 1.2.1 容量选择

#### 1.2.2 配置时间计算

### 1.3  Clock_Buffer选型

#### 1.3.1 时钟需求

#### 1.3.2 系统时钟

#### 1.3.2 DDR时钟

#### 1.3.3 PCIE时钟

#### 1.3.4 QSFP时钟

#### 1.4  Power IC选型



## 2. 框图设计

### 2.1 系统框图

### 2.2 电源框图

### 2.3 上电时序图

### 2.4 功耗统计

## 3. 原理图设计

### 3.1 FPGA原理图设计

#### 3.1.1 FPGA基本配置



#### 3.1.2 FPGA电源设计

#### 3.1.3 FPGA DDR电路设计

#### 3.1.4 FPGA PCIE设计

#### 3.1.5 FPGA GTY设计

### 3.2 DDR电路设计

### 3.3 主板电源设计

### 3.4 PCIE接口设计

## 4. 主板层叠设计

## 5. 印刷电路板设计

## 6. 高速信号仿真与优化

## 7. 菲林文件整理

## 8. BOM表整理



## 结语
