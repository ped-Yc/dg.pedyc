---
title: DevOps工作流
tags: [专业技术/DevOps工作流]
date-created: 2025-03-05
date-modified: 2025-03-11
refresh: 季度
type: [area]
---

## 专业技术领域/DevOps 工作流

### 🧱 核心组件

- [[CI/CD理论框架]]（领域基石：持续集成/持续部署原则、流水线设计模式）
- [[DevOps工具链]]（高频工具：GitHub Actions/Jenkins/Docker/K8s/Terraform）
- [[云原生最佳实践]]（实战宝典：容器化部署、不可变基础设施、混沌工程）

### 🔄 活跃连接

#### 进行中项目

- [[2025Q1-学习Docker]]（贡献组件：[[容器化部署checklist]]）
- [[2025Q1-学习GitHub Actions]]（产出物：[[自动化流水线设计文档]]）

#### 关联领域

- [[前端工程化]]
- [[云计算平台]]（协同点：基于 AWS/GCP 的流水线环境搭建）
- [[安全工程]]（冲突点：CI/CD 快速迭代与安全审计的平衡）

### 📚 资源金字塔

#### 🌟 顶级资产（★★★★★）

- [[DevOps工具链选型指南]]：含工具对比矩阵和适用场景决策树
- [[跨平台部署黄金模板]]：支持多云环境的 Terraform+Ansible 组合配置

#### 💼 实用工具（★★★☆☆）

- [[CI/CD速查手册]]：涵盖 YAML 语法速记/环境变量管理/密钥安全实践
- [[流水线排错QA]]：常见报错场景（如 OOMKilled/网络超时）的根因分析

#### 🧩 原始素材（★☆☆☆☆）

- [[CNCF年度报告]]：云原生技术趋势原始数据
- [[SRE团队会议纪要]]：关于部署频率与故障率的关联性讨论记录

### ⚠️ 前线战报

#### 近期挑战

- **技术变革**：Serverless 架构对传统流水线的冲击（需重构构建逻辑）
- **资源缺口**：缺乏 [[生产级K8s故障注入案例集]]

#### 开放问题

- 如何量化 CI/CD 改进对 MTTR（平均恢复时间）的影响？
- GitOps 模式在混合云环境中的落地验证
