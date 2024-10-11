# FPGA PCIE GRAPHIC CARD Hardware Portion

此项目设计一以FPGA为核心的PCIE ADDIN卡，作图像处理硬件加速应用。此文档主要论述硬件方面相关内容，软件部分另有仓库详细介绍。

软件部分仓库：

> 引用示例

图片示例


# 前言

# 功能细节规划

# 主要元器件选型

* FPGA芯片选型
    * 位宽192bit，容量12GB
    * 位宽256bit，容量16GB
    * 位宽384bit，容量24GB
    * PCIE3.0X16，4bank高速串行信号（32Lane series signals）

在上述三种规格下，分别计算所需bank与io数量。

以256bit为例，每三个bank控制80bit即5个16bit的DDR，9个bank控制240bit，11个bank才能完成符合位宽的设计。所以192bit需要8个bank，256bit需要11个bank，384bit需要15个bank。

所需HPIO数量可有如下公式计算得出：bit_width / 8 * 3 + bit_width /80 * ctl_signal。所以192bit需要366个IO，256bit需要484个IO，384bit需要698个IO。

根据上述bank需求选择合适的FPGA芯片，初步选定为Virtex_UltraScale系列的***XCVU3P-2FFVC1517I***。

# 框图设计

## 系统框图

## 电源框图

# 上电时序设计

# 主板层叠设计与布局布线规划

# 原理图设计

# 印刷电路板设计

# 高速信号仿真

# 菲林文件整理

# BOM表整理

# 结语




