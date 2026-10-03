<p align="center">
  <img src="https://avatars.githubusercontent.com/u/23492851?v=4" width="96" height="96" alt="tap6" />
</p>

<h1 align="center">tap6</h1>

<p align="center">
  对世界抱有敬意。<br/>
  浙江 · <a href="https://uxn.cc">uxn.cc</a> · <a href="https://github.com/trustdev-org">TrustDev</a>
</p>

<p align="center">
  <a href="https://github.com/tap6"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-2016-24292f?style=flat-square&logo=github" /></a>
  <a href="https://uxn.cc"><img alt="博客" src="https://img.shields.io/badge/博客-uxn.cc-0ea5e9?style=flat-square" /></a>
</p>

从 2016 年开始把代码放在 GitHub 上。写的东西大多绕着同一件事：数据留在自己手里。文章在自己的仓库，日记在本机，域名自己盯着，聊天可以架在自己的机器上。

下面是目前还在维护、也适合别人直接拿去用的项目。

## 日历日记

[Calendar Diary](https://github.com/trustdev-org/calendar-diary) 是一款跨平台桌面日历，用来记下每天的待办、计划和心情。点开日期就能写，月历上一眼能看到整月安排，也可以给某一天贴心情。

数据默认存在本机。需要多台电脑一起用时，可以接到自己的 WebDAV。也可以加 PIN 和 TOTP。界面有简体中文、繁体中文、英语、日语、韩语和俄语。

Windows、macOS、Linux 都有安装包，站点在 [diary.trustdev.org](https://diary.trustdev.org)。

<p align="center">
  <img src="https://raw.githubusercontent.com/trustdev-org/calendar-diary/main/img-preview-1.png" width="720" alt="日历日记的月历界面" />
</p>

<p align="center">
  <a href="https://github.com/trustdev-org/calendar-diary"><img alt="Stars" src="https://img.shields.io/github/stars/trustdev-org/calendar-diary?style=flat-square&label=Stars" /></a>
  <img alt="Electron" src="https://img.shields.io/badge/Electron-桌面应用-47848F?style=flat-square&logo=electron&logoColor=white" />
  <img alt="许可" src="https://img.shields.io/badge/许可-CC%20BY--NC%204.0-green?style=flat-square" />
</p>

技术栈是 Electron、React 和 TypeScript。许可是 [CC BY-NC 4.0](https://github.com/trustdev-org/calendar-diary/blob/main/LICENSE)：可以分享和修改，需要署名，不能用于商业用途。

## GitPress

[GitPress](https://gitpress.net) 是一个博客后台。写作体验接近 WordPress，文章、图片和站点配置都提交到你自己的 GitHub 仓库。保存之后，GitHub Actions 把已发布的文章编成静态网页，挂到 GitHub Pages 或 Vercel。读者打开的是你的站点，草稿留在私有仓库里。

换主题不用搬文章。主题版本写在 `gitpress.json` 里，重新构建即可。配置只做加法，旧站点锁定在当前大版本上，以后的升级不会改你的仓库。

<p align="center">
  <img src="https://raw.githubusercontent.com/tap6/GitPress.net/main/apps/web/public/landing/dashboard-zh.webp" width="720" alt="GitPress 后台：随手记、文章、主题和 Actions 用量" />
</p>

它拆成三个仓库，许可不一样：

| 仓库 | 做什么 | 许可 |
| --- | --- | --- |
| [GitPress.net](https://github.com/tap6/GitPress.net) | 每天打开的后台：登录、写稿、管理站点 | [PolyForm Shield](https://github.com/tap6/GitPress.net/blob/main/LICENSE)。源码公开，可以改、可以自己部署；拿去做面向他人的博客平台需要书面授权 |
| [gitpress](https://github.com/tap6/gitpress) | 写作约定和内置主题。主题有 classic、minimal、ink、quill | [MIT](https://github.com/tap6/gitpress/blob/main/LICENSE) |
| [build-action](https://github.com/tap6/build-action) | 编译器。读取私有仓库，用 Astro 生成静态站，再推到公开的网站仓库 | [MIT](https://github.com/tap6/build-action/blob/main/LICENSE) |

后台停了，文章还在。同一套主题和 `build-action@v1` 仍然可以继续构建。我自己的博客 [uxn.cc](https://uxn.cc) 就是用它发的。

## 域名管家

[DomainMaster](https://github.com/trustdev-org/domain-master) 给手里域名比较多的人用。可以单个添加，也可以按行导入一份 `.txt`。面板上能看到总数、已持有、抢注中和快要过期的数量。

Whois 信息可以按 RDAP 结构化记录看，也可以看原文，注册日、过期日和状态会自动解析出来。名单存在浏览器本地，没有单独的账号系统。在线版是 [dm.trustdev.org](https://dm.trustdev.org)，另外有 [Tauri 打包](https://github.com/trustdev-org/domain-master-tauri)，可以在 Actions 里编出 macOS、Windows 和 Linux 应用。

<p align="center">
  <a href="https://github.com/trustdev-org/domain-master"><img alt="Stars" src="https://img.shields.io/github/stars/trustdev-org/domain-master?style=flat-square&label=Stars" /></a>
  <img alt="React" src="https://img.shields.io/badge/React-TypeScript-3178C6?style=flat-square&logo=react&logoColor=white" />
  <img alt="许可" src="https://img.shields.io/badge/许可-MIT-blue?style=flat-square" />
</p>

## WhisperLink

[WhisperLink](https://github.com/trustdev-org/WhisperLink) 是自己部署的即时通讯。打开页面，填一个昵称和 4 到 32 位的频道码，就能进入房间。同一频道码的人在一个群里；点头像可以再开一对一私聊。

文字和图片在浏览器里用 Web Crypto 加密后再发出，服务端只转发密文，也不保存历史，进程重启就清空。私聊用 ECDH 单独协商密钥。语音走 WebRTC，并用自建 TURN 做中转，方便国内网络。前端是一个 HTML 文件，服务端是 Node.js，依赖很少。

<p align="center">
  <a href="https://github.com/trustdev-org/WhisperLink"><img alt="Stars" src="https://img.shields.io/github/stars/trustdev-org/WhisperLink?style=flat-square&label=Stars" /></a>
  <img alt="许可" src="https://img.shields.io/badge/许可-MIT-blue?style=flat-square" />
</p>

## AnomyChat

[AnomyChat](https://github.com/trustdev-org/AnomyChat) 是更轻的匿名聊天室。部署到 Vercel 就能用，房间靠一个 ID 加入，昵称和头像自动生成。它适合临时开一个房间说几句：消息放在 Serverless 函数的内存里，实例回收之后就没了。

<p align="center">
  <a href="https://github.com/trustdev-org/AnomyChat"><img alt="Stars" src="https://img.shields.io/github/stars/trustdev-org/AnomyChat?style=flat-square&label=Stars" /></a>
  <img alt="许可" src="https://img.shields.io/badge/许可-MIT-blue?style=flat-square" />
</p>

## 别处

- 博客：[uxn.cc](https://uxn.cc)
- 组织：[trustdev-org](https://github.com/trustdev-org)
- 使用和改动上的问题，直接到对应仓库开 Issue
