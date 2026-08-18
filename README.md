# app-legal

Crazy Brick Ball / 疯狂砖球 — 公开法律与支持页面(App Store 上架用)。

通过 **GitHub Pages** 发布,URL 前缀 `https://nightingalem.github.io/app-legal/`。

| 页面 | URL | 用途(App Store Connect) |
|---|---|---|
| 隐私政策 | https://nightingalem.github.io/app-legal/privacy.html | App 信息 → **Privacy Policy URL**(必填) |
| 支持页 | https://nightingalem.github.io/app-legal/support.html | App 信息 → **Support URL**(必填) |
| 索引页 | https://nightingalem.github.io/app-legal/ | 目录页(noindex,不参与收录) |

## 页面说明

- `privacy.html` — 双语(EN / 中文)单页、自包含零外部依赖、移动端响应式、顶部一键切语言。
  当前为 **MVP 版:零收集 / 零追踪 / 零第三方 SDK**(与游戏内 `PrivacyInfo.xcprivacy` 零声明一致)。
- `support.html` — 双语 FAQ + 联系方式。
- `index.html` — 简单目录页,方便审核员/用户从仓库根 URL 找到两个页面。

## 开启 Pages(一次性)

若 Pages 尚未开启:repo → *Settings → Pages → Source*: **Deploy from a branch** → 分支 `main` / 目录 `/ (root)` → *Save*。push 后约 1–2 分钟生效。

## 更新流程

源文件在游戏私有仓库 `legal/` 目录维护,改完后同步过来 push 即可:

```sh
cp /path/to/creazy_brick_ball_vue/legal/privacy.html .
cp /path/to/creazy_brick_ball_vue/legal/support.html .
git add -A && git commit -m "update legal pages" && git push
```

## 🔴 接广告(AdMob)后必须更新

- 隐私政策需加入广告 SDK 数据收集条款、第三方 SDK 清单、IDFA/ATT 说明;
  届时"零收集 / 零第三方 SDK"表述作废,须据实重写。
- **三处必须同步一致**(任一不一致可能被拒):
  1. 本仓库 `privacy.html`
  2. 游戏仓库 `ios/App/App/PrivacyInfo.xcprivacy`
  3. App Store Connect 后台「App Privacy」数据申报
