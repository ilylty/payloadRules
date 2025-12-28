**HK-CDN-Rules**

---

**包含的资源类型**

当前规则主要覆盖以下平台和资源类型：

* YouTube 视频与图片（googlevideo / ytimg 等）
* Telegram 视频、图片、文件下载
* TikTok 视频、直播相关 CDN
* GitHub Raw、Release、Assets 相关资源
* HuggingFace 模型与数据集下载（xet / hf CDN）
* Pixiv（P 站）图片资源
* Twitter（X）图片与视频资源
* Reddit 图片与视频资源

整体目标是：
**“体积大、连接多、持续时间长的资源单独走策略”**

---

**基本用法**

1️⃣ 在 Clash 配置文件中添加 rule-providers

```yaml
rule-providers:
  hk-cdn-domain:
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/ilylty/HK-CDN-Rules/rules/hk-domain.txt"
    path: ./ruleset/hk-cdn-domain.yaml
    interval: 86400
```

2️⃣ 在 rules 中引用该规则集

```yaml
rules:
  - RULE-SET,hk-cdn-domain,你的节点或策略组名称
```

示例：

```yaml
- RULE-SET,hk-cdn-domain,HK-CDN
```
