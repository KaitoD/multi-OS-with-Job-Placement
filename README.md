# multi-OS-with-Job-Placement
## 项目梳理
核心技术问题：在使用multi-OS思路的HPC集群上，集群管理工具无法获得硬件资源信息以进行分发。

先验信息：资源需求、局部性、最长轮转时间

解决思路：通过硬件资源管理权限的分离，让集群管理工具直接从节点内核处获得硬件资源的粗粒度先验信息

困难：内核级别上的整体先验信息。计算节点上不会部署先验信息，需要增加额外的获取机制。

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
