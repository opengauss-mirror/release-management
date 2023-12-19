## 版本背景

openGauss 5.0.1 Update版本是openGauss 5.0.0 Release的补丁版本。基于5.0.0版本基础上，回合主干分支的部分需求和缺陷，发布5.0.1补丁版本。


## 需求范围

openGauss 5.0.1 补丁版本回合的需求列表如下：


|  编号 | 需求描述  | PR链接 |
| ----- | ----- | ----- |
| 1 | 主备高可用能力增强 | https://gitee.com/opengauss/openGauss-server/pulls/3981 |
| 2 | shared_buffers支持大页内存 | https://gitee.com/opengauss/openGauss-server/pulls/3551 |
| 3 | 支持在A兼容性模式下对空串的处理 | https://gitee.com/opengauss/openGauss-server/pulls/3729 |
| 4 | openGauss资源池化支持极致RTO按需回放 | https://gitee.com/opengauss/openGauss-server/pulls/3544 |
| 5 | 发布订阅支持冲突解决 | https://gitee.com/opengauss/openGauss-server/pulls/4287 |
| 6 | 添加视图用于查询阻止wal清理的因素 | https://gitee.com/opengauss/openGauss-server/pulls/4480 |
| 7 | 金融版本特性 | https://gitee.com/opengauss/openGauss-server/pulls/4482 |


## 回合缺陷

### server仓库回合缺陷列表

