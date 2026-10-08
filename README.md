# app-legal

所有 App 共用的公开法律与支持页面中心仓库(App Store 上架用)。
通过 **GitHub Pages** 发布,URL 前缀 `https://nightingalem.github.io/app-legal/`。

## 目录结构

| 项目 | 页面 | URL |
|---|---|---|
| **Crazy Brick Ball / 疯狂砖球** | 隐私政策 | https://nightingalem.github.io/app-legal/privacy.html |
| | 支持页 | https://nightingalem.github.io/app-legal/support.html |
| **Winnow: Swipe to Keep** (照片清理) | 隐私政策 | https://nightingalem.github.io/app-legal/winnow/privacy.html |
| | 支持页 | https://nightingalem.github.io/app-legal/winnow/support.html |
| *(后续项目)* | 每项目一个子目录 | `.../app-legal/<项目名>/privacy.html` |

## 🔴 钉死约束(勿动)

- 根目录 `privacy.html` / `support.html` 属 Crazy Brick Ball 专用,URL 已填入 App Store Connect
  并随 1.0 过审,**路径永不可改**(挪动/改名 = 审核员点开 404,拒审风险)。
- `demo.mp4` = CBB App Review 审核录屏直链,同样勿动勿删。
- 历史遗留说明:根目录两页本应放 `crazy-brick-ball/` 子目录,因 ASC URL 已锁定,保持原位。

## 新增项目接入流程

1. 建子目录 `<项目名>/`(小写连字符;**名字一旦填进 ASC 即同样钉死,取名要稳**),
   放入该项目的 `privacy.html`(及可选 `support.html`)。
2. **隐私政策必须按该项目实际数据收集单独撰写,不可复制其他项目的**——须与该项目 App 内
   `PrivacyInfo.xcprivacy` 与 App Store Connect「App Privacy」申报**三处一致**(任一不一致可能被拒)。
   格式可以参考根目录 CBB 的 `privacy.html`(双语/自包含/响应式),内容必须重写。
3. ASC 填 `https://nightingalem.github.io/app-legal/<项目名>/privacy.html`。

## 页面说明(Crazy Brick Ball)

- `privacy.html` — 双语(EN / 中文)单页、自包含零外部依赖、移动端响应式、顶部一键切语言。
  当前为 **MVP 版:零收集 / 零追踪 / 零第三方 SDK**(与游戏内 `PrivacyInfo.xcprivacy` 零声明一致)。
- `support.html` — 双语 FAQ + 联系方式。
- `index.html` — 目录页(noindex,不参与收录),列出各 App 的法律页入口。

## 开启 Pages(一次性)

若 Pages 尚未开启:repo → *Settings → Pages → Source*: **Deploy from a branch** → 分支 `main` / 目录 `/ (root)` → *Save*。push 后约 1–2 分钟生效。

## 更新流程

源文件在各项目私有仓库 `legal/` 目录维护,改完后同步过来 push 即可(以 CBB 为例):

```sh
cp /path/to/creazy_brick_ball_vue/legal/privacy.html .
cp /path/to/creazy_brick_ball_vue/legal/support.html .
# 后续项目:cp /path/to/<项目>/legal/privacy.html <项目名>/privacy.html
git add -A && git commit -m "update legal pages" && git push
```

## 🔴 接广告(AdMob)后必须更新(Crazy Brick Ball)

- 隐私政策需加入广告 SDK 数据收集条款、第三方 SDK 清单、IDFA/ATT 说明;
  届时"零收集 / 零第三方 SDK"表述作废,须据实重写。
- **三处必须同步一致**(任一不一致可能被拒):
  1. 本仓库 `privacy.html`
  2. 游戏仓库 `ios/App/App/PrivacyInfo.xcprivacy`
  3. App Store Connect 后台「App Privacy」数据申报
