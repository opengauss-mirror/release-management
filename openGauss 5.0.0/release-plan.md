# Version Info
openGauss 5.0.0是规划在2023年3月30日发布的LTS版本，面向openGauss的场景化、工具链和兼容性场景，提供更多新特性和功能，给开发者和用户带来全新的体验，服务更多的领域和更多的用户。<br>

5.0.0版本整体开发周期为2022年10月8日至2023年3月30日，实际开发过程按以下两个阶段版本进行需求方案设计、开发与测试验收。<br>
阶段1：2022年10月8日至2022年12月30日； <br>
阶段2：2023年1月1日至2023年3月30日。 <br>

# Release Plan


|Stage  name             | Begin time  | End time   | Days | Note                                      |
| ---------------------- | ----------- | ---------- | ---- | ----------------------------------------------------------|
| 阶段1需求方案设计        | 2022/10/8  | 2022/10/30  | 23   | 阶段1交付需求方案设计（各SIG自行完成需求方案设计评审）   |
| 阶段1需求开发           | 2022/11/1  | 2022/11/30  | 30   | 阶段1需求完成开发和自验证，代码提交合入master    |
| 阶段1需求验收           | 2022/12/1  | 2022/12/7  | 7    | 阶段1需求测试验收    |
| 第一轮集成测试          | 2022/12/8 | 2022/12/14  | 7    | 版本集成测试，管控代码合入，原则上只允许bug fix                         |
| 第二轮集成测试          | 2022/12/15 | 2022/12/21  | 7    | 回归测试，管控代码合入，原则上只允许bug fix                            |
| 第三轮集成测试          | 2022/12/22 | 2022/12/28  | 7    | 回归测试，管控代码合入，原则上只允许bug fix                          |
| beta局点问题修复        | 2023/1/1  | 2023/2/27  | 58   | POC项目反馈问题修复（管控代码合入，原则上只允许bug fix）  |
| 第一轮集成测试          | 2023/2/28 | 2023/3/6   | 7    | 版本全量集成测试，管控代码合入，原则上只允许bug fix                   |
| 第二轮集成测试          | 2023/3/7 | 2022/3/13   | 7    | 版本回归测试，管控代码合入，原则上只允许bug fix                        |
| 第三轮集成测试          | 2023/3/14 | 2023/3/20  | 7    | 版本回归测试，管控代码合入，原则上只允许bug fix    |
| 预留buffer             | 2023/3/21  | 2023/3/26   | 6    |预留buffer解决突发问题       |
| 发布准备测试           | 2023/3/27  | 2023/3/29  | 3     | 版本发布测试        |
| Release               | 2023/3/30 | 2023/3/30   | 1    | 版本发布                                         |


# 代码合入说明
创新版本代码继承master分支 <br>
// 新特性代码请及时合入版本&自验证，跟随整体计划转测试


# Feature list
openGauss 5.0.0 Release版本发布的关键需求列表如下： <br>

|no|feature|status|sig|owner|
|:------|:-------|:-------|:-------|:-------|
|      |集成openLookeng，提供集群AP能力   |Accepted| Plugin       |        |
|      |CM管理ShardingSphere Proxy和注册中心，支持异常情况重新拉起 |Accepted| CM       |        |
|      |轻量化版本支持发布订阅功能   |Accepted| StorageEngine| |
|      |行存表压缩能力增强（高效压缩算法） |Accepted|    StorageEngine    |        |
|      |发布订阅能力增强，支持基础数据同步和备份恢复  |Accepted| SQLEngine       |        |
|      |支持基于主备双集群流式复制的异地容灾方案    |Accepted| StorageEngine|        |
|      |主机支持记录满足多数派日志的LSN，gs_ctl build支持拒绝目标LSN比此LSN要小的增量build    |Accepted|StorageEngine|        |
|      |CM开放状态查询和推送能力，支持用户应用/中间件感知当前主备角色    |Accepted|CM       |        |
|      |CM支持用户自定义组件监控和管理    |Accepted|CM       |        |
|      |DCF策略化多数派   |Accepted|DCF    |        |
|      |postgresql_fdw执行性能提升，支持聚合和条件下推到远端执行功能   |Accepted|Plugin   |        |
|      |基础算子性能提升  |Accepted|SQLEngine  |        |
|      |DBMind自治运维平台  |Accepted|AI  |        |
|      |智能优化器  |Accepted|AI  |        |
|      |支持细粒度Any权限增强 |Accepted|SecurityTechnology  |        |
|      |MySQL全量迁移性能提升 |Accepted|Tools  |        |
|      |支持MySQL增量迁移 |Accepted|Tools  |        |
|      |支持数据全量&增量校验 |Accepted|Tools  |        |
|      |数据类型兼容 |Accepted|SQLEngine  |        |
|      |系统函数兼容 |Accepted|SQLEngine  |        |
|      |DDL兼容 |Accepted|SQLEngine  |        |
|      |DML兼容 |Accepted|SQLEngine  |        |
|      |PL/SQL兼容 |Accepted|SQLEngine  |        |
|      |SHOW语法兼容|Accepted|SQLEngine  |        |
|      |其他语法兼容|Accepted|SQLEngine  |        |


现启动版本需求/特性收集，欢迎各sig maintainer和社区开发者们积极反馈和交流。<br>
状态说明：Discussion(方案讨论，需求未接受)、 Developing(开发中)、 Testing(测试中)、 Accepted(已验收) <br>
<br>

# 需求/特性反馈基本流程 <br />
1、开发者/sig在本贴的表格中填写要合入5.0.0的需求/特性，并同时填写需求issue及链接     <br>
2、申请特性在TC例会进行评审，评审通过后在release management sig例会进行详细交付计划制定与评审
<br><br>