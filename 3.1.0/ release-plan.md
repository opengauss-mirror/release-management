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
| 第三轮集成测试          | 2022/6/25 | 2022/6/30  | 5    | 回归测试，管控代码合入，原则上只允许bug fix                          |
| 阶段2需求方案设计       | 2022/7/1  | 2022/7/25   | 25   | 阶段2交付需求方案设计（各SIG自行完成需求方案设计评审）  |
| 阶段2需求开发           | 2022/7/15  | 2022/8/23  | 37   | 阶段2需求完成开发和自验证，代码提交合入master    |
| 阶段2需求验收           | 2022/8/24  | 2022/8/30  | 7    | 阶段2需求测试验收    |
| 第四轮集成测试          | 2022/9/1 | 2022/9/5    | 5    | 版本全量集成测试，管控代码合入，原则上只允许bug fix                   |
| 第五轮集成测试          | 2022/9/6 | 2022/9/10   | 5    | 版本回归测试，管控代码合入，原则上只允许bug fix                        |
| 第六轮集成测试          | 2022/9/11 | 2022/9/15  | 5    | 版本回归测试，管控代码合入，原则上只允许bug fix    |
| 第七轮集成测试          | 2022/9/16  | 2022/9/20 | 5    | 版本回归测试 (9.20~9.29预留buffer)       |
| Release               | 2022/9/30 | 2022/9/30   | 1    | 版本发布                                         |


# 代码合入说明
创新版本代码继承master分支 <br>
// 新特性代码请及时合入版本&自验证，跟随整体计划转测试


# Feature list
openGauss 3.1.0 Release版本发布的关键需求列表如下： <br>

|no|feature|status|sig|owner|
|:------|:-------|:-------|:-------|:-------|
| I50PXY      |【openGauss】发布订阅产品化能力增强    |Developing|        |        |
| I50Q06      |【openGauss】MySQL兼容性回合到社区    |Developing|        |        |
| I50PZM      |【openGauss】SQL引擎插件化能力增强  |Developing|        |        |
| I50PZV      |【openGauss】实现对MySQL简单语法的替换   |Developing|        |        |
| I50PYI      |【openGauss】MySQL数据全量迁移性能满足100MB/s   |Developing|        |        |
| I50PYM      |【openGauss】MySQL增量迁移性能提升，支持1W tps   |Developing|        |        |
| I50PY8      |【众智】MySQL对象全量迁移能力支持    |Developing|        |        |
| I50PYC      |【众智】MySQL DDL增量迁移能力支持    |Developing|        |        |
| I54AV9      |【众智】orafce插件支持openGauss    |Developing|        |        |

现启动版本需求/特性收集，欢迎各sig maintainer和社区开发者们积极反馈和交流。<br>
状态说明：Discussion(方案讨论，需求未接受)、 Developing(开发中)、 Testing(测试中)、 Accepted(已验收) <br>
<br>

# 需求/特性反馈基本流程 <br />
1、开发者/sig在本贴的表格中填写要合入3.1.0的需求/特性，并同时填写需求issue及链接     <br>
2、申请特性在TC例会进行评审，评审通过后在release management sig例会进行详细交付计划制定与评审
<br><br>