| 标题                                                         | 原PR链接                                                | ISSUE                                                      | 问题级别 |
| ------------------------------------------------------------ | ------------------------------------------------------- | ---------------------------------------------------------- | -------- |
| 修复json_to_record的偶些场景的core问题                       | https://gitee.com/opengauss/openGauss-server/pulls/3320 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SXJL    | 严重     |
| 解决pg_stat_segment_extent_usage的部分问题                   | https://gitee.com/opengauss/openGauss-server/pulls/3376 | https://e.gitee.com/opengaussorg/dashboard?issue=I6RYPD    | 严重     |
| 修复发布订阅在IU操作没有newtuple时的core问题                 | https://gitee.com/opengauss/openGauss-server/pulls/3593 | https://e.gitee.com/opengaussorg/dashboard?issue=I7DIFX    | 严重     |
| 修改从2.0升级到3.0以上版本，升级过程中执行select nextval导致core问题 | https://gitee.com/opengauss/openGauss-server/pulls/3967 | https://e.gitee.com/opengaussorg/dashboard?issue=I7NUKT    | 严重     |
| 修复执行带自治事务的存储过程未及时释放内存的问题             | https://gitee.com/opengauss/openGauss-server/pulls/3315 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SLS6    | 主要     |
| 【轻量级PR】修复gs_xlogdump_parsepage_tablepath报错提示不合理的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3407 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TDQT    | 主要     |
| 【资源池化】recovery阶段增加异常处理分支                     | https://gitee.com/opengauss/openGauss-server/pulls/3442 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Q3GV    | 主要     |
| 【bugfixed】解决MySQL模式下 insert on duplicate key语法宕机的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3342 | https://e.gitee.com/opengaussorg/dashboard?issue=I6VMN6    | 主要     |
| 修复gist索引处理NaN的bug                                     | https://gitee.com/opengauss/openGauss-server/pulls/3350 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SZCM    | 主要     |
| 修复makefile编译pagehack报错                                 | https://gitee.com/opengauss/openGauss-server/pulls/3364 | https://e.gitee.com/opengaussorg/dashboard?issue=I6WQED    | 主要     |
| 资源池化下使用dms_contrl.sh拉起gaussdb时，支持传入特殊参数   | https://gitee.com/opengauss/openGauss-server/pulls/3491 | https://e.gitee.com/opengaussorg/dashboard?issue=I71U7I    | 主要     |
| fix bug about verify parameter of gs_initdb                  | https://gitee.com/opengauss/openGauss-server/pulls/3484 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Z5GK    | 主要     |
| DMS reform repair阶段确认copy inst的回调函数适配             | https://gitee.com/opengauss/openGauss-server/pulls/3495 | https://e.gitee.com/opengaussorg/dashboard?issue=I7852H    | 主要     |
| 修复缺陷【表上带序列时，更新表数据存在内存泄露】             | https://gitee.com/opengauss/openGauss-server/pulls/3375 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Y0JK    | 主要     |
| 修复缺陷【分区表全表更新时存在内存泄露】                     | https://gitee.com/opengauss/openGauss-server/pulls/3394 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Z3JF    | 主要     |
| 修复缺陷B兼容性+线程池下，开启会话内存限制出现coredump       | https://gitee.com/opengauss/openGauss-server/pulls/3388 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YS1O    | 主要     |
| 修复cluster下盘场景coredump问题                              | https://gitee.com/opengauss/openGauss-server/pulls/3393 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Z16C    | 主要     |
| pg_resetxlog增加参数合法性校验                               | https://gitee.com/opengauss/openGauss-server/pulls/3417 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YC95    | 主要     |
| 【资源池化】解决startup线程判断reform失败出现漏判的情况      | https://gitee.com/opengauss/openGauss-server/pulls/3619 | https://e.gitee.com/opengaussorg/dashboard?issue=I7F9JL    | 主要     |
| 【资源池化】【bugfix】打开按需回放后，HashMap内存在初始化阶段就完成申请，防止回放过程时因为内存申请失败导致故障恢复失败 | https://gitee.com/opengauss/openGauss-server/pulls/3618 | https://e.gitee.com/opengaussorg/dashboard?issue=I7F9X2    | 主要     |
| dorado双集群日志回放问题                                     | https://gitee.com/opengauss/openGauss-server/pulls/3643 | https://e.gitee.com/opengaussorg/dashboard?issue=I7G2WY    | 主要     |
| 解决ss双集群build问题                                        | https://gitee.com/opengauss/openGauss-server/pulls/3664 | https://e.gitee.com/opengaussorg/dashboard?issue=I7HZOT    | 主要     |
| 【资源池化】【bugfix】解决多次进入按需回放时，回放日志选择出错的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3665 | https://e.gitee.com/opengaussorg/dashboard?issue=I7HRZV    | 主要     |
| 修复pg_partition_size()函数宕机问题。                        | https://gitee.com/opengauss/openGauss-server/pulls/3615 | https://e.gitee.com/opengaussorg/dashboard?issue=I7DSG4    | 主要     |
| 【资源池化】【bugfix】修复switchover或failover过程中重建复制槽coredump的问题，支持逻辑复制，支持删除复制槽 | https://gitee.com/opengauss/openGauss-server/pulls/3678 | https://e.gitee.com/opengaussorg/dashboard?issue=I7I77E    | 主要     |
| 修复缺陷：执行grant select (prosrc) on pg_proc to test后，数据库宕机 | https://gitee.com/opengauss/openGauss-server/pulls/3614 | https://e.gitee.com/opengaussorg/dashboard?issue=I6NLEX    | 主要     |
| [bug fix] 修复copy from制定timestamp format中包含FF6导致coredump的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3662 | https://e.gitee.com/opengaussorg/dashboard?issue=I7AU3E    | 主要     |
| 【资源池化】【bugfix】解决按需回放部分问题                   | https://gitee.com/opengauss/openGauss-server/pulls/3684 | https://e.gitee.com/opengaussorg/dashboard?issue=I7ITGE    | 主要     |
| fseeko规避                                                   | https://gitee.com/opengauss/openGauss-server/pulls/3743 | https://e.gitee.com/opengaussorg/dashboard?issue=I7J5UB    | 主要     |
| 修复无权限用户修改发布订阅名时报错信息错误的问题             | https://gitee.com/opengauss/openGauss-server/pulls/3279 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Q0A8    | 次要     |
| 修复opfusion更新带checkoption视图时对象未关闭和校验失效的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3264 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Q81L    | 次要     |
| 保持ss_enable_dss与ss_enable_dms一致                         | https://gitee.com/opengauss/openGauss-server/pulls/3339 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UR2O    | 次要     |
| 修复view definer在权限相关的一些bug                          | https://gitee.com/opengauss/openGauss-server/pulls/3262 | https://e.gitee.com/opengaussorg/dashboard?issue=I6OZMJ    | 次要     |
| guc参数校验函数check_ss_rdma_work_config完善                 | https://gitee.com/opengauss/openGauss-server/pulls/3353 | https://e.gitee.com/opengaussorg/dashboard?issue=I6VI2J    | 次要     |
| gs_probackup show时候跳过dss初始化                           | https://gitee.com/opengauss/openGauss-server/pulls/3392 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XD8D    | 次要     |
| SsIsSkipPath代码规范完善                                     | https://gitee.com/opengauss/openGauss-server/pulls/3400 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XRR9    | 次要     |
| 闪回恢复操作在drop两次同名表时的设计缺陷                     | https://gitee.com/opengauss/openGauss-server/pulls/3330 | https://e.gitee.com/opengaussorg/dashboard?issue=I6GE2Y    | 次要     |
| 修复username中出现@的场景                                    | https://gitee.com/opengauss/openGauss-server/pulls/3319 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TAW9    | 次要     |
| bug修复-非保留关键字ignore，作为列名时报错                   | https://gitee.com/opengauss/openGauss-server/pulls/3332 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UG5Y    | 次要     |
| 修复通过同义词refresh物化视图失败的问题                      | https://gitee.com/opengauss/openGauss-server/pulls/3333 | https://e.gitee.com/opengaussorg/dashboard?issue=I6RW16    | 次要     |
| 解决user@host中当用户名过长时的报错信息与mysql报错信息不一致的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3337 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TAR5    | 次要     |
| 修复允许通过 alter table 命令，将表上的列名设置为 tid        | https://gitee.com/opengauss/openGauss-server/pulls/3351 | https://e.gitee.com/opengaussorg/dashboard?issue=I6WGG1    | 次要     |
| show warnings bugfix                                         | https://gitee.com/opengauss/openGauss-server/pulls/3308 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SKCO    | 次要     |
| 1. 适配DMS DRC允许不一致；2. 适配DRC按需回收能力             | https://gitee.com/opengauss/openGauss-server/pulls/3323 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XRA7    | 次要     |
| 修复部分资源池化问题                                         | https://gitee.com/opengauss/openGauss-server/pulls/3475 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XR32    | 次要     |
| 修复src/common/backend/parser下的Makefile                    | https://gitee.com/opengauss/openGauss-server/pulls/3346 | https://e.gitee.com/opengaussorg/dashboard?issue=I6W9EZ    | 次要     |
| 修复存储过程报错位置不准确的问题                             | https://gitee.com/opengauss/openGauss-server/pulls/3368 | https://e.gitee.com/opengaussorg/dashboard?issue=I6PAZW    | 次要     |
| 解决gs_dump does not resolve circular dependency的问题       | https://gitee.com/opengauss/openGauss-server/pulls/3366 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SKVA    | 次要     |
| 修复打开plsql_show_all_error后未记录gs_error表的问题         | https://gitee.com/opengauss/openGauss-server/pulls/3367 | https://e.gitee.com/opengaussorg/dashboard?issue=I6RUMQ    | 次要     |
| 修复 xc_for_update 的用例不通过的问题                        | https://gitee.com/opengauss/openGauss-server/pulls/3413 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YV3Y    | 次要     |
| 【资源池化】更新dms版本号                                    | https://gitee.com/opengauss/openGauss-server/pulls/3534 | https://e.gitee.com/opengaussorg/dashboard?issue=I77BPF    | 次要     |
| pg_resetxlog -O报错说明调整                                  | https://gitee.com/opengauss/openGauss-server/pulls/3455 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YIJ2    | 次要     |
| 解决update多表显式关联超过三张表结果错误的问题               | https://gitee.com/opengauss/openGauss-server/pulls/3448 | https://e.gitee.com/opengaussorg/dashboard?issue=I6ZC79    | 次要     |
| pg_ctl在非资源池化场景修复                                   | https://gitee.com/opengauss/openGauss-server/pulls/3579 | https://e.gitee.com/opengaussorg/dashboard?issue=I7DNPU    | 次要     |
| 修复pbe场景下create trigger的问题                            | https://gitee.com/opengauss/openGauss-server/pulls/3460 | https://e.gitee.com/opengaussorg/dashboard?issue=I6WLVL    | 次要     |
| pagehack适配release方式编译                                  | https://gitee.com/opengauss/openGauss-server/pulls/3401 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Z3N5    | 次要     |
| 【资源池化】6.17修复DMS版本的更新                            | https://gitee.com/opengauss/openGauss-server/pulls/3588 | https://e.gitee.com/opengaussorg/dashboard?issue=I765E4    | 次要     |
| 修复基于cstore表的视图select for update导致数据库core的问题  | https://gitee.com/opengauss/openGauss-server/pulls/3487 | https://e.gitee.com/opengaussorg/dashboard?issue=I76UF2    | 次要     |
| 【资源池化】ss_buffer_ctrl对于非资源池化进行拦截             | https://gitee.com/opengauss/openGauss-server/pulls/3629 | https://e.gitee.com/opengaussorg/dashboard?issue=I7FARF    | 次要     |
| 【bugfixed】解决创建表空间，绝对路径不存在时会话卡住，数据库服务无法正常关闭也无法登陆的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3523 | https://e.gitee.com/opengaussorg/dashboard?issue=I76MG5    | 次要     |
| 修改文件被删除时处理逻辑，由原先DEBUG日志修改为：ERROR日志。且增加判断：文件被删除时直接返回 | https://gitee.com/opengauss/openGauss-server/pulls/3517 | https://e.gitee.com/opengaussorg/dashboard?issue=I6WZM7    | 次要     |
| 【bugfixed】解决存在exception时匿名事务占用内存不断上升的问题 & 2个memcheck 内存泄漏 | https://gitee.com/opengauss/openGauss-server/pulls/3533 | https://e.gitee.com/opengaussorg/dashboard?issue=I7A4DO    | 次要     |
| 解决在兼容b库上，lock table功能在nodes.yml中url的参数为非simple模式下，利用jdbc（yat）运行结果不正确的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3385 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TAMS    | 次要     |
| 修复列存表 update 内存泄露                                   | https://gitee.com/opengauss/openGauss-server/pulls/3420 | https://e.gitee.com/opengaussorg/dashboard?issue=I70KOE    | 次要     |
| 修复分区表统计信息错误，优化其查询计划                       | https://gitee.com/opengauss/openGauss-server/pulls/3369 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Y0EI    | 次要     |
| 双集群日志回放问题                                           | https://gitee.com/opengauss/openGauss-server/pulls/3659 | https://e.gitee.com/opengaussorg/dashboard?issue=I7HZDQ    | 次要     |
| 修复pg_job无法重新执行的bug                                  | https://gitee.com/opengauss/openGauss-server/pulls/3426 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YB91    | 次要     |
| 【bugfixed】对提前返回的场景，将路径指针*ptr恢复为‘/’        | https://gitee.com/opengauss/openGauss-server/pulls/3604 | https://e.gitee.com/opengaussorg/dashboard?issue=I76MG5    | 次要     |
| 【资源池化】转移页面时，当本地页面淘汰的情况下，让请求节点从磁盘加载 | https://gitee.com/opengauss/openGauss-server/pulls/3655 | https://e.gitee.com/opengaussorg/dashboard?issue=I78II2    | 次要     |
| to_date函数支持秒单位后使用小数点                            | https://gitee.com/opengauss/openGauss-server/pulls/3586 | https://e.gitee.com/opengaussorg/dashboard?issue=I7DIS4    | 次要     |
| 解决兼容B库下，可以成功创建user@localhost用户 但是无法连接   | https://gitee.com/opengauss/openGauss-server/pulls/3381 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TCWE    | 次要     |
| gs_probackup: Multithread backup supports pglz compression   | https://gitee.com/opengauss/openGauss-server/pulls/3671 | https://e.gitee.com/opengaussorg/dashboard?issue=I7IHTL    | 次要     |
| issue修复：dolphin插件下B兼容数据库分区表gs_dump失败修复     | https://gitee.com/opengauss/openGauss-server/pulls/3276 | https://e.gitee.com/opengaussorg/dashboard?issue=I6QMGL    | 未指定   |
| dblink完善异常场景安全性                                     | https://gitee.com/opengauss/openGauss-server/pulls/3294 | 未指定                                                     | 未指定   |
| 问题修复：dolphin插件下含enum类型列的表导出后无法导入修复    | https://gitee.com/opengauss/openGauss-server/pulls/3303 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TDA2    | 未指定   |
| 【bugfixed】解决orderby 列的别名在distinct中也报错的问题     | https://gitee.com/opengauss/openGauss-server/pulls/3326 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TMU5    | 未指定   |
| 修复uppercase_attribute_name打开的场景下，gs_dump的core问题  | https://gitee.com/opengauss/openGauss-server/pulls/3327 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SOQU    | 未指定   |
| issue修复：COMMENT ON对存储过程注释后，gs_dump导出内容导入失败问题修复 | https://gitee.com/opengauss/openGauss-server/pulls/3292 | https://e.gitee.com/opengaussorg/dashboard?issue=I6QWI9    | 未指定   |
| 【资源池化】DB侧适配DMS的并行逻辑                            | https://gitee.com/opengauss/openGauss-server/pulls/3345 | https://e.gitee.com/opengaussorg/dashboard?issue=I6PPOJ    | 未指定   |
| 【资源池化】增加系统内置函数ss_buffer_ctrl，便于直接查看buf_ctrl | https://gitee.com/opengauss/openGauss-server/pulls/3423 | https://e.gitee.com/opengaussorg/dashboard?issue=I6PPOJ    | 未指定   |
| 【资源池化】系统函数ss_buffer_ctrl增加升级和回退脚本         | https://gitee.com/opengauss/openGauss-server/pulls/3457 | https://e.gitee.com/opengaussorg/dashboard?issue=I6PPOJ    | 未指定   |
| B模式下fetch自动退出                                         | https://gitee.com/opengauss/openGauss-server/pulls/3295 | 未指定                                                     | 未指定   |
| 修复memcheck问题                                             | https://gitee.com/opengauss/openGauss-server/pulls/3382 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YHAK    | 未指定   |
| _copyCreateTrigStmt中funcSource复制                          | https://gitee.com/opengauss/openGauss-server/pulls/3109 | 未指定                                                     | 未指定   |
| [资源池化]在线failover停止业务线程步骤前移+failover微重构    | https://gitee.com/opengauss/openGauss-server/pulls/3512 | https://e.gitee.com/opengaussorg/dashboard?issue=I73F5G    | 未指定   |
| 修复 NasWrite 中free之后还继续使用指针的问题                 | https://gitee.com/opengauss/openGauss-server/pulls/3383 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YG27    | 未指定   |
| [资源池化]增加flush_copy阶段在异常场景下的退出分支           | https://gitee.com/opengauss/openGauss-server/pulls/3516 | https://e.gitee.com/opengaussorg/dashboard?issue=I73F5G    | 未指定   |
| 【资源池化】reform先完成startup线程后退出                    | https://gitee.com/opengauss/openGauss-server/pulls/3522 | https://e.gitee.com/opengaussorg/dashboard?issue=I73F5G    | 未指定   |
| 优化gstrace_options、gaussdb_options、gsql_options、gsbasebackup_options、gsdump_options、gsloader_options测试用例 | https://gitee.com/opengauss/openGauss-server/pulls/3430 | 未指定                                                     | 未指定   |
| 脱敏grant usage语法                                          | https://gitee.com/opengauss/openGauss-server/pulls/3437 | 未指定                                                     | 未指定   |
| shared storage adapt dual cluster in the same city about read consistency cluster switching | https://gitee.com/opengauss/openGauss-server/pulls/3438 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UI96    | 未指定   |
| 【资源池化】同步接口dms_buf_res_rebuild_drc_parallel         | https://gitee.com/opengauss/openGauss-server/pulls/3559 | https://e.gitee.com/opengaussorg/dashboard?issue=I73F5G    | 未指定   |
| 资源池化dorado备机群主备切换                                 | https://gitee.com/opengauss/openGauss-server/pulls/3555 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UI96    | 未指定   |
| dblink代码逻辑调整                                           | https://gitee.com/opengauss/openGauss-server/pulls/3456 | https://e.gitee.com/opengaussorg/dashboard?issue=I739AY    | 未指定   |
| openGauss资源池化支持极致RTO按需回放                         | https://gitee.com/opengauss/openGauss-server/pulls/3544 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UI0H    | 未指定   |
| 修复溢出判断错误问题                                         | https://gitee.com/opengauss/openGauss-server/pulls/3408 | https://e.gitee.com/opengaussorg/dashboard?issue=I7038X    | 未指定   |
| 修复NUMERIC_SIGN宏在值为Nan时获取错误的BUG                   | https://gitee.com/opengauss/openGauss-server/pulls/3470 | 未指定                                                     | 未指定   |
| 解决dorado sharestorage init失败的问题                       | https://gitee.com/opengauss/openGauss-server/pulls/3596 | 未指定                                                     | 未指定   |
| 修复笔误导致两个函数无法使用的问题                           | https://gitee.com/opengauss/openGauss-server/pulls/3488 | https://e.gitee.com/opengaussorg/dashboard?issue=I78O7S    | 未指定   |
| 【资源池化】系统函数ss_buffer_ctrl--删除内容锁的请求         | https://gitee.com/opengauss/openGauss-server/pulls/3601 | https://e.gitee.com/opengaussorg/dashboard?issue=I6PPOJ    | 未指定   |
| 定时任务适配ACL权限检查                                      | https://gitee.com/opengauss/openGauss-server/pulls/3210 | https://e.gitee.com/opengaussorg/dashboard?issue=I6OUDI    | 未指定   |
| 资源池化dorado双集群屏蔽影响                                 | https://gitee.com/opengauss/openGauss-server/pulls/3616 | 未指定                                                     | 未指定   |
| 提高timestamp/time/date输出函数的速度                        | https://gitee.com/opengauss/openGauss-server/pulls/3015 | 未指定                                                     | 未指定   |
| 合并pg pr：PrivateRefCount相关问题修复                       | https://gitee.com/opengauss/openGauss-server/pulls/3013 | 未指定                                                     | 未指定   |
| 修复query_dop>1时修改外部表导致的宕机问题                    | https://gitee.com/opengauss/openGauss-server/pulls/3486 | https://e.gitee.com/opengaussorg/dashboard?issue=I78GJR    | 未指定   |
| dblink提前校验是否在线程池模式                               | https://gitee.com/opengauss/openGauss-server/pulls/3547 | 未指定                                                     | 未指定   |
| 修复发布端主备切换后，订阅端无法自动连接到新主的问题         | https://gitee.com/opengauss/openGauss-server/pulls/3539 | https://e.gitee.com/opengaussorg/dashboard?issue=I7BO0A    | 未指定   |
| 【资源池化】共享存储模式禁止配置过大的Proc threads数量       | https://gitee.com/opengauss/openGauss-server/pulls/3649 | https://e.gitee.com/opengaussorg/dashboard?issue=I71B6Q    | 未指定   |
| 修复回收站导致分区表relfilenode无法删除的问题                | https://gitee.com/opengauss/openGauss-server/pulls/3538 | https://e.gitee.com/opengaussorg/dashboard?issue=I77SW4    | 未指定   |
| 【bugfixed】解决 procedure 存在variadic参数时call报错的问题  | https://gitee.com/opengauss/openGauss-server/pulls/3598 | https://e.gitee.com/opengaussorg/dashboard?issue=I7CPCA    | 未指定   |
| on update current_timestamp特性对并发update修复              | https://gitee.com/opengauss/openGauss-server/pulls/3609 | https://e.gitee.com/opengaussorg/dashboard?issue=I7EGNS    | 未指定   |
| 修复分区表文件无法删除、部分array函数coredump的问题          | https://gitee.com/opengauss/openGauss-server/pulls/3610 | https://e.gitee.com/opengaussorg/dashboard?issue=I7F3YQ    | 未指定   |
| 修复copy识别gbk/gb18030中文字符错误的bug                     | https://gitee.com/opengauss/openGauss-server/pulls/3661 | https://e.gitee.com/opengaussorg/dashboard?issue=I7GPV2    | 未指定   |
| 修复多次drop package body失败的问题                          | https://gitee.com/opengauss/openGauss-server/pulls/3703 | 未指定                                                     | 未指定   |
| 开启synchronous_commit='remote_apply'后，事务提交延迟过大    | https://gitee.com/opengauss/openGauss-server/pulls/3611 | https://e.gitee.com/opengaussorg/dashboard?issue=I7F570    | 未指定   |
| 双集群build check                                            | https://gitee.com/opengauss/openGauss-server/pulls/3780 | https://e.gitee.com/opengaussorg/dashboard?issue=I7IM3I    | 未指定   |
| 修正了parser.cpp文件中的拼写错误                             | https://gitee.com/opengauss/openGauss-server/pulls/3144 | https://e.gitee.com/opengaussorg/dashboard?issue=I6N4JB    | 不重要   |
| probackup提示                                                | https://gitee.com/opengauss/openGauss-server/pulls/3462 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XA5T    | 不重要   |
| 创建触发器语法报错信息修改                                   | https://gitee.com/opengauss/openGauss-server/pulls/3110 | https://e.gitee.com/opengaussorg/dashboard?issue=I6496V    | 不重要   |
| gsql explain执行调整                                         | https://gitee.com/opengauss/openGauss-server/pulls/3416 | https://e.gitee.com/opengaussorg/dashboard?issue=I70DDJ    | 不重要   |
| 修复fuction带参数并且参数个数和默认入参个数相同，不带括号调用报错的问题。 | https://gitee.com/opengauss/openGauss-server/pulls/3436 | https://e.gitee.com/opengaussorg/dashboard?issue=I71I9G    | 不重要   |
| 替换存储过程时，重建依赖于此存储过程的视图                   | https://gitee.com/opengauss/openGauss-server/pulls/3439 | https://e.gitee.com/opengaussorg/dashboard?issue=I71D06    | 不重要   |
| 修复gs_errors表中行号信息不准确的问题                        | https://gitee.com/opengauss/openGauss-server/pulls/3443 | https://e.gitee.com/opengaussorg/dashboard?issue=I71A5P    | 不重要   |
| bug修复-非保留关键字charset，作为列名时报错                  | https://gitee.com/opengauss/openGauss-server/pulls/3445 | https://e.gitee.com/opengaussorg/dashboard?issue=I72RXW    | 不重要   |
| 修复存在dolphin时使用反引号当列名插入失败的问题              | https://gitee.com/opengauss/openGauss-server/pulls/3447 | https://e.gitee.com/opengaussorg/dashboard?issue=I725RF    | 不重要   |
| 修复local_debug_server_info函数返回值类型错误的问题          | https://gitee.com/opengauss/openGauss-server/pulls/3454 | https://e.gitee.com/opengaussorg/dashboard?issue=I72JSK    | 不重要   |
| 当targetlist存在系统列时，不重写fulljoin                     | https://gitee.com/opengauss/openGauss-server/pulls/3459 | https://e.gitee.com/opengaussorg/dashboard?issue=I73J9V    | 不重要   |
| connect by 查询中使用同义词报错                              | https://gitee.com/opengauss/openGauss-server/pulls/3108 | https://e.gitee.com/opengaussorg/dashboard?issue=I6LRTZ    | 不重要   |
| 【bugfixed】增加对 file_fdw 扩展的删除限制，与文档保持一致   | https://gitee.com/opengauss/openGauss-server/pulls/3506 | https://e.gitee.com/opengaussorg/dashboard?issue=I77PLV    | 不重要   |
| 修复创建包头报错没有记录到gs_source的问题                    | https://gitee.com/opengauss/openGauss-server/pulls/3483 | https://e.gitee.com/opengaussorg/dashboard?issue=I7775Y    | 不重要   |
| 修复视图定义中包含row mark子句时报错的问题                   | https://gitee.com/opengauss/openGauss-server/pulls/3518 | https://e.gitee.com/opengaussorg/dashboard?issue=I790RF    | 不重要   |
| 修复dolphin 的列名大小写在触发器中的问题                     | https://gitee.com/opengauss/openGauss-server/pulls/3542 | https://e.gitee.com/opengaussorg/dashboard?issue=I7BVBT    | 不重要   |
| 【bugfixed】解决全量重建备机时，postgresconf.guc.bak文件被覆盖，postgresql.conf.bak文件被删除问题 | https://gitee.com/opengauss/openGauss-server/pulls/3553 | https://e.gitee.com/opengaussorg/dashboard?issue=I77ML6    | 不重要   |
| 修复存储过程种包含commit时出现内存泄漏的问题                 | https://gitee.com/opengauss/openGauss-server/pulls/3519 | https://e.gitee.com/opengaussorg/dashboard?issue=I7AKHG    | 不重要   |
| 解决分区键表达式场景，打开enable_partition_opfusion走opfusion后报错 | https://gitee.com/opengauss/openGauss-server/pulls/3537 | https://e.gitee.com/opengaussorg/dashboard?issue=I7984D    | 不重要   |
| gs_dumpall不备份系统gs_role角色                              | https://gitee.com/opengauss/openGauss-server/pulls/3573 | https://e.gitee.com/opengaussorg/dashboard?issue=I72MWS    | 不重要   |
| 修复资源池化系统toast表reloption含有segment=on               | https://gitee.com/opengauss/openGauss-server/pulls/3674 | https://e.gitee.com/opengaussorg/dashboard?issue=I7DU57    | 不重要   |
| 增加DMS日志存储，优化日志打印信息                            | https://gitee.com/opengauss/openGauss-server/pulls/3751 | https://e.gitee.com/opengaussorg/dashboard?issue=I70B1Q    | 不重要   |
| shared storage adapt dual cluster about deploy and main standby only read | https://gitee.com/opengauss/openGauss-server/pulls/3304 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UI96    | 不重要   |
| 修复3.0.0-3.1.0-5.1.0跨版本灰度升级失败，报错Key (oid)=(560) already exists | https://gitee.com/opengauss/openGauss-server/pulls/4192 | https://e.gitee.com/opengaussorg/dashboard?issue=I82MZR    | 未指定   |
| 修复interval在存储过程中赋值错误的问题                       | https://gitee.com/opengauss/openGauss-server/pulls/4047 | https://e.gitee.com/opengaussorg/dashboard?issue=I7VCZI    | 未指定   |
| 【回合5.0.0分支】解决备机获取快照导致主备复制卡住的问题      | https://gitee.com/opengauss/openGauss-server/pulls/3651 | 未指定                                                     | 未指定   |
| 修复alter system set导致参数设置错误的问题                   | https://gitee.com/opengauss/openGauss-server/pulls/4240 | https://gitee.com/opengauss/openGauss-server/issues/I7VXNQ | 未指定   |
| 实现pg_terminate_active_session_socket用于直接关闭session的socket | https://gitee.com/opengauss/openGauss-server/pulls/4076 | 未指定                                                     | 未指定   |
| 解决gs_ctl内存泄漏                                           | https://gitee.com/opengauss/openGauss-server/pulls/3815 | 未指定                                                     | 未指定   |
| 【bugfix】【资源池化】解决按需回放部分问题                   | https://gitee.com/opengauss/openGauss-server/pulls/3892 | I7PI9D                                                     | 主要     |
| 【资源池化】解决消息超时时间默认1s导致的smon流程无法成功的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3896 | I7PNXZ                                                     | 次要     |
| 适配初始化时ENABLE_DMS未生效的场景，toast表不增加segment=on选项 | https://gitee.com/opengauss/openGauss-server/pulls/3889 | 未指定                                                     | 未指定   |
| 适配DSS接口与错误码修改                                      | https://gitee.com/opengauss/openGauss-server/pulls/3946 | 未指定                                                     | 未指定   |
| 【bugfix】【资源池化】解决按需回放部分问题                   | https://gitee.com/opengauss/openGauss-server/pulls/3945 | I7SNUJ                                                     | 主要     |
| 【资源池化】适配DMS兼容性                                    | https://gitee.com/opengauss/openGauss-server/pulls/3979 | I7F1RO                                                     | 不重要   |
| dms_control执行脚本删除大量无用日志                          | https://gitee.com/opengauss/openGauss-server/pulls/4011 | 未指定                                                     | 未指定   |
| 适配DMS侧增加smon_recycle线程；DMS推点                       | https://gitee.com/opengauss/openGauss-server/pulls/4079 | I7XV28                                                     | 次要     |
| 【bugfix】解决按需回放部分问题                               | https://gitee.com/opengauss/openGauss-server/pulls/4030 | I7Q6BU I7IMMH I7ZB9E                                       | 主要     |
| 段页表支持hash索引插入                                       | https://gitee.com/opengauss/openGauss-server/pulls/3998 | I7QC81                                                     | 不重要   |
| 【资源池化】owner转移页面场景，对于been_load为false情况，补充内容锁的释放 | https://gitee.com/opengauss/openGauss-server/pulls/4116 | I7ZR5M                                                     | 次要     |
| 【资源池化】DMS推点                                          | https://gitee.com/opengauss/openGauss-server/pulls/4121 | I7VNQC                                                     | 主要     |
| 修复极致RTO支持备机读对按需回放的影响                        | https://gitee.com/opengauss/openGauss-server/pulls/4115 | I7ZD5L I7ZXV9                                              | 主要     |
| 修改dss_contrl脚本，实现僵死检测                             | https://gitee.com/opengauss/openGauss-server/pulls/4068 | I80FFK                                                     | 次要     |
| 解决关闭双写，段页式执行local_space_shrink可能会core的问题   | https://gitee.com/opengauss/openGauss-server/pulls/4138 | I7XXCR                                                     | 主要     |
| 修复hash索引编译告警                                         | https://gitee.com/opengauss/openGauss-server/pulls/4118 | I7QC81                                                     | 不重要   |
| 9.12dss推点                                                  | https://gitee.com/opengauss/openGauss-server/pulls/4105 | 未指定                                                     | 未指定   |
| issue修复：dms增加本地dn校验                                 | https://gitee.com/opengauss/openGauss-server/pulls/4148 | I7Q1DP                                                     | 未指定   |
| 【资源池化】mes worker线程回调函数中使用超时接口             | https://gitee.com/opengauss/openGauss-server/pulls/4143 | I7VNQC I7YLPM                                              | 主要     |
| DB侧适配新MES；适配参数变更；推进commit点                    | https://gitee.com/opengauss/openGauss-server/pulls/4139 | I65AFJ                                                     | 未指定   |
| 【资源池化】修复主备倒换后,由于新主的segfiles里面fd是0,会导致读和aio出错的问题 | https://gitee.com/opengauss/openGauss-server/pulls/4168 | I7ZI6O I80U20                                              | 主要     |
| 【bugfix】修复主节点按需回放时，重启备节点，主节点卡在PM_WAIT_BACKEND | https://gitee.com/opengauss/openGauss-server/pulls/4171 | I7YQRJ I82ZAD                                              | 主要     |
| 【资源池化】对于请求页面长时间等待的日志，避免其打印到前端gsql | https://gitee.com/opengauss/openGauss-server/pulls/4182 | I836G4                                                     | 次要     |
| 1、修复SS switchover TwoPhaseCleaner退出失败；2、优化更新primaryInst逻辑，去除重复校验 | https://gitee.com/opengauss/openGauss-server/pulls/4179 | 未指定                                                     | 未指定   |
| 解决按需回放redo阶段，未升主备机lsn不一致的问题              | https://gitee.com/opengauss/openGauss-server/pulls/4166 | I82MIV                                                     | 次要     |
| 【资源池化】SSWaitIOTimeout修复+DMS推点                      | https://gitee.com/opengauss/openGauss-server/pulls/4219 | I84GE1                                                     | 次要     |
| 修改gs_ctl内存泄漏问题                                       | https://gitee.com/opengauss/openGauss-server/pulls/4238 | 未指定                                                     | 未指定   |
| 打开dms时，数据库只能使用段页式存储，所以修改默认模式为段页式存储提升易用性 | https://gitee.com/opengauss/openGauss-server/pulls/3507 | I70AC3                                                     | 未指定   |
| 【资源池化】【bugfix】解决按需回放内存配置比实际回放内存小时，回放卡住及回放失败的问题 | https://gitee.com/opengauss/openGauss-server/pulls/3765 | I7KJ47 I7IKSX                                              | 主要     |
| ss probackup适配double write initdb的调整                    | https://gitee.com/opengauss/openGauss-server/pulls/4198 | I82E6J                                                     | 次要     |
| 资源池化回合5.0.1-pg_controldata预留双集群模式               | https://gitee.com/opengauss/openGauss-server/pulls/3906 | 未指定                                                     | 未指定   |
| 【资源池化】解决主机新加段页式文件，备机更新时没有初始化的问题 | https://gitee.com/opengauss/openGauss-server/pulls/4126 | I7ZBPN I7ZIQZ                                              | 次要     |
| 【资源池化】优化cm_agent获取快照逻辑，不走dms，减少cm_agent获取状态异常的场景 | https://gitee.com/opengauss/openGauss-server/pulls/4045 | I7WQZB                                                     | 主要     |
| 5.0.0版本默认发布包加上xlogdump和pagehack工具                | https://gitee.com/opengauss/openGauss-server/pulls/4284 | I7LSPQ                                                     | 不重要   |
| 【回合】实现dolphin插件基于cmakelists.txt的轻量版安装包编译  | https://gitee.com/opengauss/openGauss-server/pulls/3397 | I6ZFRO                                                     | 未指定   |
| 修复小型化版本带dolphin插件升级失败的问题                    | https://gitee.com/opengauss/openGauss-server/pulls/4210 | I845ZN                                                     | 次要     |
| 升级dolphin5.0.1版本的版本号从1.1变更为1.2，修复5.0.1-》5.1.0回滚失败问题 | https://gitee.com/opengauss/Plugin/pulls/1070           | 未指定                                                     | 未指定   |
| 修复B兼容性数据库逻辑解码结果错误的问题                      | https://gitee.com/opengauss/openGauss-server/pulls/4250 | I869P7                                                     | 未指定   |
| 解决sql_mode_full_group关闭下，对没值的列使用聚合函数报错，与MySQL输出不一致 | https://gitee.com/opengauss/openGauss-server/pulls/4142 | I7URBV                                                     | 不重要   |
| 记录query的parsetree nodetag                                 | https://gitee.com/opengauss/openGauss-server/pulls/4085 | I7NX0C                                                     | 不重要   |
| 【资源池化】修复频繁kill备机触发full clean导致extend中的页面走了rebuild | https://gitee.com/opengauss/openGauss-server/pulls/4323 | #I88Y9S                                                    | 次要     |
| 【回合5.0.0】修改txn redo线程确认redo work线程确认lsn的方式  | https://gitee.com/opengauss/openGauss-server/pulls/4315 | #I87OYH                                                    | 次要     |
| issue修复：gs_basebackup备份时pg_xlog/archive_status缺失导致备份失败问题修复 | https://gitee.com/opengauss/openGauss-server/pulls/4308 | #I87W9N                                                    | 主要     |
| 【master回合5.0.0】Rename支持修改表的schema                  | https://gitee.com/opengauss/openGauss-server/pulls/4316 | I6KIBM                                                     | 未指定   |
| 【5.0.0回合】按需回放bugfix回合5.0.0分支                     | https://gitee.com/opengauss/openGauss-server/pulls/4310 | #I88PBI #I88MZA                                            | 次要     |
| 【5.0.0】 修复第一轮按需回放失败后，备机failover时备节点core掉的问题 | https://gitee.com/opengauss/openGauss-server/pulls/4306 | #I8735J                                                    | 次要     |
| 【测试类型：故障注入】【测试版本：5.0.1】【可靠性】【概率问题】备机重建过程中ctl+c故障后，1h无返回结果。再次重建失败后，stop集群时，主机无法stop | https://gitee.com/opengauss/openGauss-server/pulls/4554 | #I894YC                                                    | 次要     |
| 【测试类型：SQL功能】【测试版本：5.0.1】【自动化】  5.0.1金融版本进行alter server操作，报错“ERROR: invalid option "krbsrvname"” | https://gitee.com/opengauss/openGauss-server/pulls/4629 | https://gitee.com/opengauss/openGauss-server/issues/I8O2Q4 | 次要     |
| 【测试类型：SQL功能】【测试版本：5.0.1】【概率失败问题】执行建表建索引、删除表操作后，重启集群，备机均无法start，pg日志报错“PANIC: The Page's LSN[15026772743224134984] bigger  than want set LSN [353026928]” | https://gitee.com/opengauss/openGauss-server/pulls/4503 | https://gitee.com/opengauss/openGauss-server/issues/I89N9K | 次要     |
| 【测试类型：故障注入】【测试版本：5.0.1】【可靠性】【概率问题】备机重建过程中ctl+c故障后，1h无返回结果。再次重建失败后，stop集群时，主机无法stop | https://gitee.com/opengauss/openGauss-server/pulls/4571 | https://gitee.com/opengauss/openGauss-server/issues/I894YC | 次要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】3.x（带cm）升级至5.0.1（带cm），升级提交后一段时间，CM集群主备发生切换 | https://gitee.com/opengauss/openGauss-OM/pulls/606      | https://gitee.com/opengauss/openGauss-server/issues/I88Y89 | 次要     |
| 【测试类型：兼容性】【测试版本：5.0.0】1主2备环境经过业务后突然3台机器出现Standby  need repair状态[zyzx] | https://gitee.com/opengauss/openGauss-server/pulls/4473 | https://gitee.com/opengauss/openGauss-server/issues/I8AERQ | 次要     |
| \|\|用法不兼容                                               | https://gitee.com/opengauss/Plugin/pulls/1144           | https://gitee.com/opengauss/openGauss-server/issues/I8EQMT | 次要     |
| 使用create  table ... like ... 语法创建表时，新创建的表字段属性与原表不一致 | https://gitee.com/opengauss/Plugin/pulls/1139           | https://gitee.com/opengauss/openGauss-server/issues/I8AGOT | 不重要   |
| 【测试类型：SQL功能】【测试版本：5.0.1】【自动化】执行hash索引相关用例后，备机重启异常，产生core | https://gitee.com/opengauss/openGauss-server/pulls/4527 | https://gitee.com/opengauss/openGauss-server/issues/I8KRXY | 主要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】  3.0.3(带cm)就地升级到5.0.1(带cm)后cms core | https://gitee.com/opengauss/openGauss-OM/pulls/629      | https://gitee.com/opengauss/openGauss-server/issues/I8H27X | 主要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】  2.0.1就地升级5.0.1，提交升级时启库失败，产生core | https://gitee.com/opengauss/openGauss-OM/pulls/634      | https://gitee.com/opengauss/openGauss-server/issues/I8KUD7 | 主要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】  2.0.4/2.0.5(不带cm)灰度地升级5.0.1(带cm)，提交/回滚失败 | https://gitee.com/opengauss/openGauss-server/pulls/4634 | https://gitee.com/opengauss/openGauss-server/issues/I8LUVZ | 次要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】3.1.0(带cm)灰度升级5.0.1(带cm)后dn节点切换 | https://gitee.com/opengauss/CM/pulls/167                | https://gitee.com/opengauss/openGauss-server/issues/I8ML3D | 次要     |
| 【测试类型：工具功能】【测试版本：5.0.1】【升级】3.1.0(带cm)灰度升级5.0.1(带cm)后强制回滚，回滚过程中报错，dolphin版本未回滚成功 | https://gitee.com/opengauss/openGauss-OM/pulls/640      | https://gitee.com/opengauss/openGauss-server/issues/I8MLAX | 次要     |


