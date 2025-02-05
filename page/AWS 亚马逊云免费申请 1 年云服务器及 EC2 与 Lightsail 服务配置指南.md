# AWS 亚马逊云免费申请 1 年云服务器及 EC2 与 Lightsail 服务配置指南

## 准备工作：外币信用卡

> 在使用海外服务时，通常需要外币信用卡进行支付。国内信用卡虽然部分支持外币支付，但仍可能无法用于某些国际服务。因此，建议使用虚拟信用卡平台作为支付工具。

以下是几款推荐的虚拟信用卡平台：

1. **EASYPAY**  
   这是我最早使用的虚拟信用卡平台，支持注册两张卡。遗憾的是，该平台已退出中国市场，无法继续使用。

   ![EASYPAY 截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8fa55bd290c343078673dff266a92c81~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=1680&h=524&s=109131&e=png&b=f8f9f9)

2. **PokeyPay**  
   这是后来接触的一款虚拟信用卡平台，前两张卡无月费，使用成本较低。

   ![PokeyPay 截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7baaf32c18194fd39eee27cd932b8a65~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=2240&h=1505&s=1083243&e=png&b=fbfbfb)

3. **FOMECard**  
   这是一款操作非常便捷的虚拟信用卡平台，推荐使用。

   ![FOMECard 截图](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4f659f94f00241d680b9ea67f06692c3~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=3316&h=646&s=184342&e=png&b=fefdfd)

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)

## 亚马逊云服务介绍

### 免费产品推荐

亚马逊云官网：[https://aws.amazon.com/cn/free/](https://aws.amazon.com/cn/free/)

![亚马逊云首页](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5db24a07920f451fbd6ad7cd3523f388~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=3771&h=1457&s=569328&e=png&b=fdfdfd)

#### 推荐服务：
- **Lightsail 服务**：适合短期试用。
- **EC2 服务**：提供 12 个月免费试用，适合长期使用。
- **永久免费服务**：需要自行深入研究。

![Lightsail 服务](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1543c11c43b446f09192ba6426e54ebc~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=2650&h=1574&s=585802&e=png&b=fcfcfc)  
![EC2 服务](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a6310a1bf3484468b05d9f3f2830b969~tplv-k3u1fbpfcp-jj-mark:3024:0:0:0:q75.awebp#?w=2753&h=1460&s=485504&e=png&b=fcfcfc)

### 注册账号

1. 访问[亚马逊云官网](https://aws.amazon.com/cn/free/)，点击“创建免费账号”。  
2. 验证邮箱并设置账号密码。  
3. 填写真实的账号信息。  
4. 绑定外币信用卡，确保信息准确。  
5. 验证手机号并选择默认账户计划，完成注册。

### 控制台操作

登录控制台：[https://console.aws.amazon.com](https://console.aws.amazon.com)

1. 设置区域（推荐选择日本、新加坡或首尔）。  
2. 搜索并启用 EC2 服务（通常需要 24 小时激活）。  
3. 搜索并试用 Lightsail 服务（3 个月免费试用）。

## EC2 服务配置

### 创建实例

1. 输入实例名称并选择操作系统。  
2. 选择免费套餐实例类型。  
3. 创建并下载密钥对，用于登录服务器。  
4. 设置网络安全组和存储空间（默认 10G，免费额度 30G）。  
5. 启动实例。

### 连接服务器

1. 使用私钥登录或通过网页设置登录。  
2. 在安全组中开放所需端口。

### 开启 root 用户登录

1. 切换到 root 用户：  
   bash
   sudo -i
   
2. 修改 SSH 配置文件：  
   bash
   vi /etc/ssh/sshd_config
   
3. 修改以下两项：  
   bash
   PermitRootLogin yes
   PasswordAuthentication yes
   
4. 设置 root 密码并重启 SSH 服务：  
   bash
   passwd
   systemctl restart ssh
   

## Lightsail 服务配置

### 创建实例

1. 选择实例位置和操作系统（推荐 CentOS 7）。  
2. 选择实例计划并创建实例。

### 实例详情

完成创建后直接使用即可。

## 网络性能测试

使用以下命令测试网络性能：  
bash
wget -qO- bench.sh | bash


## 注意事项

- **免费时长**：EC2 服务为 12 个月，Lightsail 服务为 3 个月，从账号注册日开始计算。请务必注意使用时限，避免产生额外费用。

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)