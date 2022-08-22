# Version Info
openGauss 3.1.0是规划在2022年9月30日发布的创新版本，面向openGauss的场景化、工具链和兼容性场景，提供更多新特性和功能，给开发者和用户带来全新的体验，服务更多的领域和更多的用户。<br>

3.1.0版本整体开发周期为2022年4月1日至2022年9月30日，实际开发过程按以下两个阶段版本进行需求方案设计、开发与测试验收。<br>
阶段1：2022年4月1日至2022年6月30日； <br>
阶段2：2022年7月1日至2022年9月30日。 <br>

# Release Plan


|Stage  name             | Begin time  | End time   | Days | Note                                      |
| ---------------------- | ----------- | ---------- | ---- | ----------------------------------------------------------|
| 阶段1需求方案设计        | 2022/4/1  | 2022/4/30  | 30   | 阶段1交付需求方案设计（各SIG自行完成需求方案设计评审）   |
| 阶段1需求开发           | 2022/4/15  | 2022/6/8  | 53   | 阶段1需求完成开发和自验证，代码提交合入master    |
| 阶段1需求验收           | 2022/6/9  | 2022/6/15  | 7    | 阶段1需求测试验收    |
| 第一轮集成测试          | 2022/6/16 | 2022/6/20  | 5    | 版本集成测试，管控代码合入，原则上只允许bug fix                         |
| 第二轮集成测试          | 2022/6/21 | 2022/6/25  | 5    | 回归测试，管控代码合入，原则上只允许bug fix                            |
| 第三轮集成测试          | 2022/6/26 | 2022/6/30  | 5    | 回归测试，管控代码合入，原则上只允许bug fix                          |
| 阶段2需求方案设计       | 2022/7/1  | 2022/7/15  | 15   | 阶段2交付需求方案设计（各SIG自行完成需求方案设计评审）  |
| 阶段2需求开发           | 2022/7/16  | 2022/8/23 | 38   | 阶段2需求完成开发和自验证，代码提交合入master    |
| 阶段2需求验收           | 2022/8/24  | 2022/8/30 | 7    | 阶段2需求测试验收    |
| 第一轮集成测试          | 2022/8/31 | 2022/9/6   | 7    | 版本全量集成测试，管控代码合入，原则上只允许bug fix                   |
| 第二轮集成测试          | 2022/9/7 | 2022/9/13   | 7    | 版本回归测试，管控代码合入，原则上只允许bug fix                        |
| 第三轮集成测试          | 2022/9/14 | 2022/9/20  | 7    | 版本回归测试，管控代码合入，原则上只允许bug fix    |
| 预留buffer             | 2022/9/21  | 2022/9/26   | 6    |预留buffer解决突发问题       |
| 发布准备测试           | 2022/9/27  | 2022/9/29   | 3     | 版本发布测试        |
| Release               | 2022/9/30 | 2022/9/30   | 1    | 版本发布                                         |


# 代码合入说明
创新版本代码继承master分支 <br>
// 新特性代码请及时合入版本&自验证，跟随整体计划转测试


# Feature list
openGauss 3.1.0 Release版本发布的关键需求列表如下： <br>

|no|feature|status|sig|owner|
|:------|:-------|:-------|:-------|:-------|
|[I5NJPB](https://gitee.com/opengauss/release-management/issues/I5NJPB)|支持基于共享存储、共享内存的资源池化架构，满足实时一致性的一写多读|Developing| StorageEngine|        |
|      |集成openLookeng，提供集群AP能力   |Developing| Plugin       |        |
|      |CM管理ShardingSphere Proxy和注册中心，支持异常情况重新拉起 |Developing| CM       |        |
|      |轻量化版本支持发布订阅功能   |Developing| StorageEngine| |
|      |行存表压缩能力增强（高效压缩算法） |Developing|    StorageEngine    |        |
|      |发布订阅能力增强，支持基础数据同步和备份恢复  |Developing| SQLEngine       |        |
|      |支持基于主备双集群流式复制的异地容灾方案    |Developing| StorageEngine|        |
|      |主机支持记录满足多数派日志的LSN，gs_ctl build支持拒绝目标LSN比此LSN要小的增量build    |Developing|StorageEngine|        |
|      |CM开放状态查询和推送能力，支持用户应用/中间件感知当前主备角色    |Developing|CM       |        |
|      |CM支持用户自定义组件监控和管理    |Developing|CM       |        |
|      |DCF策略化多数派   |Developing|DCF    |        |
|      |postgresql_fdw执行性能提升，支持聚合和条件下推到远端执行功能   |Developing|Plugin   |        |
|      |基础算子性能提升  |Developing|SQLEngine  |        |
|      |DBMind自治运维平台  |Developing|AI  |        |
|      |智能优化器  |Developing|AI  |        |
|      |支持细粒度Any权限增强 |Developing|SecurityTechnology  |        |
|      |MySQL全量迁移性能提升 |Developing|Tools  |        |
|      |支持MySQL增量迁移 |Developing|Tools  |        |
|      |支持数据全量&增量校验 |Developing|Tools  |        |
|      |数据类型兼容 |Developing|SQLEngine  |        |
|      |系统函数兼容 |Developing|SQLEngine  |        |
|      |DDL兼容 |Developing|SQLEngine  |        |
|      |DML兼容 |Developing|SQLEngine  |        |
|      |PL/SQL兼容 |Developing|SQLEngine  |        |
|      |SHOW语法兼容|Developing|SQLEngine  |        |
|      |其他语法兼容|Developing|SQLEngine  |        |


现启动版本需求/特性收集，欢迎各sig maintainer和社区开发者们积极反馈和交流。<br>
状态说明：Discussion(方案讨论，需求未接受)、 Developing(开发中)、 Testing(测试中)、 Accepted(已验收) <br>
<br>

# 需求/特性反馈基本流程 <br />
1、开发者/sig在本贴的表格中填写要合入3.1.0的需求/特性，并同时填写需求issue及链接     <br>
2、申请特性在TC例会进行评审，评审通过后在release management sig例会进行详细交付计划制定与评审
<br><br>