### OM仓库回合缺陷列表

| 标题                                                         | 原始PR                                             | ISSUE                                                   | 问题级别 |
| ------------------------------------------------------------ | -------------------------------------------------- | ------------------------------------------------------- | -------- |
| 【opengauss】【fixbug】修复dssserver拉起后，暂时不可用的问题 | https://gitee.com/opengauss/openGauss-OM/pulls/484 | https://e.gitee.com/opengaussorg/dashboard?issue=I7BZWP | 主要     |
| 3.0.3new就地升级到5.0.0报错删除索引不存在                    | https://gitee.com/opengauss/openGauss-OM/pulls/460 | https://e.gitee.com/opengaussorg/dashboard?issue=I6SWZA | 主要     |
| 【opengauss】【fixbug】 修复无法清理升级清理GAUSSHOME/bin的问题 | https://gitee.com/opengauss/openGauss-OM/pulls/479 | https://e.gitee.com/opengaussorg/dashboard?issue=I71U1X | 次要     |
| 【opengauss】【fixbug】回退A4的设置项以及A10的检查项         | https://gitee.com/opengauss/openGauss-OM/pulls/478 | https://e.gitee.com/opengaussorg/dashboard?issue=I6XRA7 | 次要     |
| om安装，添加PGDATA环境变量；修改azPriority优先级相同增加报错提示 | https://gitee.com/opengauss/openGauss-OM/pulls/467 | https://e.gitee.com/opengaussorg/dashboard?issue=I6Y32M | 次要     |
| 修复打开uppercase_attribute_name后，执行gs_om -t status和gs_om restart失败的问题 | https://gitee.com/opengauss/openGauss-OM/pulls/466 | https://e.gitee.com/opengaussorg/dashboard?issue=I6YO0J | 次要     |
| 在preinstall开始，添加os和包架构的是否一致的判断             | https://gitee.com/opengauss/openGauss-OM/pulls/462 | https://e.gitee.com/opengaussorg/dashboard?issue=I6UYKC | 次要     |
| gs_sdr搭建流式集群设置most_available_sync                    | https://gitee.com/opengauss/openGauss-OM/pulls/450 | https://e.gitee.com/opengaussorg/dashboard?issue=I6TBNH | 次要     |
| 修改CheckEtcHosts检查逻辑                                    | https://gitee.com/opengauss/openGauss-OM/pulls/449 | https://e.gitee.com/opengaussorg/dashboard?issue=I6QTQ3 | 次要     |
| 修改getNetWorkConfFile方法中大小写不一致                     | https://gitee.com/opengauss/openGauss-OM/pulls/441 | https://e.gitee.com/opengaussorg/dashboard?issue=I6RMEX | 次要     |
| 恢复global_syscache默认为on                                  | https://gitee.com/opengauss/openGauss-OM/pulls/458 | https://e.gitee.com/opengaussorg/dashboard?issue=I6VUC6 | 不重要   |
| 对Resetreplconninfo.py判断进行加固，避免出现空指针问题       | https://gitee.com/opengauss/openGauss-OM/pulls/509 | 未指定                                                  | 未指定   |
| 扩容节点设置hba认证，trust方式指定管理用户替换all            | https://gitee.com/opengauss/openGauss-OM/pulls/504 | https://e.gitee.com/opengaussorg/dashboard?issue=I7FY6H | 未指定   |
| fix(TaskPool):修复执行ssh命令时找不到ssh可执行文件的问题     | https://gitee.com/opengauss/openGauss-OM/pulls/447 | https://e.gitee.com/opengaussorg/dashboard?issue=I6ULHA | 未指定   |
| 修复3.0.0-3.1.0-5.1.0跨版本就地升级失败问题                  | https://gitee.com/opengauss/openGauss-OM/pulls/577 | https://e.gitee.com/opengaussorg/dashboard?issue=I81P6C | 未指定   |
| 修复gs_sdr start \| stop 支持 --json 配置                    | https://gitee.com/opengauss/openGauss-OM/pulls/577 | https://e.gitee.com/opengaussorg/dashboard?issue=I81JXU | 未指定   |
| 资源池化支持xlog配置在一个LUN                                | https://gitee.com/opengauss/openGauss-OM/pulls/501 | 未指定                                                  | 未指定   |
| 修复获取私有卷失败                                           | https://gitee.com/opengauss/openGauss-OM/pulls/558 | I7WTE9                                                  | 主要     |

