# Version Info
openGauss 3.1.1是规划在2022年12月31日发布的社区公测版本，面向openGauss的场景化、工具链和兼容性场景，提供更多新特性和功能，给开发者和用户带来全新的体验，服务更多的领域和更多的用户。<br>

3.1.1版本整体开发周期为2022年10月8日至2022年12月31日，实际开发过程按以下计划进行需求方案设计、开发、测试验收。<br>

# Release Plan


|Stage  name             | Begin time  | End time   | Days | Note                                      |
| ---------------------- | ----------- | ---------- | ---- | ----------------------------------------------------------|
| 需求方案设计        | 2022/10/8  | 2022/10/30  | 23   | 交付需求方案设计（各SIG自行完成需求方案设计评审）   |
| 需求开发验收           | 2022/11/1  | 2022/11/30  | 30   | 需求完成开发和自验证，代码提交合入master，测试验收    |
| 第一轮集成测试          | 2022/12/1 | 2022/12/7  | 7    | 版本集成测试，管控代码合入，原则上只允许bug fix                         |
| 第二轮集成测试          | 2022/12/8 | 2022/12/14  | 7    | 版本集成测试，管控代码合入，原则上只允许bug fix                            |
| 第三轮集成测试          | 2022/12/15 | 2022/12/23  | 7    | 版本集成测试，管控代码合入，原则上只允许bug fix                          |
| 预留buffer             | 2022/12/24  | 2022/12/28   | 5    |预留buffer解决突发问题       |
| 发布准备测试           | 2022/12/29  | 2022/12/30  | 2     | 版本发布测试        |
| Release               | 2022/12/31 | 2022/12/31   | 1    | 版本发布                                         |


# 代码合入说明
创新版本代码继承master分支 <br>
// 新特性代码请及时合入版本&自验证，跟随整体计划转测试


# Feature list
详见[openGauss 3.1.1 版本需求列表](https://e.gitee.com/opengaussorg/projects/451125/requirements/table)



现启动版本需求/特性收集，欢迎各sig maintainer和社区开发者们积极反馈和交流。<br>
状态说明：Discussion(方案讨论，需求未接受)、 Developing(开发中)、 Testing(测试中)、 Accepted(已验收) <br>
<br>

# 需求/特性反馈基本流程 <br />
1、开发者/sig在本贴的表格中填写要合入5.0.0的需求/特性，并同时填写需求issue及链接     <br>
2、申请特性在TC例会进行评审，评审通过后在release management sig例会进行详细交付计划制定与评审
<br><br>