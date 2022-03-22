

# **1. 流程背景**

为了规范社区化开发流程，支撑社区开发高效、有序开展，特梳理出基于“社区化开发”的需求接纳和管理规范，实现openGauss社区开发者有效协同，杜绝重复开发和PR合入冲突，提升开发效率。


# **2. 需求端到端交付流程**

利用TC月度例会、sig组双周例会（ sql引擎/存储引擎sig例会/QA sig组）做好需求的评审、方案评审、代码评审和验收


        • TC月度例会：需求价值和建议交付节奏评审，跨sig组的重大特性方案评审。针对接纳需求指定交付owner，落入迭代交付计划，社区公示，防止重复交付；


        • SIG组双周例会：设计方案评审，及时纠偏。针对方案评审通过的需求，PR检视SLA一周内响应；


        • QA sig组双周例会：测试方案评审，需求验收，为需求出口负责。

 


<table>
  <tr>
   <td>
    <strong>管道/组织&人员</strong>
   </td>
   <td colspan="3" >
    <strong>需求管理</strong>
   </td>
   <td colspan="7" >
    <strong>需求交付</strong>
   </td>
  </tr>
  <tr>
   <td>
    <strong>组织</strong>
   </td>
   <td>
    <strong>需求分析</strong>
   </td>
   <td>
    <strong>需求认领</strong>
   </td>
   <td>
    <strong>需求评议</strong>
   </td>
   <td>
    <strong>方案设计</strong>
   </td>
   <td>
    <strong>方案评审/串讲</strong>
   </td>
   <td>
    <strong>测试方案反串讲/评审</strong>
   </td>
   <td>
    <strong>代码编写</strong>
   </td>
   <td>
    <strong>需求自测</strong>
   </td>
   <td>
    <strong>代码检视</strong>
   </td>
   <td>
    <strong>需求验收</strong>
   </td>
  </tr>
  <tr>
   <td>
    <strong>PLM</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
  </tr>
  <tr>
   <td>
    <strong>交付owner</strong>
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
  </tr>
  <tr>
   <td>
    <strong>TC</strong>
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    √
<p>

    TC例会
   </td>
   <td>
     
   </td>
   <td>
    √
<p>

    重大特性TC例会评审
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
  </tr>
  <tr>
   <td>
    <strong>开发SIG组</strong>
   </td>
   <td>
    √
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    √
<p>

    开发SIG组例会
   </td>
   <td>
    √
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    <strong>*</strong>
   </td>
   <td>
     
   </td>
  </tr>
  <tr>
   <td>
    <strong>QA SIG组</strong>
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    √
   </td>
   <td>
    <strong>*</strong>
<p>

    QA SIG组例会
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    <strong>*</strong>
<p>

    QA SIG组例会
   </td>
  </tr>
  <tr>
   <td>
    <strong>release management SIG组</strong>
   </td>
   <td>
     
   </td>
   <td>
    √
   </td>
   <td>
    √
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
     
   </td>
   <td>
    <strong>√</strong>
   </td>
  </tr>
</table>


 

需求管理流程

![输入图片说明](picture/%E9%9C%80%E6%B1%82%E7%AE%A1%E7%90%86%E6%B5%81%E7%A8%8B.png)
 

特性交付流程

![输入图片说明](picture/%E7%89%B9%E6%80%A7%E4%BA%A4%E4%BB%98%E6%B5%81%E7%A8%8B.png)
 


## **2.1 需求管理**


### **2.1.1 需求录入**

 

外部开发者、社区合作伙伴等均可在社区通过issue录入需求。需求提交者进入对应的仓库，提交需求，如果不知道需求提交至那个仓，则默认提交至community仓。issue类型选择“需求”，状态保持默认“待办的”，此时需求进入需求分析。需求内容提交格式要求如下：


    **【需求标题】***


    _列存查询能力增强_

    **【客户对openGauss的需求（需求描述）】***


    _列存支持jsonb、json格式_


    **【openGauss的差距】***


    _暂不支持需求描述的能力_


    **【需求价值】***


    _影响客户预期与产品竞争力_


    **【目前客户使用openGauss，及其DBV合作伙伴产品的规模和升级/扩展计划】***


    _现网openGauss存量1000套，基于当前openGauss版本会持续演进， _


    **【期望交付时间】***


        _2022年9月份交付_

注：需求录入者可以在附件中录入详细的使用场景说明和规格要求。

示例如下：
![输入图片说明](picture/%E7%A4%BA%E4%BE%8B.png)
 


### **2.1.2 需求分析**


