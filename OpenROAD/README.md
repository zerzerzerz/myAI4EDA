# README
- [https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts)
- [https://openroad.readthedocs.io/en/latest/tutorials/FlowTutorial.html](https://openroad.readthedocs.io/en/latest/tutorials/FlowTutorial.html)

## OpenROAD简介
- OpenROAD是一个工具链（tool-chain），将各种EDA的开源工具串联起来，实现从[RTL](https://en.wikipedia.org/wiki/Register-transfer_level)-to-[GDS](https://en.wikipedia.org/wiki/GDSII)的自动化流程，如输入对应电路的硬件描述（VHDL，Verilog）已经对应的约束、工艺目标，它能够自动完成逻辑综合、布局、时钟树生成、布线等等各种流程
- OpenROAD将各个工具串联起来，如逻辑综合使用abc，global placement使用RePlAce，时序分析使用OpenSTA等等，具体的每个步骤由哪些工具实现可以参考[https://openroad.readthedocs.io/en/latest/main/README.html#run](https://openroad.readthedocs.io/en/latest/main/README.html#run)

## Table of Contents
- 本节将介绍OpenROAD的安装、使用、数据导出
- 设备环境
  - 本地机器，Windows 10
  - 远程服务器，Ubuntu-18.04，配备显示器
  - OpenROAD提供本地直接安装和通过Docker安装，因为安装时笔者在公司实习，mentor担心笔者将服务器搞崩，因此笔者选择Docker进行编译和安装