### CM仓库回合缺陷列表

| pull_title                                        | pull_url                                       | ISSUE                                                   | 问题级别 |
| ------------------------------------------------- | ---------------------------------------------- | ------------------------------------------------------- | -------- |
| 修复dss注册失败，无法踢出集群问题                 | https://gitee.com/opengauss/CM/pulls/132       | https://e.gitee.com/opengaussorg/dashboard?issue=I78PJL | 次要     |
| start资源添加-u参数                               | https://gitee.com/opengauss/CM/pulls/125       | 未指定                                                  | 未指定   |
| 共享存储启动dss前，调用reg接口                    | https://gitee.com/opengauss/CM/pulls/127       | https://e.gitee.com/opengaussorg/dashboard?issue=I70L68 | 次要     |
| pom.xml内版本依赖问题更新                         | https://gitee.com/opengauss/CM-RestAPI/pulls/6 | https://e.gitee.com/opengaussorg/dashboard?issue=I798Q2 | 未指定   |
| 适配开启数据库参数uppercase_attribute_name        | https://gitee.com/opengauss/CM/pulls/124       | https://e.gitee.com/opengaussorg/dashboard?issue=I72BZW | 次要     |
| 修复cm_ctl远程设置event_triggers失败的问题        | https://gitee.com/opengauss/CM/pulls/123       | https://e.gitee.com/opengaussorg/dashboard?issue=I71G1W | 次要     |
| 支持配置等待静态主的时间                          | https://gitee.com/opengauss/CM/pulls/122       | https://e.gitee.com/opengaussorg/dashboard?issue=I71NS5 | 未指定   |
| 修复资源泄漏                                      | https://gitee.com/opengauss/CM-RestAPI/pulls/8 | https://e.gitee.com/opengaussorg/dashboard?issue=I6WOH5 | 次要     |
| 修复resname为NULL导致段错误的问题                 | https://gitee.com/opengauss/CM/pulls/121       | https://e.gitee.com/opengaussorg/dashboard?issue=I6WIY6 | 未指定   |
| 最大集群仲裁，校验agent网络连通性过程原子化       | https://gitee.com/opengauss/CM/pulls/117       | https://e.gitee.com/opengaussorg/dashboard?issue=I6WBBX | 未指定   |
| 【轻量级 PR】: 添加了指针释放，修复了部分内存泄漏 | https://gitee.com/opengauss/CM/pulls/120       | https://e.gitee.com/opengaussorg/dashboard?issue=I6WUDA | 次要     |
| 【轻量级 PR】：磁盘心跳，每次读64M，占用带宽较多  | https://gitee.com/opengauss/CM/pulls/115       | https://e.gitee.com/opengaussorg/dashboard?issue=I6R77W | 次要     |
| 修复cm_ctl工具检验结果有误的问题                  | https://gitee.com/opengauss/CM/pulls/149       | I7PXE9                                                  | 不重要   |
| 修复dss僵死检测                                   | https://gitee.com/opengauss/CM/pulls/150       | I817VH                                                  | 次要     |
| 适配mes                                           | https://gitee.com/opengauss/CM/pulls/148       | I82DUX                                                  | NA       |
| 同步close file日志修改                            | https://gitee.com/opengauss/DSS/pulls/261      | #I87H4O                                                 | 次要     |
| 集群kill进程后，dss产生mes-channel的core          | https://gitee.com/opengauss/CBB/pulls/97       | I87WBG                                                  | 主要     |

