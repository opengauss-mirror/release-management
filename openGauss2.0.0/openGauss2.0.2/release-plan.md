# Release plan
|Stange name|Begin time|End time|
|:----------|:---------|:-------|
|Kernel update 2.0.1|2021-12-20|2021-12-23|
|Key feature collect|2021-12-24|2022-03-05|
|Kernel freezing|2022-03-06|2022-03-10|
|Key feature freezing|2022-03-11|2021-03-13|
|Build beta branch|2022-03-14|2022-03-20|
|Beta test round 1|2022-03-21|2021-03-26|
|Beta test round 2|2022--03-27|2022-04-03|
|release|2022-04-03|2022-04-04|

# Feture list
状态说明：discussion(方案讨论，需求未接受)，Reject(未纳入版本)，developing(开发中)，Testing(测试中)，Accepted(已验收)
|no|fetur|status|sig|owner|
|:----|:---|:---|:--|:----|
|1|[【BUGFIX】 修复两次备份、生成snapshot IO高与打印-no free slot等问题](https://gitee.com/opengauss/openGauss-server/commit/f927083841aa42de2740e4a83f20fbbf9875681d)|Testing|sig-kernel|[李剑秋](https://gitee.com/li_jianqiu) |
|2|[修复gs_guc/reload方式设置分组同步复制参数失败](https://gitee.com/opengauss/openGauss-server/commit/ef7949c398a5e77de0d599ebc6c794d77be30191)|Testing|sig-kernel|[胡正超](https://gitee.com/gentle_hu)|
|3|[notify 支持指定为cascade standby](https://gitee.com/opengauss/openGauss-server/commit/7344c836011064a4b034e309b7fee40fcd16a35a)|Testing|sig-CM|[nifinity](https://gitee.com/nifinity)|
|4|[【轻量级PR】在release打包文件中，添加libzstd库文件](https://gitee.com/opengauss/openGauss-server/commit/1db5ddc8f91d97cf2f014ddcdaa6b82ff4d6f95d)|Accepted|sig-om|[zhangxubo](https://gitee.com/zhang_xubo)|
|6|[支持any x分组组合同步复制协议](https://gitee.com/opengauss/openGauss-server/commit/ee99c06af33346d7d66ba6b201a665ab4c49d870)|Accepted|sig-kernel|[胡正超](https://gitee.com/gentle_hu)|
|7|[修复twophasecleaner内存泄漏](https://gitee.com/opengauss/openGauss-server/commit/7ed416426a01044e9e469a64b6496d8ae15471bb)|Accepted|sig-kernel|[maxiang](https://gitee.com/Xiao__Ma)|
|8|[修复视图时间戳出错的问题](https://gitee.com/opengauss/openGauss-server/commit/c3b98cd0849f4aec3e3ed8fea51bfe5e26e759f3)|Accepted|sig-kernel|[罗梓浩](https://gitee.com/luo_zihao5524)|
|9|[[修复缺陷master同步到2.0.0分支\] gs_probackup远程备份的时候，环境变量分离下，加载不到lib库](https://gitee.com/opengauss/openGauss-server/commit/f5e1bf0ef763f0e4362d5ff5f9304daff3fe395d)|Accepted|sig-probackup|[zhangxubo](https://gitee.com/zhang_xubo)|
|10|[pg_probackup数据页完整性校验](https://gitee.com/opengauss/openGauss-server/commit/55986704fc90e960271896d4887d473b6a5eee80)|Accepted|sig-kernel|[薛蒙恩](https://gitee.com/xue_meng_en)|
|11|[修复数据目录名被修改再恢复后gaussdb无法stop的问题](https://gitee.com/opengauss/openGauss-server/commit/ce5358b2dc5ec8f4204b597978403de2d8ce8c1b)|Accepted|sig-kernel|[罗梓浩](https://gitee.com/luo_zihao5524)|

