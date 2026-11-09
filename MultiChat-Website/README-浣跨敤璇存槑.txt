MultiChat Desktop 官方下载网站（GitHub Pages 免费版）
================================================

【这个压缩包是什么】
这是你的网站文件，不是 MultiChat 软件安装包。
其中 index.html 是网站首页。上传到 GitHub Pages 后，朋友可以打开网站。
网站自动查询你的 GitHub Releases 最新公开版本，找到 .exe 安装包后显示下载按钮。

【第一步：创建仓库】
打开 https://github.com 登录你的 GitHub 账号。
右上角 + -> New repository。
仓库名称必须为：multichat-desktop（与网站代码内的仓库名称一致）。
选择 Public（公开），勾选 Add a README file，然后点击 Create repository。

【第二步：上传网站】
在这个仓库首页，点击 Add file -> Upload files。
把 index.html 和 .nojekyll 两个文件拖到上传区，点击 Commit changes。
不要把本说明文件、你的 WhatsApp/Facebook 登录数据上传到公开仓库。

【第三步：开启免费网站】
仓库上方 Settings -> 左边 Pages。
Build and deployment -> Source 选 Deploy from a branch。
Branch 选 main，Folder 选 /(root)，点击 Save。
完成部署后，你的网站地址是：
https://你的GitHub用户名.github.io/multichat-desktop/
例如用户名为 happy123，则为 https://happy123.github.io/multichat-desktop/
如果暂时 404，等部署完成后刷新，可到仓库 Actions 页面查看是否成功。

【第四步：首次发布软件】
你需要先用 MultiChat 项目的构建脚本生成 Windows .exe 安装包。
仓库首页右侧 Releases -> Create a new release / Draft a new release。
Tag 填 v1.0.6（或与你实际安装包一致的版本号）。
标题填 MultiChat Desktop v1.0.6。
在 Assets 区上传对应的 Windows Setup .exe。
点击 Publish release（公开发布，非 Draft/Prerelease）。
刷新官网，版本和下载按钮会从 GitHub 自动读取。
请不要把源码 ZIP 错当成 EXE 上传，也不要上传任何登录数据。

【第五步：以后如何自己更新网站上的下载】
先让新的项目源码构建出新 EXE，再新建一个更高版本的 Release（例如 v1.0.7）并上传新 EXE。
网站下次打开时会读取最新 Release，自动切换下载链接，无须改 index.html。

【重要：网站下载更新 ≠ 软件内部自动更新】
此网站能够自动显示/下载最新发布的安装包；但你当前的 1.0.6 程序并没有因此获得“在软件内自动更新”的能力。
真正的应用内自动更新需要先修改 Electron 程序，接入 electron-updater，配置 GitHub publish，
并正确发布 Windows NSIS 安装包以及 latest.yml、blockmap 等配套文件。
完成并测试一次包含更新功能的版本后，未来更新才能直接从软件里检查/下载。
在此之前，朋友可以通过官网手动下载新版并安装。

【如何设置网站仓库名称为其他值】
如果你的 GitHub 仓库不叫 multichat-desktop，需同时在 index.html 中修改
const repo = 'multichat-desktop'; 这一行，并相应调整网址。