### JDBC回合列表

| pull_title                                                   | pull_url                                                     | ISSUE                                                        | 问题级别 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | -------- |
| 修复集群探测主节点执行sql时没有字符编码类型报错              | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/129 | https://e.gitee.com/opengaussorg/dashboard?issue=I71NDO      | 主要     |
| 【bugfix】修复leastconn模式并发场景下有小概率没有完全负载均衡的问题 | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/128 | https://e.gitee.com/opengaussorg/dashboard?issue=I70OYB      | 次要     |
| [bugfix] 修复b兼容模式下timestamp(0)类型查询时结果不正确的问题 | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/151 | https://e.gitee.com/opengaussorg/dashboard?issue=I7PAP9      | 未指定   |
| getBlob支持bytea/blob                                        | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/131 | https://e.gitee.com/opengaussorg/dashboard?issue=I7EYCF      | 未指定   |
| 修复字符集线程不安全导致不同类型字符集的数据库JDBC链接同时存在时会相互影响的问题 | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/127 | https://e.gitee.com/opengaussorg/dashboard?issue=I6ZNL8      | 未指定   |
| 修复setBinaryStream  重载方法没有对BLOB MODE逻辑生效的问题   | https://gitee.com/opengauss/openGauss-connector-jdbc/pulls/163 | https://gitee.com/opengauss/openGauss-connector-jdbc/issues/I76SGV | 不重要   |

