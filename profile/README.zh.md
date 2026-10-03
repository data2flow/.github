<div align="center">

🌐 **[한국어](./README.md)** | **[English](./README.en.md)** | **[日本語](./README.ja.md)** | **简体中文**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.svg">
  <img alt="data2flow" src="./logo-light.svg" width="300">
</picture>

**只会盯着看的运维已经结束。现在，它会自己解决问题。**

只需配置即可接入、整理、分析楼宇内的传感器数据，<br>并根据结果驱动设备的 AIoT 平台

</div>

---

## data2flow 是什么

> 实训室的 CO2 超过 1,000ppm 的状态持续了 5 分钟。<br>
> → data2flow 检测到后打开通风设备。<br>
> → 如果 15 分钟内没有下降，就向负责人发送“控制无效”通知。<br>
> → 一个月后，用报告展示超标时间减少了多少。

整个过程无需部署代码，**在界面上通过配置和流程图** 完成。正如其名，**data** 沿着 **flow** 依次经过清洗 → 分析 → 行动。

## 五个阶段

| 阶段 | 内容 |
|---|---|
| **接入** | 仅通过界面配置接入 LoRaWAN(ChirpStack)、MQTT、Webhook 和边缘网关传感器；从收到的数据中发现新设备，经管理员批准后注册 |
| **清洗** | 把各厂商不同的数据统一成同一格式：沙箱 JavaScript 脚本、质量代码、原始数据保存与重新处理 |
| **理解** | 选择即可运行的分析模板(舒适度、空间利用率、异常检测、能耗)，并由 AI 解释结果 |
| **行动** | 用流程编辑器和规则进行检测，通过与厂商无关的统一控制入口驱动设备，并通过 Telegram 通知 |
| **复现** | 没有真实设备也能先在虚拟空间、虚拟传感器和场景中验证自动化 |

## 有何不同

- **测量 → 标准 → 行动 → 证明** 在一个产品中贯通，直至室内空气质量达标判定和合规报告。
- **零数据丢失、零停机部署。** 即使在重新部署期间，也不会丢失任何一条消息。
- **实时编辑。** 修改流程后无需停止引擎即可立即生效。
- **厂商中立的控制。** 通过 Capability + Driver + Control Facade，界面、流程和 AI 使用同一个控制入口。
- **开源许可证政策。** 产品中只包含 Apache、MIT、BSD 等宽松许可证的组件。

## 代码仓库

| 仓库 | 作用 | 技术 |
|---|---|---|
| data2flow-web | 界面 + BFF(服务端渲染、会话) | React Router v7, TypeScript |
| data2flow-api-gateway | 路由、令牌校验、身份传递 | Spring Cloud Gateway |
| data2flow-auth | 登录、令牌签发与吊销 | Spring Boot 4 |
| data2flow-core-api | 用户、设备、空间、数据源、流程定义、规则、仪表盘 | Spring Boot 4 |
| data2flow-ingress | MQTT 订阅、Webhook 与边缘接入 | Spring Boot 4 |
| data2flow-pipeline | 解码、脚本、存储、聚合 | Spring Boot 4, GraalJS |
| data2flow-flow-engine | 流程与规则执行、热重载 | Spring Boot 4, GraalJS |
| data2flow-action | 设备控制、通知、外部输出 | Spring Boot 4 |
| data2flow-simulator | 虚拟空间、传感器、设备与场景 | Spring Boot 4 |
| data2flow-ai | 结果解读、报告、聊天机器人、MCP 服务器 | Spring AI |
| data2flow-analytics | 分析模板、实时推理 | Python, FastAPI |
| data2flow-contracts | 消息模式、通用响应与错误格式 | Java, JSON Schema |

## 技术栈

`React Router v7` `TypeScript` `Spring Boot 4` `Java 21` `Spring AI` `Python FastAPI` `PostgreSQL 18 + pgvector` `RabbitMQ Streams` `Redis` `GraalJS` `Kubernetes` `Argo CD`

## 版本发布

每个版本都以 4 种语言(한국어 · English · 日本語 · 简体中文)发布版本说明，并在所有服务仓库打上相同的 git 标签(`vX.Y`)。目前尚未发布第一个版本。

## 当前阶段

我们以文档优先的方式推进。已完成 763 条规格、1,096 条验收测试、155 个画面的故事板、ERD 以及 OpenAPI/AsyncAPI 规格，正在准备第一个实现里程碑(M0)。

<div align="center"><sub>Made at NHN Academy · data → flow</sub></div>
