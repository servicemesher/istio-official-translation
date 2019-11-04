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

所有的中文标题都要补充英文锚点，如英文标题为 `Before you begin`，则中文翻译的标题应该为`开始之前{#before-you-begin}`，其中锚点及所有英文单词的小写，空格以连字符替代，如遇到复杂格式，请在 <https://istio.io> 上要翻译的英文原文查看英文锚点。

## 关于文章头信息

很多文章头部有 YAML 格式的配置信息，其中 `aliases` 是用于访问历史链接跳转的，若该配置为 `/docs/tasks/request-routing.html`，则在其中加上中文前缀 `/zh/docs/tasks/request-routing.html`，若 aliases 配置中有多个值，则需要每个值都加上 `/zh` 语言前缀。

## 常用词汇

常用词汇指常见的技术类词汇，使用本表格中固定、统一的译文。

- Transport Layer Security：传输层安全
- application：应用/应用程序
- authentication：认证
- authorization：授权
- automatic retry：自动重试
- bulkheading：隔离层
- canary rollout：金丝雀发布
- caveat：注意事项
- circuit breaker：熔断器
- cleanup：清除
- client-side load balancing：客户端负载均衡
- cloud native：云原生
- configure / configuartion：配置
- container orchestration framework：容器编排框架
- connection timeout：连接超时
- control plane：控制平面
- data plane：数据平面
- distributed tracing：分布式追踪
- fault injection：故障注入
- infrastructure：基础设施
- microservice：微服务
- mount：挂载
- mutual TLS：双向TLS
- namespace：命名空间
- organizational policy：组织策略
- policy：策略
- proxy：代理
- remote：远程
- rule evaluation：告警规则（Prometheus 中的术语）
- retry quota/budget：重试配额/预算
- service account：服务帐户（Kubernetes中的资源对象）
- service mesh：服务网格
- service：服务
- setting：设置
- target scrape：采样目标
- traffic：流量
- traffic routing：流量路由
- traffic shadowing：流量复制（动词），影子流量（名词）
- validate：验证
- monolithic application：单体应用
- observability：可观测性
- integrate / integration：整合
- Pluggable：可拔插的
- plugin / addon：插件
- logging：（记录）日志
- customization：定制
- Architecture：架构
- Adapter：适配器
- Load balancing / load balancer：负载均衡 / 负载均衡器
- Health checks：健康检查
- metric / metrics：指标
- telemetry：遥测
- service registry、discovery：服务注册、发现
- resilience：弹性
- rate limiting：速率限制
- High-level：高阶
- On-premise：物理机，实体机
- On-premises machines scenario：物理机场景
- scenario：场景
- Best practices：最佳实践
- latency：延迟
- benchmark：基准测试
- workload：工作负载
- multi-Tenancy：多租户
- Prerequisites：前提条件
- Traffic Shifting：流量转移
- Mirroring：（流量）镜像
- end-user：终端用户
- Deep-Dive：深入
- Statistics：统计
- Troubleshooting：问题排查

## 术语

术语：特定的专有技术名词，或 Istio 中特定的词汇、关键字，使用原文；例如：Mixer

- Pilot
- Mixer
- Citadel
- Galley
- Envoy
- sidecar
- ingress / egress
- span
- endpoint
- log
- TLS / mTLS
- gRPC
- Kubernetes
- Pod
- Node
- Deployment
- CRD
- Virtual service
- Destination rule
- Service entry
- Gateway
- Denials
- Operator
- CLI
- release
- Host
- webhook
- HTTP header
- productpage 示例服务名
- ratings 示例服务名
- reviews 示例服务名