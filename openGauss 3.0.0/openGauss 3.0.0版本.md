![avatar](https://gitee.com/opengauss/QA/raw/master/images/openGauss.png)

版权所有 © 2021 openGauss社区 您对“本文档”的复制、使用、修改及分发受知识共享(Creative Commons)署名—相同方式共享4.0国际公共许可协议(以下简称“CC BY-SA 4.0”)的约束。为了方便用户理解，您可以通过访问[https://creativecommons.org/licenses/by-sa/4.0/](https://gitee.com/link?target=https%3A%2F%2Fcreativecommons.org%2Flicenses%2Fby-sa%2F4.0%2F) 了解CC BY-SA 4.0的概要 (但不是替代)。CC BY-SA 4.0的完整协议内容您可以访问如下网址获取：[https://creativecommons.org/licenses/by-sa/4.0/legalcode>。](https://gitee.com/link?target=https%3A%2F%2Fcreativecommons.org%2Flicenses%2Fby-sa%2F4.0%2Flegalcode%3E%E3%80%82)

# 概述

openGauss是一款全面友好开放，携手伙伴共同打造的企业级开源关系型数据库。openGauss提供面向多核架构的极致性能、全链路的业务、数据安全、基于AI的调优和高效运维的能力。openGauss具有高性能、高可靠、高安全和易运维等特性，深度融合华为在数据库领域多年的研发经验，结合企业级场景需求，持续构建竞争力特性。

本文主要描述了openGauss 3.0.0 Release版本策略，按照社区开发模式进行运作，由release-manager来u指定以及指导openGauss 3.0.0版本策略的执行。

## 版本背景

openGauss 3.0.0 Release版本是openGauss第二个长期支持版本（LTS），维护周期为3.5年，本次发布的重大特性有：

1. 【openGauss 3.0.0 LTS】CM集群管理开源
2. 【openGauss 3.0.0 LTS】openGauss分布式解决方案
3. 【openGauss 3.0.0 LTS】openGauss支持行表、索引压缩
4. 【openGauss 3.0.0 LTS】openGauss支持发布订阅的多地多活
5. 【openGauss 3.0.0 LTS】Data Studio开源
6. 【openGauss 3.0.0 LTS】支持小型化部署，空载内存底噪<250M，安装包<20M
7. 【openGauss 3.0.0 LTS】支持当前会话统计中加入归一化SQL处理，提升慢SQL历史信息诊断
9. 【openGauss 3.0.0 LTS】openGauss支持5220鲲鹏服务器达成100w tpmC
10. 【openGauss 3.0.0 LTS】openGauss支持Global system cache

## 需求范围

openGauss 3.0.0 Release版本发布的需求列表如下：

| no   | feature                                                      | status   | sig           | owner |
| ---- | ------------------------------------------------------------ | -------- | ------------- | ----- |
| 1    | 【openGauss 3.0.0 LTS】CM集群管理开源                        | Accepted | Tools         |       |
| 2    | 【openGauss 3.0.0 LTS】openGauss分布式解决方案               | Accepted | Tools         |       |
| 3    | 【openGauss 3.0.0 LTS】openGauss支持行表、索引压缩           | Accepted | StorageEngine |       |
| 4    | 【openGauss 3.0.0 LTS】openGauss支持发布订阅的多地多活       | Accepted | StorageEngine |       |
| 5    | 【openGauss 3.0.0 LTS】Data Studio开源                       | Accepted | Tools         |       |
| 6    | 【openGauss 3.0.0 LTS】支持小型化部署，空载内存底噪<250M，安装包<20M | Accepted | StorageEngine |       |
| 7    | 【openGauss 3.0.0 LTS】支持当前会话统计中加入归一化SQL处理，提升慢SQL历史信息诊断 | Accepted | SQLEngine     |       |
| 8    | 【openGauss 3.0.0 LTS】openGauss支持5220鲲鹏服务器达成100w tpmC | Accepted | StorageEngine |       |
| 9    | 【openGauss 3.0.0 LTS】openGauss支持Global system cache      | Accepted | StorageEngine |       |

# 性能指标

性能指标除了关注关键性能指标不劣化外，还需要对新的性能指标（如kunpeng-5220 2P单机1H 100W）进行摸底和测试。利用benckmarksql等工具辅助完成性能测试。

| **指标大项** | **指标小项**                                                 | **指标值** | **说明**                              |
| ------------ | ------------------------------------------------------------ | ---------- | ------------------------------------- |
| TPCC         | 2P（Taishan 200 2280 6426）单节点 1H                         | 150万      | 与Release基线数据差异小于5%以内可接受 |
|              | 2P（Taishan 200 2280 6426）单节点 8H                         | 150万      | 与Release基线数据差异小于5%以内可接受 |
|              | 2P（Taishan 200 2280 6426）一主一备 1H                       | 120万      | 与Release基线数据差异小于5%以内可接受 |
|              | 4P（Taishan 200 2280 7260）单节点 1H                         | 230万      | 与Release基线数据差异小于5%以内可接受 |
|              | 2P（Taishan 200 2280 5220）单节点 1H                         | 100万      | 此即为Release基线数据                 |
|              | 分布式OLTP，TPCC线性度0.8，2P（Taishan 200 2280 6426）16节点 1H | 1000万     | 此即为Release基线数据                 |
| RTO          | 一主两同步备failover                                         | 10s        | 与Release基线数据差异小于5%以内可接受 |

# 兼容性指标

#### 升级兼容

| Domain     | 测试策略                                                     |
| ---------- | ------------------------------------------------------------ |
| 升级路径   | 1.升级路径<br>--支持openGauss 1.1.0升级到openGauss 3.0.0；<br/>--支持openGauss 2.0.0升级到openGauss 3.0.0；<br/>--支持openGauss 2.0.1升级到openGauss 3.0.0；<br/>--支持openGauss 2.1.0升级到openGauss 3.0.0；<br/>2.升级失败或者升级未提交，可以回滚到原版本<br>3.故障场景下，环境恢复后升级可以重入并升级成功 |
| 升级兼容性 | 关注升级后特性功能运行正常                                   |

#### 硬件兼容

| Domain       | 测试策略                                                     |
| ------------ | ------------------------------------------------------------ |
| 服务器兼容   | 继承已有测试能力，支持在X86（Intel(R) Xeon(R) Gold）/鲲鹏（Kunpeng 920）服务器上部署 |
| 存储设备兼容 | 继承已有测试能力，支持在本地盘、云盘上部署，支持在SAS，SATA，SSD部署 |

#### 软件兼容

| Domain       | 测试策略                                                     |
| ------------ | ------------------------------------------------------------ |
| 支持云化部署 | 继承已有测试能力，支持容器化部署                             |
| 操作系统兼容 | 继承已有测试能力，支持在X86+openEuler 20.03 LTS、X86+CentOS 7.6、ARM+麒麟V10和ARM+openEuler 20.03 LTS操作系统上部署 |

# 测试执行策略

openGauss 3.0.0 Release版本按照社区release-management团队既定的版本计划，共有8轮测试，按照社区研发模式，所有的需求在2022年2月20日前完成合入。

版本计划规划8轮测试，采取5（SDV：需求验证测试）+3（SIT ：集成验证以及专项测试）的测试方式，即5轮系统测试+3轮集成验证的策略。

### 测试计划

openGauss 3.0.0 Release版本按照社区开发模式进行运作，结合社区release-management团队指定的版本计划规划相应的测试活动。

| Stage name | Begin time | End time |
| :---- | :---- | :---- |
| Test round 1 | 2022-1-20 | 2022-1-26 |
| Test round 2 | 2022-1-27 | 2022-1-30 |
| Test round 3 | 2022-2-10  | 2022-2-16 |
| Test round 4 | 2022-2-17  | 2022-2-19 |
| Test round 5 | 2022-2-20 | 2022-2-27 |
| Test round 6 | 2022-2-28 | 2022-3-3 |
| Test round 7 | 2022-3-4 | 2022-3-9 |
| Test round 8 | 2022-3-10 | 2022-3-12 |