### Plugin插件回合列表

| 描述                                                         | PR                                            | 关联issue                                               |
| ------------------------------------------------------------ | --------------------------------------------- | ------------------------------------------------------- |
| 兼容B库模式下，bigint unsigned类型转bigint类型部分结果与mysql不一致 | https://gitee.com/opengauss/Plugin/pulls/987  | https://e.gitee.com/opengaussorg/dashboard?issue=I7VCQ8 |
| 解决text类型隐式转换为bool与显示结果不一致的问题             | https://gitee.com/opengauss/Plugin/pulls/989  | https://e.gitee.com/opengaussorg/dashboard?issue=I7UOKW |
| 修复int16转换为int1/2/4/8, unsigned结果异常的问题            | https://gitee.com/opengauss/Plugin/pulls/998  | https://e.gitee.com/opengaussorg/dashboard?issue=I7X75N |
| 【mysql协议兼容】修复偶发的鉴权失败问题                      | https://gitee.com/opengauss/Plugin/pulls/1006 | NA                                                      |
| 修复cast as char问题                                         | https://gitee.com/opengauss/Plugin/pulls/1009 | https://e.gitee.com/opengaussorg/dashboard?issue=I7ZSA1 |
| 修复uint场景下的select case问题                              | https://gitee.com/opengauss/Plugin/pulls/1019 | https://e.gitee.com/opengaussorg/dashboard?issue=I81SO9 |
| 添加alter table rename new_tbl语法                           | https://gitee.com/opengauss/Plugin/pulls/1023 | https://e.gitee.com/opengaussorg/dashboard?issue=I81WCI |
| 支持ALTER TABLE ADD(col type), add(col type) 语法            | https://gitee.com/opengauss/Plugin/pulls/1020 | https://e.gitee.com/opengaussorg/dashboard?issue=I81VS8 |
| 解决load data导入空值报错的问题                              | https://gitee.com/opengauss/Plugin/pulls/1030 | https://e.gitee.com/opengaussorg/dashboard?issue=I81LJC |
| 修复time_bool&date_bool                                      | https://gitee.com/opengauss/Plugin/pulls/1035 | https://e.gitee.com/opengaussorg/dashboard?issue=I81O5A |
| 修复auto_increment引用的问题                                 | https://gitee.com/opengauss/Plugin/pulls/1018 | https://e.gitee.com/opengaussorg/dashboard?issue=I7ZDIF |
| timediff函数一个参数为date，另一个参数不指定类型时结果有误   | https://gitee.com/opengauss/Plugin/pulls/1016 | https://e.gitee.com/opengaussorg/dashboard?issue=I7YD68 |
| 修复default默认值导出带括号的问题                            | https://gitee.com/opengauss/Plugin/pulls/1033 | https://e.gitee.com/opengaussorg/dashboard?issue=I81OI7 |
| 修复B兼容模式json字段操作问题                                | https://gitee.com/opengauss/Plugin/pulls/1042 | https://e.gitee.com/opengaussorg/dashboard?issue=I80P2I |
| 修复unix_timestamp函数指定不同时区——返回值跟mysql不相符      | https://gitee.com/opengauss/Plugin/pulls/1039 | https://e.gitee.com/opengaussorg/dashboard?issue=I82VAH |
| 修复mysql兼容性-timediff函数，入参类型非法，返回结果错误的问题 | https://gitee.com/opengauss/Plugin/pulls/1036 | https://e.gitee.com/opengaussorg/dashboard?issue=I7YD3T |
| 修复only full group by在min/max场景下的优化问题              | https://gitee.com/opengauss/Plugin/pulls/1046 | https://e.gitee.com/opengaussorg/dashboard?issue=I83ODD |
| 修复数字转date表现                                           | https://gitee.com/opengauss/Plugin/pulls/1047 | https://e.gitee.com/opengaussorg/dashboard?issue=I83I9E |
| 添加b库timestamp(tz)类型时区解析                             | https://gitee.com/opengauss/Plugin/pulls/1049 | https://e.gitee.com/opengaussorg/dashboard?issue=I7E49X |
| 严格模式区分SELECT和IUD                                      | https://gitee.com/opengauss/Plugin/pulls/1017 | I7NX0C                                                  |
| 支持sql_mode ERROR_FOR_DIVISION_BY_ZERO，除0不报错           | https://gitee.com/opengauss/Plugin/pulls/1024 | I82O75                                                  |
| 升级5.0.1版本的版本号从1.1变更为1.2，修复5.0.1-》5.1.0回滚失败问题 | https://gitee.com/opengauss/Plugin/pulls/1070 | NA                                                      |
| 实现dolphin插件基于cmakelists.txt的轻量版安装包编译          | https://gitee.com/opengauss/Plugin/pulls/811  | I6ZFRO                                                  |
| 【测试类型：SQL功能】【测试版本：5.0.1】【自动化】  问题描述 部分函数返回结果错误 | https://gitee.com/opengauss/Plugin/pulls/1194 | https://gitee.com/opengauss/Plugin/issues/I8KY31        |



