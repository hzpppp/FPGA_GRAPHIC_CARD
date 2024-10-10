# FPGA_GRAPHIC_CARD

# 主要元器件选型
* FPGA芯片选型
    * 位宽192bit，容量12GB
    * 位宽256bit，容量16GB
    * 位宽384bit，容量24GB
    * PCIE3.0X16，4bank高速串行信号

在上述三种规格下，分别计算所需bank与io数量。

以256bit为例，每三个bank控制80bit即5个16bit的DDR，9个bank控制240bit，11个bank才能完成符合位宽的设计。所以192bit需要8个bank，256bit需要11个bank，384bit需要15个bank。

所需HPIO数量可有如下公式计算得出：bit_width / 8 * 3 + bit_width /80 * ctl_signal。所以192bit需要366个IO，256bit需要484个IO，384bit需要698个IO。

根据上述bank需求选择合适的FPGA芯片，待选芯片有XCVU3P-2FFVC1517I、
