# multi-OS-with-Job-Placement
## 项目梳理

核心技术问题：在使用multi-OS思路的HPC集群上，当前集群管理工具没有感知硬件资源信息和算力节点的调度优化策略，并结合应用特点以进行作业分发，使得算力节点无法发挥调度优势，造成HPC整体性能欠佳。

先验信息：应用层（资源需求、局部性、最长轮转时间），算力节点（OS调度策略，隔离配置）

解决思路：增强集群作业管理系统的扩展性、可定制性和灵活性，使其可以通过硬件资源管理权限的分离，让集群管理工具直接从节点内核处获得硬件资源的粗粒度先验信息，根据算力节点的调度策略，决定作业分发的数量和位置。

困难：内核级别上的整体先验信息。计算节点上不会部署先验信息；集群管理和算力节点的相互感知框架；挖掘应用特点，并针对性地设计集群级作业管理策略。

## related work

### Intel mOS

源代码：https://github.com/intel/mOS

论文：https://dl.acm.org/doi/10.1145/2612262.2612263

### Cluster Management

slurm：https://github.com/SchedMD/slurm

openpbs: https://openpbs.org

### benchmark

hpcg: https://github.com/hpcg-benchmark/hpcg

ccs-qcd: https://github.com/fiber-miniapp/ccs-qcd

### other paper

Multi-objective job placement in clusters: https://dl.acm.org/doi/10.1145/2807591.2807636

Exploring the Design Space of Combining Linux with Lightweight Kernels for Extreme Scale Computing: https://dl.acm.org/doi/10.1145/2768405.2768410

## 目前进展

2022.11.23： 整理了相关工作，完成了Intel mOS的虚拟机环境配置，使用HPCG benchmark进行了一些简单的测试来进行验证。
