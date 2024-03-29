# 每周纪要
## 2022.11.24

### 目前进展
完成了Intel mOS的相关论文调研和虚拟机上的环境搭建，使用HPCG作为benchmark进行了简单的测试。

阅读了slurm相关的一些文档，阅读了部分相关代码（主要是关于任务分发的部分）。

阅读了论文：Multi-Objective Job Placement in Clusters[](https://dl.acm.org/doi/10.1145/2807591.2807636)。本文主要介绍了在集群上面向多种优化目标（能耗与性能）进行任务分发的一种新的思路，即通过可视化以及变量的线性规划来进行。对于本项目关于任务分发方面有着一定参考价值。

### 问题

虚拟机环境搭建时有一定困难，由于核的数量配置较低因此实际的性能提升不够明显。而且mOS的依赖工具也比较多，还需要进一步完善和补充。

### 解决方案

安装mOS的依赖，同时虚拟机仅用于正确性的验证，而不用于实际的性能验证，后续可以使用物理机服务器来进行相应的测试。

### 下周计划

1. 基于mOS环境下尝试配置slurm，如果有时间运行HPCG进行测试，研究集群管理工具的任务分发功能在multi-kernel上的效果。
2. 继续调研阅读关于集群任务分发的论文。
3. 整理文献，制作开题PPT

## 2022.12.1

### 目前进展

在虚拟机上尝试配置了slurm，但还没有完全跑起来（主要是分布式环境还没有搭建好）。

阅读了论文：Elasecutor: Elastic Executor Scheduling in Data Analytics Systems: https://dl.acm.org/doi/10.1145/3267809.3267818 这篇文章主要介绍了在云服务器上基于硬件运行状态进行动态的执行器调度的一种弹性调度器。它对于任务所占用的硬件资源分析和信息的收集对于本项目有一定的参考价值。

阅读了论文：COBRA: Toward Provably Efficient Semi-Clairvoyant Scheduling in Data Analytics Systems: https://dl.acm.org/doi/10.1109/INFOCOM.2018.8485981 这篇文章介绍了一种“半千里眼”式的调度算法，根据不完全的任务先验信息进行动态的调度。这种设计思路对于本项目关于如何使用粗粒度的先验信息进行任务分发有一定的参考价值。

制作开题报告PPT。

### 问题

虚拟机的分布式环境搭建比较困难，因此部署slurm环境的过程比预期要更加困难。

### 解决方案

如果可能的话直接使用云服务器来进行slurm和mOS的结合实验，也能获得更好的性能数据。可以考虑去找一下网上的一些云服务器租赁。

### 下周计划

1. 继续搭建分布式的虚拟机环境，尝试配置slurm。
2. 继续调研阅读关于集群任务分发的论文，具体可以尝试从云计算领域收集。
3. 整理文献作为reading list。

## 2022.12.8

### 目前进展

在虚拟机上成功配置了slurm，基于分布式环境（两台虚拟机的局域网连接）进行了测试。

阅读了论文：SPIN: BSP Job Scheduling With Placement-Sensitive Execution: https://dl.acm.org/doi/pdf/10.1109/TNET.2021.3087221 这篇文章介绍了在面对特定的HPC任务（BSP）时，如何通过分发调度来解决其运行时的同步、局部性、先验信息缺失等问题，因此对于本项目如何基于较少的任务先验信息进行分发决策有比较重要的参考价值。

调整了开题报告PPT，主要将相关论文部分转移到了最后进行一笔带过，增加了对于课题技术问题以及个人工作目标的分析。

### 问题

mOS和slurm不是很好一起配置，尤其是在虚拟环境上。

### 解决方案

如果可能的话直接使用云服务器来进行slurm和mOS的结合实验，也能获得更好的性能数据。可以考虑去找一下网上的一些云服务器租赁。目前考虑先进行调研工作，后续直接使用华为提供的环境进行测试。

### 下周计划

1. 继续调研阅读关于集群任务分发的论文，具体可以尝试从云计算、高性能计算领域收集。
2. 整理文献作为reading list。
3. 完善开题PPT。


## 2022.12.15

### 目前进展

阅读了论文：Morpheus: Towards Automated SLOs for Enterprise Clusters: https://www.microsoft.com/en-us/research/publication/morpheus-towards-automated-slos-enterprise-clusters/ 这篇文章介绍了一款针对周期性作业，基于历史运行信息分析来自动的设置运行的目标（一般是完成时间），而避免使用用户提供的信息，从而帮助提高集群的资源利用率、降低违背SLO的频率。

研究了slurmctld和sbatch的部分代码，准备尝试修改其中关于任务分发的部分代码来查看效果。

整理了reading list，和校外导师讨论了一下调研方面的问题

### 问题

调研思路上，在multi-kernel本身的介绍有一些欠缺，不能只围绕mOS本身，需要一些更早的文章。另一方面，毕设开题的报告中需要一些更多集群领域的常见思路来帮助理解项目的设计，可以使用一些云计算领域的弹性调度思路的文章来引入。

### 解决方案

对于缺少调研的部分进行弥补，有些文献可以用收集和略读为主。

### 下周计划

1. 继续调研阅读关于集群任务分发的论文，具体可以尝试从云计算、高性能计算领域收集。
2. 完善开题PPT。
3. 修改slurm，通过实验测试一下对代码的理解是否正确。


## 2022.12.22

本周感染新冠，休息一周。主要是完善了虚拟机slurm环境的搭建。

## 2022.12.29

### 目前进展

完成了虚拟机分布式环境的计算搭建，修改了部分slurm中的设计调度的代码，验证了对于slurm代码理解的正确性，以及slurm在处理分发策略上的一些局限性。
阅读了一篇关于周期类任务运行时状态预测的论文。

### 下周计划

1. 准备好开题PPT，系统归纳Reading List。
2. 准备期末考试
3. 尝试在slurm环境中部署mOS

## 2023.1.6

### 目前进展

通过实验验证了对于slurm.conf以及代码中实现的任务分发策略的优先级，从而确保后续实现中可以在兼容slurm原有的功能下进行新的分发算法设计。
阅读了slurm的srun功能相关代码，与批处理任务分发的sbatch进行了对比，后续实现算法时需要对这两部分进行区分。
完成了开题PPT，与校外导师交流完善了Reading List，确认了后续调研和分析的方向主要围绕mOS的特征进行。

### 下周计划

下周将会前往校外实习，因此可以使用到一些实机环境，因此计划主要完善实机上的环境配置，如有时间则尝试进行实验的性能测试。

## 2023.2.23

### 目前进展

验证了问题的存在性：HPCG下slurm+mOS的性能与mOS对比linux的加速比有明显退化，1.03 - 1.07
分析了可能的原因，进行了代码设计。

### 下周计划

完成计算节点上的内核信息感知脚本，先不考虑和slurm的耦合性。

## 2023.3.2

### 目前进展

使用独立的脚本完成了对于mOS的lwk特性的监控，包括lwkcpus、lwkmem。
尝试通过硬编码方式来实现slurm对mOS的适配。

### 下周计划

完善信息感知脚本，希望利用linux内核自带的noise tracer来跟踪一些OS抖动信息。
完善slurm与mOS的适配。

## 2023.3.9

### 目前进展

更新了信息感知脚本，使得脚本可以感知OS抖动的信息。
通过硬编码方式初步实现了slurm对mOS的适配，在单线程上已经可以弥补slurm带来的性能损失（使用HPCG进行测试）。

### 下周计划

尝试引入多线程的任务提交，进一步测试slurm与mOS的适配性。
