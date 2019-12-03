## 翻译约定和术语表

以下短语翻译约定：

- before you begin 开始之前
- further reading 进阶阅读
- next step 下一步
- understanding What happened 理解原理

## 格式约定

- 中文和英文之间加空格
- 中文标点与英文之间**不需要**加空格
- 中文与数字之间、英文与数字之间都**需要**加空格。
- 出现并列的词请使用中文顿号

## 关于锚点

**请不要翻译英文锚点。**

所有的中文标题都要补充英文锚点，如英文标题为 `Before you begin`，则中文翻译的标题应该为`开始之前{#before-you-begin}`，其中锚点及所有英文单词的小写，空格以连字符替代。

下面是一些锚点的例子，这里主要讨论锚点 `{#}` 里面的内容，如遇到复杂格式，请在 [Istio](https://istio.io) 上找到要翻译的英文原文查看英文锚点。

#### 专有名词

`TLS` `Delayering` `RPCs` 等专有名词，由于拼写检查的原因，在添加锚点时，请保持原文，该规则仅限于中文文档。

`TCP` `AppSwitch` 等专有名词，由于同时存在对应的小写专有名词：`tcp` `appswitch`，在添加锚点时，可以修改为小写。

完整的专有名词列表请参考：[.spelling](https://github.com/istio/istio.io/blob/master/.spelling)。

#### 符号名词

使用 `` ` `` (反引号) 包裹的名词，这种名词一般不翻译、不能通过拼写检查、且不在 `专有名词` 列表内，所以需要将其包裹在 `` ` `` 内，如：`Kubectl` `Istioctl` `DaemonSet` 等，此时处理锚点分为以下几种情况：

1.如果该标题整体不需要翻译，请保持原文，Istio 会自动生成正确的锚点，如：

`` AppSwitch `DaemonSet` `` 自动生成 -> `appswitch-daemonset`，[参考链接](https://istio.io/blog/2018/delayering-istio/#appswitch-daemonset)。

2.如果该标题部分需要翻译，添加的锚点忽略使用反引号 `` ` `` 包裹的部分，如：

`` `Istioctl` auto-completion `` -> `auto-completion`，完整标题类似于：``## `Istioctl` 自动补全{#auto-completion} ``，[参考链接](https://preliminary.istio.io/zh/docs/ops/diagnostic-tools/istioctl/#auto-completion)。

3.使用 `` ` `` (反引号) 包裹的 `短语`，此时可以将其视作 `忽略字符`，如：

`` `no such hosts` or `no endpoints available` errors in deployment status `` -> `no-such-hosts-or-no-endpoints-available-errors-in-deployment-status`，[参考链接](https://preliminary.istio.io/zh/docs/ops/common-problems/injection/#no-such-hosts-or-no-endpoints-available-errors-in-deployment-status)。

#### 忽略字符

`,` `:` `+` `"` `?` `&` 等字符直接忽略，如：

`Zero-cost load balancer, firewall and network analyzer` -> `zero-cost-load-balancer-firewall-and-network-analyzer`，[参考链接](https://preliminary.istio.io/zh/docs/ops/diagnostic-tools/istioctl-analyze/#analyzing-live-clusters-local-files-or-both)。

`The solution: secure control of egress traffic` -> `the-solution-secure-control-of-egress-traffic`，[参考链接](https://istio.io/blog/2019/egress-traffic-control-in-istio-part-1/#the-solution-secure-control-of-egress-traffic)。

`Namespace level segmentation via RBAC + conditions` -> `namespace-level-segmentation-via-rbac-conditions`，[参考链接](https://istio.io/blog/2018/istio-authorization/#namespace-level-segmentation-via-rbac-conditions)。

`“Sidecar-aware” applications` -> `sidecar-aware-applications`，[参考链接](https://istio.io/blog/2018/delayering-istio/#sidecar-aware-applications)。

`So what’s the net?` -> `so-what-s-the-net`，[参考链接](https://istio.io/blog/2018/delayering-istio/#so-what-s-the-net)。

`Q&A` -> `q-a`，[参考链接](https://preliminary.istio.io/zh/docs/ops/diagnostic-tools/istioctl-analyze/#q-a)。
  
#### 分隔符

`.` `/` `'`(单引号) 等字符视作分隔符，将单词分割为两个单词，并用中划线 `-` 连接，如：

`Istio 1.1 performance enhancements` -> `istio-1-1-performance-enhancements`，[参考连接](https://istio.io/blog/2019/istio1.1_perf/#istio-1-1-performance-enhancements)。

`Google Cloud Pub/Sub` -> `google-cloud-pub-sub`，[参考链接](https://istio.io/blog/2018/export-logs-through-stackdriver/#google-cloud-pub-sub)。

`It’s not just about performance` -> `it-s-not-just-about-performance`，[参考连接](https://istio.io/blog/2018/delayering-istio/#it-s-not-just-about-performance)。

## 关于文章头信息

很多文章头部有 YAML 格式的配置信息，其中 `aliases` 是用于访问历史链接跳转的，若该配置为 `/docs/tasks/request-routing.html`，则在其中加上中文前缀 `/zh/docs/tasks/request-routing.html`，若 aliases 配置中有多个值，则需要每个值都加上 `/zh` 语言前缀。

## 常用词汇

常用词汇指常见的技术类词汇，使用本表格中固定、统一的译文。

- adapter：适配器
- application：应用/应用程序
- architecture：架构
- authentication：认证
- authorization：授权
- automatic retry：自动重试
- benchmark：基准测试
- best practices：最佳实践
- bulkheading：隔离层
- canary rollout：金丝雀发布
- caveat：注意事项
- circuit breaker：熔断器
- cleanup：清除
- client-side load balancing：客户端负载均衡
- cloud native：云原生
- configure / configuration：配置
- connection timeout：连接超时
- customization：定制
- container orchestration framework：容器编排框架
- control plane：控制平面
- data plane：数据平面
- deep-dive：深入
- distributed tracing：分布式追踪
- end-user：终端用户
- fault injection：故障注入
- health checks：健康检查
- high-level：高阶
- infrastructure：基础设施
- integrate / integration：整合
- key/cert 密钥/证书
- latency：延迟
- legacy：遗留
- load balancing / load balancer：负载均衡 / 负载均衡器
- logging：（记录）日志
- metric / metrics：指标
- microservice：微服务
- mirroring：（流量）镜像
- monolithic application：单体应用
- mount：挂载
- multi-Tenancy：多租户
- mutual TLS：双向TLS
- namespace：命名空间
- observability：可观测性
- on-premise：物理机，实体机
- on-premises machines scenario：物理机场景
- organizational policy：组织策略
- pluggable：可拔插的
- plugin / addon：插件
- policy：策略
- prerequisites：前提条件
- proxy：代理
- rate limiting：速率限制
- remote：远程
- resilience：弹性
- retry quota/budget：重试配额/预算
- rule evaluation：告警规则（Prometheus 中的术语）
- scenario：场景
- service：服务
- service account：服务帐户（Kubernetes中的资源对象）
- service mesh：服务网格
- service registry、discovery：服务注册、发现
- setting：设置
- statistics：统计
- target scrape：采样目标
- telemetry：遥测
- traffic：流量
- traffic routing：流量路由
- traffic shadowing：流量复制（动词），影子流量（名词）
- traffic shifting：流量转移
- Transport Layer Security：传输层安全
- troubleshooting：问题排查
- validate：验证
- workload：工作负载
- you：您

## 术语

术语：特定的专有技术名词，或 Istio 中特定的词汇、关键字，使用原文；例如：Mixer

- Citadel
- CLI
- CRD
- Denials
- Deployment
- Destination rule
- endpoint
- Envoy
- Galley
- Gateway
- gRPC
- Host
- HTTP header
- ingress / egress
- Kubernetes
- log
- Mixer
- Node
- Operator
- Pilot
- Pod
- productpage 示例服务名
- ratings 示例服务名
- release
- reviews 示例服务名
- secrets
- Service entry
- sidecar
- span
- TLS / mTLS
- Virtual service
- webhook