### 其他仓库

以下仓库，除了需求外，均从5.1.0同步回合

| 组件 | 仓库        |
| ---- | ----------- |
| DDES | CBB         |
|      | DCC         |
|      | DCF         |
|      | DSS         |
|      | DMS         |
| 工具 | debezium    |
|      | datachecker |
|      | chameleon   |

### 遗留问题

本次主要遗留问题为资源池化相关的问题单，不开启此特别则不受下面问题单影响。

| 问题ID | 问题描述                                                     | 级别 |
| ------ | ------------------------------------------------------------ | ---- |
| I6DRSA | 【测试类型：功能】【测试版本：5.0.0】【GSC】线程池模式下，打开enable_global_syscache，进行新库创建后，连接库进行创建表操作时，建连报错:gsql: ERROR: aquire wrlock failed | 次要 |
| I88GMF | 【测试类型：功能测试】【测试版本：5.0.1】【资源池化】stop，start之后节点core掉 | 次要 |
| I8BHFZ | 【测试类型：压力长稳】【测试版本：5.0.1】【资源池化】稳定性测试6*24H后cm倒换导致集群failover | 次要 |
| I8EIOE | 【测试类型：功能测试】【测试版本：5.0.1】【资源池化】kill 主节点gaussdb进程，产生extreme_rto not mark dirty的core | 次要 |
| I8F6DI | 【测试类型：压力长稳】【测试版本：5.0.1】传统数据库稳定性测试，备机xlog回收速度慢，导致xlog文件膨胀，磁盘占用过大 | 主要 |
| I8KO5F | 【测试类型：SQL功能】【测试版本：5.0.1】【资源池化】sysbench主机读写，备机读，执行DDL 产生FreeMemoryContextList的core | 次要 |
| I8KRHI | 【测试类型：压力长稳】tpcc1000仓长稳测试时，连跑11h小时后报错 | 次要 |
| I8KT78 | 【测试类型：功能测试】【测试版本：5.0.1】【需求名称：资源池化】集群switchover+kill 进程，，备机出现core | 主要 |
| I8KU3S | 【测试类型：压力长稳】tpcc1000仓长稳测试时，连跑18h小时后出现等锁超时 | 主要 |
| I8KXYM | 【测试类型：SQL功能】【测试版本：5.0.1】【资源池化】集群starting中再次执行stop，start集群操作，同时执行cursor语句，产生lsn check error的core | 主要 |
| I8L21S | 【测试类型：功能测试】【测试版本：5.0.1】【资源池化】failover后主备节点产生now lsn(0x3764f46e8) is less than past lsn(0x3779cd448)的core | 次要 |
| I8LWO6 | 【测试类型：SQL功能】【测试版本：5.0.1】【资源池化】kill gaussdb进程，集群恢复后执行stop，start集群操作，产生core | 主要 |
| I8LX4D | 【测试类型：工具功能】【测试版本：5.0.1】【资源池化升级】 5.0.1升级到5.1.1时（就地升级），升级过程中，集群状态异常，不能正常拉起 | 次要 |
| I8M95Z | 【测试类型：功能测试】【测试版本：5.0.1】【资源池化】kill掉备节点dss进程后，dn无法加回集群，状态为starting(建立tcp链接失败) | 次要 |