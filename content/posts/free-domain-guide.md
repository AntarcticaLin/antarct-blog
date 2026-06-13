+++
date = '2026-05-31T17:56:27+08:00'
draft = false
title = '免费域名 US.KG / QZZ.IO 注册教程'
tags = ['tutorial', 'domain', 'free']
comments = true
+++

## 前言

想搭网站但没有域名？市面上有不少免费域名服务，本文将详细介绍 **DigitalPlat FreeDomain** 的注册和使用方法。

<!--more-->

## 什么是 DigitalPlat FreeDomain？

DigitalPlat 是一个提供免费域名的项目，由 Edward Hsing 创立。目前已注册超过 **50 万个域名**，支持多种后缀：

| 后缀 | 说明 |
|------|------|
| `.US.KG` | 最热门，需付费插槽 |
| `.QZZ.IO` | 简洁短域名 |
| `.DPDNS.ORG` | 经典选择 |
| `.QD.JE` | 小众后缀 |

## 注册步骤

### 第一步：注册账号

打开 [DigitalPlat 控制面板](https://dash.domain.digitalplat.org/auth/register)，填写：

- **用户名** — 唯一标识，会出现在 WHOIS 记录中
- **邮箱** — 真实常用邮箱
- **密码** — 至少 12 位
- **WHOIS 信息** — 姓名、地址、电话

> 注册后建议开启 **WHOIS 隐私保护**，隐藏个人信息。

### 第二步：申请域名

登录 Dashboard → 找到 Register Domain → 输入想要的域名 → 选择后缀。

### 第三步：配置 DNS

推荐用 **Cloudflare**（需 VPN）或 **DNSPod（腾讯云）**（国内直连）：

1. 在 DNS 提供商添加你的域名
2. 获取 Nameserver 地址
3. 填回 DigitalPlat 控制面板

### 第四步：等待生效

DNS 传播通常几分钟到几小时。生效后你的域名就可以正常使用了。

## 几点提醒

- 每个账号默认只能注册 **1 个域名**
- 域名有效期一年，到期前 120 天内可**免费续期**
- 有自动续期脚本可用：[DigitalPlat-FreeDomain-Continue](https://github.com/adamzqcj/DigitalPlat-FreeDomain-Continue)
- Telegram 官方群已被入侵，请勿相信任何 Telegram 消息

## 总结

免费域名适合个人博客、测试项目、开源项目展示。虽然功能上不如付费域名灵活，但对于个人使用完全足够。快去申请一个吧！
