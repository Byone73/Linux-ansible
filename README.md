# Linux Ansible 自动化项目

## 项目简介
本项目用于自动化部署LNMP环境（Linux + Nginx + MySQL + PHP），适用于快速搭建Web服务器环境。

## 环境要求
- Ubuntu 22.04
- Ansible 2.x

## 快速开始

### 1. 安装Ansible
`bash
sudo apt update
sudo apt install ansible -y
`

### 2. 执行Playbook
`bash
ansible-playbook -i inventory.yml deploy_lnmp.yml -K
`

## 功能说明
- 自动安装Nginx、MySQL 8.0、PHP 8.1
- 自动配置Nginx支持PHP解析
- 创建phpinfo测试页面用于验证

## 验证部署
`bash
curl http://localhost/info.php | head -10
`

## 项目结构
` `
├── deploy_lnmp.yml   # LNMP部署Playbook
├── inventory.yml     # 主机清单文件
└── .gitignore        # Git忽略配置
