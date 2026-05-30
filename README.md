# Linux Ansible 自动化运维平台

基于 Ansible + Docker + Prometheus + Grafana 的一键自动化运维方案。

## 项目简介

本项目解决了手动部署环境繁琐、重复、易出错的问题，实现三个核心自动化场景：

- **Docker 自动化安装**：一键安装 Docker 并配置国内镜像加速
- **Web 服务自动化部署**：一键部署 Nginx 容器化服务
- **监控栈自动化部署**：一键部署 Prometheus + Grafana 监控体系

## 技术栈

| 类别 | 技术 |
|------|------|
| 自动化 | Ansible 2.x |
| 容器化 | Docker、Docker Compose |
| Web 服务 | Nginx |
| 监控 | Prometheus、Grafana、Node Exporter |


 快速开始

 环境要求

- Ubuntu 22.04 / 20.04
- 已配置 sudo 免密（推荐）

 1. 安装 Docker

bash

ansible-playbook install_docker.yml

2. 部署 Web 服务

bash

ansible-playbook deploy_web.yml

3. 部署监控栈
bash

ansible-playbook deploy_monitoring.yml

访问服务
服务	地址	账号/密码
Web 页面	http://localhost	-
Prometheus	http://localhost:9090	-
Grafana	http://localhost:3000	admin / admin

项目结构
├── install_docker.yml          # Playbook: 安装 Docker + 镜像加速
├── deploy_web.yml              # Playbook: 部署 Web 服务
├── deploy_monitoring.yml       # Playbook: 部署监控栈
├── monitoring/                 # 监控配置文件
│   ├── docker-compose.yml
│   └── prometheus/
│       └── prometheus.yml
└── myproject/                  # 示例 Web 应用
    ├── docker-compose.yml
    └── html/
        └── index.html
项目亮点:
    一键部署：三个核心场景全部自动化，无需人工干预

    幂等性设计：Playbook 可重复执行，不会产生错误或重复安装

    企业级监控：集成 Prometheus + Grafana，实时监控主机指标

    容器化运行：所有服务运行在 Docker 中，环境一致，易于迁移
