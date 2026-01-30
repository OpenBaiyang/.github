# OpenBaiyang介绍

本项目拟基于 Chisel 开发开源 DDR4 内存控制器，向香山开源生态体系提供可自主演进的、开源共享的高性能内存控制器 IP 及相关测试验证工具。

项目主要包括五部分内容：

1、开源高性能内存控制器 (Baiyang IP)

2、周期精准内存仿真器 

3、海量踪迹高速测试仪

4、开源高频信号校准器

5、精准内存子系统模拟器

---

## 重要说明：

本项目已迁移至 https://github.com/OpenXiangShan/YuQuan ，第一版 DDR4-Baiyang-V0.8 已于 2026 年 1 月 30 日发布，欢迎访问新链接。本链接不再更新。

### 一、Baiyang 

Baiyang是一种高性能内存控制器设计和实现方案。通过对地址映射、分流、系统缓存、调度、内存颗粒时序控制的功能划分和模块化处理，可实现自主演进。

当前版本 IP 支持：

* AXI4 总线接口协议

* DFI3.0 PHY总线接口协议
  
* DDR4-2400

OpenBaiyang的设计文档请参考本项目提供的[设计文档](https://github.com/OpenBaiyang/Baiyang/blob/main/Baiyang%20IP%E8%AE%BE%E8%AE%A1%E6%96%87%E6%A1%A3.docx)



### 二、周期精准内存仿真器

通过协议转换、跨时钟域信号处理、存储介质运行命令管理等方法，支持DFI PHY协议，支持多频点的模拟仿真，支持周期精准的访存时序，解决了两个问题：

* FPGA 平台缺少支持 DFI PHY 接口的 IP

* FPGA 平台验证存在CPU降频 SDRAM芯片不降频的“频率倒挂”现象，导致CPU 性能测试结果不准确

  

### 三、海量踪迹高速测试仪

通过数据注入、指令适配、数据比对等方法，支持基于丰富的真实负载Trace，持续长时间测试，易于发现和定位问题。旨在解决现有DDR4系统级测试过于依赖复杂香山处理器核的问题，具体地：

* CPU复杂负载故障难以定位和重放
  
* 采用内置测试模块，只能产生固定模式的负载

* 单核难以产生足够的负载，双核单片FPGA资源不够



### 四、开源高频信号校准器

编写了一套 C 程序源码，用于调整 FPGA 高频信号时序，当前版本适用于以下场景： 

* FPGA平台DDR4 SDRAM读写训练不通过报 error 的情况下，可用该程序调整 FPGA 高频信号时序，以完成内存读写训练。



### 五、精准内存子系统模拟器

旨在提供一款与 Baiyang RTL 结构对齐的模拟器，用于研究和探索 Baiyang IP 优化方案，拟支持DDR3 / DDR4。

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
