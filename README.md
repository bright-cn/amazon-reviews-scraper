# Amazon 评论抓取工具

[![Bright Data](https://img.shields.io/badge/Powered%20by-Bright%20Data-FF9A00?style=flat-square)](https://www.bright.cn/) [![爬虫工具 API](https://img.shields.io/badge/Scraper%20API-Available-FF9A00?style=flat-square)](https://www.bright.cn/products/web-scraper/amazon) [![数据集](https://img.shields.io/badge/Dataset-Available-0066CC?style=flat-square)](https://www.bright.cn/products/datasets/amazon) [![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org) [![许可证：MIT](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)](LICENSE)

[![促销](https://github.com/bright-cn/Awesome-Web-Scraping/raw/main/Proxies%20and%20scrapers%20GitHub%20bonus%20banner%20CN.png)](https://www.bright.cn/products/web-scraper/amazon)

> **由 [Bright Data](https://www.bright.cn/) 提供支持的亚马逊评论数据。**

此代码库提供两种大规模访问亚马逊评论数据的方法：

- **[方法 1：Bright Data 亚马逊评论爬虫工具 API](#方法-1bright-data-亚马逊评论爬虫工具-api)**（推荐）- 完全托管的企业级爬虫 API，可自动处理代理、CAPTCHA 和扩展。
- **[方法 2：Bright Data 亚马逊评论数据集](#方法-2bright-data-亚马逊评论数据集)** - 可随时下载的预采集亚马逊评论数据集，无需进行抓取。

## 目录

- [为什么使用 Bright Data 抓取亚马逊评论？](#为什么使用-bright-data-抓取亚马逊评论)
- [方法 1：Bright Data 亚马逊评论爬虫工具 API](#方法-1bright-data-亚马逊评论爬虫工具-api)
  - [快速入门](#开始使用亚马逊评论爬虫工具-api)
  - [1. 亚马逊评论数据](#1-亚马逊评论数据)
- [方法 2：Bright Data 亚马逊评论数据集](#方法-2bright-data-亚马逊评论数据集)
- [数据采集方式](#数据采集方式)

## 为什么使用 Bright Data 抓取亚马逊评论？

抓取亚马逊评论面临多项挑战：

- 速率限制：亚马逊评论会监控请求频率，并可能封禁超出限制的 IP。
- CAPTCHA 检测：自动访问可能会触发 CAPTCHA 验证。
- 身份验证障碍：某些数据需要登录才能访问，并且平台会检测自动化操作。
- 动态内容加载：使用简单的 HTTP 请求很难抓取由 JavaScript 渲染的内容。
- IP 封禁：从同一 IP 重复发送请求可能会导致封禁。

Bright Data 的亚马逊评论爬虫工具 API 可通过以下功能解决这些问题：

- ✅ **内置动态代理**：自动绕过基于 IP 的速率限制
- ✅ **验证码破解**：无需任何额外设置即可应对机器人检测
- ✅ **结构化数据输出**：获取可直接用于分析的整洁 JSON
- ✅ **无需基础设施**：支持任意规模的云端托管抓取
- ✅ **99.9% 正常运行时间 SLA**：为业务关键型工作流提供可靠的数据采集

## 方法 1：Bright Data 亚马逊评论爬虫工具 API

[Bright Data 亚马逊评论爬虫工具 API](https://www.bright.cn/products/web-scraper/amazon) 是一种无需设置任何基础设施的完全托管式解决方案。

### 开始使用亚马逊评论爬虫工具 API

1. **注册**一个[免费的 Bright Data 账户](https://www.bright.cn/)
2. **前往**[亚马逊评论爬虫工具 API](https://www.bright.cn/products/web-scraper/amazon)
3. 从控制面板**获取你的 API 令牌**
4. **安装** `requests` 库：`pip install requests`
5. **运行** `amazon-reviews_scraper_api_codes/` 中的任意脚本

### 1. 亚马逊评论数据

从亚马逊评论中采集评论数据。

#### 输入参数

| 字段 | 类型 | 必填 | 说明 |
|-------|------|----------|-------------|
| `url` | 字符串 | 是 | 要抓取的亚马逊评论项目 URL |
| `limit` | 整数 | 否 | 返回结果的最大数量 |
| `include_errors` | 布尔值 | 否 | 在响应中包含错误详情 |
| `notify` | url | 否 | 数据采集完成时用于接收通知的 Webhook URL |
| `format` | 枚举 | 否 | 输出格式：`JSON`、`NDJSON`、`JSON Lines`、`CSV` |

#### 响应示例

```json
{
  "asin": "B0BSHF7LLL",
  "author_id": "AFVVGI2LFNKIRMZVUJJTOLGIJS4A",
  "author_link": "https://www.amazon.com/gp/profile/amzn1.account.AFVVGI2LFNKIRMZVUJJTOLGIJS4A",
  "author_name": "Michael M",
  "badge": "Verified Purchase",
  "brand": "Apple",
  "helpful_count": 66,
  "is_amazon_vine": false,
  "is_verified": true,
  "product_name": "Apple 2023 MacBook Pro Laptop with Apple M2 Pro chip with 12\u2011core CPU and 19\u2011core GPU: 16.2-inch Liquid Retina XDR Display, 16GB Unified Memory, 512GB SSD Storage. Works with iPhone/iPad; Silver",
  "product_rating": 4.7,
  "product_rating_count": 484,
  "product_rating_max": 5,
  "product_rating_object": {
    "five_star": 421,
    "four_star": 34,
    "one_star": 10,
    "three_star": 15,
    "two_star": 5
  },
  "rating": 5,
  "review_country": "United States",
  "review_header": "This thing is insane.",
  "review_id": "RCA7TI5EBH5VK",
  "review_posted_date": "July 22, 2023",
  "review_text": "I upgraded from the $3,499 i9 Intel MacBook Pro from 2019, and this laptop seriously blows that away. The keyboard is amazing and so much better, the screen is amazing, I love the refresh rate, the responsiveness of jumping between pages and apps is so ridiculously fast, the trackpad and speakers are still just amazing, and the battery life on this is mind-blowing.\n\n\nSeriously, 10/10, absolutely recommend this to anyone, this thing is insane. I put it in my backpack for 9 days, and 9 days later it was still at 54%, even though it was powered on the entire time. I literally got a FaceTime call on my iPhone and my MacBook rang in my backpack at the same time on day 9.\n\n\nGet this MacBook if you need power and battery life, nothing will beat this.",
  "url": "https://www.amazon.com/dp/B0BSHF7WHW"
}
```

👉 查看[完整 Python 代码](amazon-reviews_scraper_api_codes/amazon_reviews_scraper.py)

## 方法 2：Bright Data 亚马逊评论数据集

如果你需要即用型数据，又不想编写任何爬虫代码，[Bright Data 亚马逊评论数据集](https://www.bright.cn/products/datasets/amazon)可提供预采集并定期更新的数据，支持即时下载。

**为什么使用数据集而不是 API？**

- 📦 **即时访问**：无需设置、无需代码，也无需等待数据采集
- 🔄 **定期更新**：按固定计划刷新最新数据
- 📊 **多种格式**：可下载为 JSON、JSONL 或 CSV
- 🌍 **超大规模**：覆盖所有主要亚马逊评论类别的数百万条记录
- ✅ **完全合规**：数据来源符合道德规范，并已获得合法授权

👉 **[探索亚马逊评论数据集](https://www.bright.cn/products/datasets/amazon)**

## 数据采集方式

| 功能 | Bright Data 爬虫工具 API | Bright Data 数据集 |
|---------|------------------------|---------------------|
| 所需设置 | 仅需 API 令牌 | 无 |
| 实时数据 | ✅ 是 | ❌ 预采集 |
| 自定义查询 | ✅ 完全控制 | ❌ 固定模式 |
| 包含代理 | ✅ 内置动态代理 | N/A |
| CAPTCHA 破解 | ✅ 自动 | N/A |
| 规模 | 无限制 | 无限制 |
| 结构化输出 | ✅ JSON / NDJSON / JSON Lines / CSV | ✅ JSON / JSONL / CSV |
| 支持 | 企业级全天候支持 | 企业级全天候支持 |

---

🔗 **了解更多**：[https://www.bright.cn/products/web-scraper/amazon](https://www.bright.cn/products/web-scraper/amazon)
