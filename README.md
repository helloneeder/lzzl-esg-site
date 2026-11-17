# lzzl-esg-site

凌朝智绿官方静态网站（2026-11-18 起为合伙人定稿版，墨绿+金主题单页）。
旧版（亮绿主题，index/cases 两页）保留在分支 `backup/old-site-20261118` 与 tag `pre-replace-20261118`。

## 当前结构

```
index.html        # 单页官网（业务体系/产品服务/凌绿智报/案例样本/碳价值/飞轮/合规/联系）
assets/           # logo.png / logo-en.png
esg-sample.pdf    # ESG 报告样本
sample-cover.png  # 样本封面图
_redirects        # Cloudflare Pages：/cases、/cases.html 301 到首页
```

部署：Cloudflare Pages，纯静态零构建，直接上传目录或整包 zip。

---

# 历史说明（旧版）


## 技术栈

纯静态 HTML / CSS / JS，零依赖，内联样式，无需构建。

## 页面

| 文件 | 说明 |
|------|------|
| `index.html` | 官网首页（1140行） |
| `cases.html` | 案例页（677行） |

## 本地运行

直接用浏览器打开 `index.html` 即可，或启动任意静态服务器：

```bash
# Python
python3 -m http.server 8080

# Node (npx)
npx serve .
```

访问 http://localhost:8080

## 部署

### 方案一：静态托管（推荐）

可部署到任意静态托管平台：
- **Vercel / Netlify**：直接拖拽或连接仓库，自动部署
- **GitHub Pages**：push 到 main 分支，开启 Pages
- **阿里云 OSS + CDN**：上传文件，绑定域名
- **腾讯云 COS + CDN**：同上
- **Nginx**：将文件放到站点根目录

### 方案二：Vercel 演示环境

最快的上线方式，适合验收和演示：
1. 仓库推到 GitHub
2. Vercel import 仓库
3. 自动部署，分配 vercel.app 子域名
4. 正式上线再绑定自有域名

### 注意事项

- 纯静态站，无后端，部署成本极低
- 全站零构建，部署即上线
- 响应式布局，兼容移动端

## 上线前检查清单

- [ ] 400 电话替换真实号码（当前 `400-xxx-xxxx` 占位，共 3 处）
- [ ] questionnaire.lzzl-esg.com 子域名 DNS 配置（页面有 3 处链接指向数据平台）
- [ ] 确认域名备案状态（国内部署需要 ICP 备案）
- [ ] 配置 HTTPS（所有托管平台默认提供）

## 目录说明

```
lzzl-esg-site/
├── index.html          # 首页
├── cases.html          # 案例页
│   └──（已移除，见历史提交）

└── README.md
```

**注意**：历史版本中的 `jewelry-static/` 目录已从仓库移除。
珠宝站代码已迁移到独立仓库：https://github.com/helloneeder/infa-jewelry
