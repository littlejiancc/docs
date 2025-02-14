# erda.yml

平台通过让开发者声明的方式，描述微服务运行的整体环境，并将该声明转化为环境搭建的过程。

<img src="https://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/08/23/25d12ec9-1904-4ff0-9df2-5d2c2164f701.png" style="zoom:50%;" />

YAML 文件的声明可分为以下两部分：

* 微服务声明，包括微服务数量，以及各微服务所需的资源、副本个数、端口、环境变量，甚至对外网关的域名、网关的转发设置。
* 扩展服务设置，即 Addon。开发者仅需声明应用涉及的 Addon，例如 MySQL，指明 MySQL 的规格、版本即可，平台将自动为应用创建 MySQL，并将其配置通过环境变量的方式传递至微服务。同时 Addon 支持扩展，通过这一开放途径，您几乎可以将所有中间件集成进平台。

或许您会有疑问，K8s 的 YAML 也是声明式的，为何不直接使用 K8s 的 YAML？在此需明确一点，即“关注点分离”。K8s 本身并不是面向开发者的平台，而是面向平台的平台，K8s YAML 中存在太多开发者无需关心的基础设施细节。

![](https://terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2021/08/23/9e186d95-90fb-4562-abda-911f5e786d7d.png)

通过 erda.yml 文件，开发者在中心平台经过验证的部署过程，无需修改，即可同时适配至客户环境，为一键部署打下基础。
