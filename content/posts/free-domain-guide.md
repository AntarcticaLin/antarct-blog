+++
date = '2026-05-31T17:56:27+08:00'
draft = false
title = '我的 qzz.io 免费域名用了大半年'
tags = ['domain', 'free']
comments = true
+++

这个博客的域名 `antarct.qzz.io` 是免费域名，来自 DigitalPlat FreeDomain 项目，用了大半年了，目前一切正常。

## 怎么来的

去年搭博客时不想花钱买域名——不是花不起，是觉得万一博客没坚持下来，域名白买了。

搜了一圈免费域名方案：

- **Freenom**（.tk .ml 等）— 曾经最火，但已经被回收了，现在注册不了
- **EU.org** — 波兰的免费域名，审核要等很久，我等了两周没消息放弃了
- **DigitalPlat FreeDomain** — 操作简单，当天生效，就它了

<!--more-->

## DigitalPlat 注册流程

我在 [dash.domain.digitalplat.org](https://dash.domain.digitalplat.org) 注册账号，填了用户名、邮箱、WHOIS 信息（用英文填的，地址没写真实门牌号），然后申请了 `antarct.qzz.io`。

整个流程很简单：
1. 注册账号 → 验证邮箱
2. 去 Dashboard → Register Domain → 输入前缀 → 选后缀 → 确认
3. 配 DNS

第三步最麻烦。DigitalPlat 不提供 DNS 托管，得自己去 Cloudflare 或者 DNSPod 配 Nameserver。我用的 Cloudflare，添加域名后它给了两个 Nameserver 地址，填回 DigitalPlat 的控制面板就好了。

**坑**：注册完后不要立刻去 Cloudflare 添加域名——DNS 还没生效，Cloudflare 会报错说查不到记录。等 10-30 分钟再去。

## 用了大半年的感受

**好的方面：**
- 一直稳定，没掉过链子
- HTTPS 正常（Cloudflare 代理的）
- 搜索引擎收录正常

**需要注意的：**
- 有效期一年，到期前 120 天才能续期。我在手机日历设了提醒
- 有自动续期脚本，但我没用——怕脚本哪天突然不能用了反而不如自己手动续可靠
- Telegram 官方群被入侵过，别信上面的任何消息

## 总结

如果你只是想搭个个人博客或测试项目，免费域名完全够用。我现在用了大半年，没遇到任何问题。即使哪天这个域名不能用了，也就换个域名的事——文章数据在 GitHub 上丢不了。

毕竟，`git push` 才是真正的"域名"。
