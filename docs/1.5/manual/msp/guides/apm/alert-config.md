# 告警策略

平台的稳定性是保障业务程序持续运行的基础。您可通过设置合适的告警机制保障业务程序及平台的稳定性，同时解放劳动力，无需时刻紧盯屏幕关注服务运行情况。

请进入 **微服务平台 > 项目列表 > 选择项目 > 告警中心 > 告警策略**，新建告警策略。

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/11/17/d11dd6e6-70b2-43e7-83e8-69dc1099976a.png)

如上图所示，若发生了应用错误次数告警，说明某个服务的异常次数已达到阀值，项目管理员和应用开发人员需关注程序中的逻辑是否有误。

若发生了应用实例 OOM 告警，则说明该服务的 erda.yml 配置内存过小，或服务有内存泄露，开发人员需调整内存，或检查是否有内存泄露的代码。

## 过滤规则

创建告警策略时，您可以按需添加一个或多个过滤规则。

* **多云管理平台**：过滤规则的可选标签为集群名、主机 IP 和平台组件。 

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/12/24/6810d211-43d4-45e9-b619-6bd66f31dc68.png)

* **微服务平台**：过滤规则的可选标签为应用名和服务名。

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/12/24/7570d254-e8f6-4d8d-a010-0d3b0fd8f032.png)

若您在告警策略中已添加过滤规则，则告警需同时满足过滤规则和告警规则才可触发。例如，过滤规则为集群名等于 terminus，则集群名需为 terminus 且满足相应告警规则才可触发告警及发送通知。

## 告警级别

在告警策略中添加告警规则时，支持告警级别和触发恢复设置，默认告警级别为故障且触发告警。

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/12/24/1d2f7f6e-a690-40b2-8238-61f8363b1bf0.png)

告警级别分为故障、严重、警告、提示，通知级别由高到低。您可以按需选择对应的告警级别和是否触发恢复。若启用触发恢复，则对应指标的数据低于设置值时将发送告警恢复通知。 

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/12/24/983eaf98-01b0-4cb0-b05b-1a9b7df0693b.png)

## 通知对象

您可以设置多个告警通知对象并选择对应级别，通知级别与告警规则的级别相同。

![](http://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/12/24/eaddb45c-8477-490a-a092-4f2ae6411446.png)

当通知对象中的级别包含告警规则级别时，该规则触发告警后将发送告警消息至对应通知对象。若您在同一告警策略中添加多条告警规则，且规则同时触发告警，则仅有高级别的告警规则可发送告警消息至同等级别的通知对象。
