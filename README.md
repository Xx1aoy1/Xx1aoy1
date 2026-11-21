<div align="center">

<h1 align="center">xiaoyi</h1>

<p align="center">
  把便宜硬件榨干的折腾派 · 刷机 / 容器 / 代理 / 自动化脚本<br/>
  能自己跑起来的东西，就不想手动点。
</p>

<p align="center">
  <a href="https://xiaoyiweb.xyz"><img src="https://img.shields.io/badge/站点-xiaoyiweb.xyz-3b82f6?style=flat-square&logo=cloudflare&logoColor=white" alt="站点"></a>
  <a href="https://xiaoyiweb.xyz/articles.html"><img src="https://img.shields.io/badge/笔记-实战踩坑-06b6d4?style=flat-square&logo=readthedocs&logoColor=white" alt="笔记"></a>
  <a href="mailto:200940211@qq.com"><img src="https://img.shields.io/badge/邮箱-200940211@qq.com-ef4444?style=flat-square&logo=gmail&logoColor=white" alt="邮箱"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/github/followers/Xx1aoy1?style=flat-square&label=followers&color=2da44e" alt="followers">
  <img src="https://img.shields.io/badge/仓库-32个-0969da?style=flat-square" alt="repos">
  <img src="https://img.shields.io/github/stars/Xx1aoy1?style=flat-square&label=total%20stars&color=e3b341" alt="stars">
  <img src="https://img.shields.io/github/contributors/Xx1aoy1/Xx1aoy1.github.io?style=flat-square&label=pages&color=8250df" alt="pages">
</p>

</div>

---

## 🖥️ 主力机器

```yaml
machine : CM311-1A (Amlogic S905L3A / 4×Cortex-A55 / 2GB RAM / 16GB eMMC)
os      : Armbian 26.8.3 (Ubuntu 26.04 base)
network : 家宽无公网 IPv4  ->  Cloudflare Tunnel  ->  OpenResty
services: 1Panel, 青龙面板, YYB-Go, v2rayA, OpenResty, cloudflared
website : https://xiaoyiweb.xyz
```

## 📖 关于这个号

主要拿来放我在自家小机器上折腾出来的东西：能跑通的就整理成手册或脚本，跑不通的也记下来——踩过的坑比顺过的路更值得写。

不产出「翻译官方文档」式的教程。这里的每一篇都对应一次真实的故障现场，附定位过程和能直接复制的命令。

## 🛠️ 技术栈

| 方向 | 在用的 |
| :--- | :--- |
| 操作系统 | Armbian、Linux 内核与 systemd、eMMC 分区与扩容 |
| 容器化 | Docker、Docker Compose、镜像分层与空间回收、容器网络 |
| 反向代理 | Nginx / OpenResty、Cloudflare Tunnel、SSL 终局到源站 |
| 脚本 | Python（requests / 定时任务 / 数据抓取）、Shell、Node.js |
| 网络排查 | 代理链路（HTTP/SOCKS5）、`NO_PROXY` 匹配规则、tcpdump / ss / curl |
| 前端 | 纯手写 HTML + CSS，静态站，无构建链 |

## 🚀 在维护的项目

### xiaoyiweb — 一台电视盒子的服务托管实践

把一台 200 块的运营商盒子当成小型服务器用，跑着 7 个容器服务，并通过 Cloudflare Tunnel 挂上自己的域名对外提供访问。

- **站点**：<https://xiaoyiweb.xyz>
- **硬件约束**：4 核 A55 / 2G 内存 / 16G eMMC，没有公网 IPv4
- **核心难点**：内存紧、存储更紧、出口靠隧道，任何一处配置错了都会连环出问题

写出来的手册：

| 手册 | 内容 |
| :--- | :--- |
| [容器代理配置排查手册](https://xiaoyiweb.xyz/proxy-troubleshooting.html) | 7 个容器逐个过，代理端口怎么选、`NO_PROXY` 为什么失效、容器名互访 503 的真因 |
| [Armbian 存储清理手册](https://xiaoyiweb.xyz/armbian-storage.html) | 16G eMMC 上镜像分层、构建缓存、日志膨胀的定位与安全回收 |
| [无公网 IP 建站教程](https://xiaoyiweb.xyz/site-guide.html) | 家宽没有公网 IPv4，用 Cloudflare Tunnel + 1Panel + OpenResty 上线 |
| [收尾优化三件事](https://xiaoyiweb.xyz/optimize.html) | 健康检查、自动重启、日志轮转，小机器长期稳定绕不过去 |

同步更新的实战笔记（每篇一个具体故障）：<https://xiaoyiweb.xyz/articles.html>

### 自动化脚本

青龙面板上跑的日常任务，主要是签到、数据同步、状态推送这一类。做法偏工程：公共模块统一放、日志按任务分开、失败要能一眼看出是哪一层挂的。

## ✍️ 我比较在意的事

- **可复现**：命令要能直接粘，不要「大概是这样」
- **判据要硬**：配置值对了不算修好，请求真的返回 200 才算
- **说清边界**：什么环境下验证的、哪一步没验，都写出来

## 📮 联系

- 站点：<https://xiaoyiweb.xyz>
- 邮箱：200940211@qq.com
- 闲鱼：[技术类服务与技能类需求](https://m.tb.cn/h.j1Ac3Zf?tk=uqg4TGAXpyO)

<sub>上面这些手册都是我自己踩出来的。卡在同一个坑里的话，写邮件说明现象和环境，我一般都会回。</sub>