社区产品管理人员（PLM）例行把需求视图中，“需求分析”阶段的issue分配给需求分析者(sig组Maintainer/committer)进行需求价值分析，设置issue 标签为对应sql组（sig-sqlengine/sig-storageengine/其他），指定负责人为对应sql组。需求分析者需要在一周内完成需求分析，去伪存真，识别高价值需求，并给出需求的交付工作量。大颗粒需求需要分解为子需求，针对不建议落入研发管道的需求要给出原因说明。例如：由于用户不熟悉openGauss导致的使用类问题，需求分析者要把issue类型修改为“咨询”或者“缺陷”；针对低价值需求变更issue状态为“已拒绝”，并在评论区给出拒绝原因。


针对高价值需求 需求分析者需要变更issue状态为“需求认领”，并在评论区给出需求的交付工作量评估结果和结论。例如：工作量3人月，建议落入研发管道。


### **2.1.3 需求认领**


PLM将分析完毕的高价值需求列表通过邮件发送给RM SIG组成员，进行需求认领。并在一周内反馈认领结果（默认为不认领相关需求）。


需求认领模板
![输入图片说明](picture/%E9%9C%80%E6%B1%82%E8%AE%A4%E9%A2%86%E6%A8%A1%E6%9D%BF.png)

    


### **2.1.4 需求评议**


PLM在每月月初的TC例会上汇报需求分析和认领结果。经过TC例会评审通过后，在社区内公示。无人认领的需求PLM设置issue状态为“已拒绝”，评论区决绝原因：无研发人力。RM sig组成员把TC例会的会议决策纪要添加到issue附件中，并设置其issue相关字段。此时特性进入交付管道。


    类型：_“特性”_


    状态：_“方案设计”_


    负责人/协作：_开发者owner/测试owne_r


    计划时间：_XXX   -> XXX。_


    需求正式进入研发交付管道，由RM sig组PM进行需求交付跟踪。


    RM sig组成员操作指南

![输入图片说明](picture/sig%E7%BB%84%E6%88%90%E5%91%98%E6%93%8D%E4%BD%9C%E6%8C%87%E5%8D%97.png)
     


## **2.2 特性交付**


### **2.2.1 方案设计**


需求负责人根据社区需求设计模板要求和设计checklist 要求，输出方案设计文档和[设计checklist满足度评估表](openGauss%E8%AE%BE%E8%AE%A1CheckList.md)，添加到issue附件中，变更issue状态为“设计方案评审”。
请参考[设计文档模板](https://gitee.com/opengauss/community/blob/master/design/template/openGauss%20xx%E7%89%B9%E6%80%A7%E8%AE%BE%E8%AE%A1%E8%AF%B4%E6%98%8E%E4%B9%A6.md)


### **2.2.2 设计方案评审**


开发Sig组maintainer在双周例会上针对处于“设计方案评审”状态的issue进行评审，评审通过后进行需求测试方案设计阶段和代码编写阶段。需求负责人把评审通过的会议纪要、遗留问题闭环结论、需求设计文档，添加到issue附件中，并邮件知会RM sig组申请进入“测试方案评审”阶段。RM sig组成员变更issue状态为“测试方案评审”。


### **2.2.3 测试方案评审**

QA Sig组maintainer在双周例会上针对处于“测试方案评审”状态的issue进行评审，评审通过后进行测试用例编写阶段。测试负责人把评审通过的会议纪要、遗留问题闭环结论、测试方案文档，添加到issue附件中，并邮件知会RM sig组申请进入“代码编写与自测”阶段。RM sig组成员变更issue状态为“代码编写与自测”。
请参考[openGauss测试方案模板](https://gitee.com/opengauss/QA/blob/master/Test_Delivery_Templates/openGauss%20XX%E7%89%88%E6%9C%AC%E6%B5%8B%E8%AF%95%E7%AD%96%E7%95%A5%E6%A8%A1%E6%9D%BF.md)进行提交。


### **2.2.4 代码编写与自测**


开发责任人按照华为代码编写格式和提交要求完成代码输出和自验，并提交[checkin报告模板](https://gitee.com/opengauss/community/blob/master/check-in/template/opengGauss%20SQL%E5%85%BC%E5%AE%B9%E6%80%A7%E9%9C%80%E6%B1%82%E9%AA%8C%E6%94%B6checkin%E6%A8%A1%E6%9D%BF.md)。满足checkin的条件后，邮件知会RM  sig组申请进入“代码检视”阶段。RM sig组成员审视交付件满足度情况，针对满足条件的需求变更issue状态为“代码检视”。并提交对应的PR，建立PR与issue的关联关系。


### **2.2.5 代码提交**


开发sig组针对处于“代码检视”阶段的PR开展代码检视，代码检视要在一周内完成检视和检视意见提交。所有检视意见闭环后，sql组Maintainer/committer合入PR到社区，设置关联issue状态为“测试验收”，开发责任人邮件知会QA sig组开展测试用例执行和需求验收。


### **2.2.6 测试验收**


测试owner用例执行完毕后，针对测试发现的阻塞类型完成修复回归后，测试owner邮件知会RM sig 组成员申请进行“”issue状态修改“已完成”。



