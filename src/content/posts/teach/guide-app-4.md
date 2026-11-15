---
title: 如何在保留集控的情况下干掉冰点
published: 2026-10-25
updated: 2026-11-15
description: 使用HugoAura在保留集控的情况下，骗过上面
image: "api"
tags: [教程, 软件,SEEWO,冰点还原,HugoAura,HugoWidget,IceMelt]
category: 教程
draft: false
---

# 前言

天下苦冰点还原久矣
> 原 HugoAura 早删库了，现在可用的是 HugoAura-Enhanced 。

::github{repo="blingbling-bow/HugoAura-Enhanced"}

> [!CAUTION] 继续操作, 您可能会面临:
> - 在配置 HugoAura-Enhanced 的过程中被老师发现, 从而需要解释自己的行为
> - 可能因某个不稳定的 HugoAura-Enhanced 更新, 导致集控端出现设备掉线等异常, 从而遭责问 (尽管 HugoAura-Enhanced 开发者会尽一切努力避免此类问题, 但由于测试环境严重受限, 仍有极小概率会发生此类问题)
> - 可能因错误的篡改设置 (例如将被冰冻盘上报为某些明显不合理的值) 而导致被发现
> - 其他类似的风险

选择自由, 意味着承担责任。如果您可以接受上述风险, 另请检查自身资质:
![](https://hugoaura.pages.dev/static/img/userGuide/introduction/SelfCheck_WithBg.png)

## ❗ 免责声明
本项目仅用于研究或教育目的, 请勿将本项目用于可能违反当地法律、侵犯著作权或其他软件 EULA 的用途。若将本项目用于非法用途, 一切后果由使用者承担。开发者不承担此类行为带来的任何后果或责任。
项目基于 GNU GPL-3.0 许可证开源。

# 部署
首先，请准备这些东西：
- 希沃管家最新版(v1.6.7.4018)
- HugoAura 自动安装器
- 希沃管家管理密码（通常为000000或666888）

# 使用HugoAura-Enhanced
## 联网安装
### 网络可访问性检查
![](https://hugoaura.pages.dev/static/img/userGuide/installation/autoInstallation/CheckYourConnection_WithBg.png)

> 请确保您的网络可访问以下站点
> 无需逐一手动测试, 仅当一键安装器在下载过程中失败时再诊断即可
> -  GitHub API (https://api.github.com), **以及**
> -  希沃易 + 软件下载站 (https://e.seewo.com), **以及**
> -  以下下载源中的**任意一个**:
> git.yylx.win
>
> github.chenc.dev
>
> gh.07150721.xyz
>
> cdn.gh-proxy.org
>
> axisnow.gh-proxy.org
>
> gh-proxy.org
>
> githubdog.com
>
> js.jiangss.shop
>
> gh.927223.xyz
>
> ghproxy.felicity.land
>
> github.tbap.top
>
> github.com

### 更新至最新版希沃管家
请打开 [e.seewo.com](e.seewo.com), 接着按下图所示完成管家最新版下载。

> [!CAUTION] 请务必更新到 e.seewo.com 上的最新管家版本
> 受注入技术限制, HugoAura-Enhanced-Main 始终仅对最新版本的希沃管家提供支持, 如果您尝试在旧版本管家上安装 HugoAura-Enhanced, 可能会引发崩溃或功能失效等问题。
我们不受理来自旧版管家的 Issues。

> [!INFO] 如果您能确定设备上运行的希沃管家即为最新版...
> 请留意, 希沃集控端一般实施灰度性版本推送。开启了管家自动更新的学校, 设备上的管家版本依然不一定是最新的。

1. 将鼠标置于顶栏 "软件下载" 处
2. 在展开的软件列表中选择 "希沃管家 (大板端)"
3. 在弹窗中默认的 "Windows" 选项卡中点击 "立即下载"
下载完成后, 运行安装包并根据提示操作即可。

### 下载安装器文件
如果网络情况允许, 推荐您通过 [GitHub Releases](https://github.com/blingbling-bow/HugoAura-Enhanced-Install/releases) 下载安装器文件。

一般选择最新的 Release 即可。

> [!CAUTION] 正在使用 Windows 7 ?
> 在 Windows 7 设备上使用一键安装可能需要特殊处理。接下来的每个步骤, 文档都会提供针对 Windows 7 设备的操作方案。请留意。
我们强烈建议您尽快更新 Windows 版本, Windows 7 是完全 EOL 的 Windows 发行, HugoAura-Enhanced 不对任何 Win 7 设备上遇到的特化 Bug 进行处理。
>
> 针对本步骤, 在下载文件时, 请下载带有 `py3-8` 字样的 EXE 包。Windows 7 无法运行 Python 3.10 的构建产物。

如果您的网络在访问 GitHub 时存在困难, 也可通过以下渠道下载:

| 下载渠道 | 下载链接 | 最新版本 |
|---|---|---|
|GitHub | [链接](https://github.com/blingbling-bow/HugoAura-Enhanced-Install/releases) | `始终最新` |
|蓝奏云 | [链接 (提取码: cmba)](https://openapi.lanzout.com/ivpbH44ce7he) | `v0.0.4-beta-I` |

### 使用 GUI 安装器
等待管家安装完成后，打开HugoAura-Enhanced自动安装器，选择“CI版本”，点击“开始安装“，等待即可。
> 此处借用官方文档站的图片
> ![](https://hugoaura.pages.dev/static/img/userGuide/installation/autoInstallation/InstallerUI_WithBg.png)

打开希沃管家，按照下图操作，进入HugoAura设置页面。

> 此处照样借用alt text
> ![](https://hugoaura.pages.dev/static/img/userGuide/installation/autoInstallation/SSADone_WithBg.png)

找到”行为管控“，也就是第二个设置板块，依次点击`下载应用`，`安装服务`和`启动服务`，接着找到”信息上报“，开启”冰点伪装“，点击C盘，即可伪装冰点。

> 希沃管家管理密码不是000000或666888的，记得修改密码后再重新安装一遍

> 如果希沃管家里面没有雨之光环的设置按钮，找到版本号，像是对安卓那样连续点击版本号很多遍，就能进入设置页面了

### 视频教程：

<iframe width="100%" height="468"
  src="//player.bilibili.com/player.html?bvid=BV1GLaU6uEYx&p=1&autoplay=0"
  scrolling="no" border="0" frameborder="no"
  framespacing="0" allowfullscreen="true">
</iframe>

# 使用其它
## HugoWidget
开源仓库地址：
::github{repo="HugoWidget/HugoWidgets"}
release下载地址：
::github{repo="HugoWidget/HugoSetup"}
命令行版本仓库：
::github{repo="HugoWidget/HugoProgs"}

QQ群号：707741689，入群问题答案见问卷。
项目几乎停止更新，但仍然欢迎入群讨论协作！

> [!CAUTION] CAUTION
> 声明：本项目仅用于研究或教育目的。请勿用于违反当地法律、侵犯著作权或软件 EULA 的用途。使用者需自行承担因不当使用带来的一切后果，开发者不承担任何责任。
>
> "希沃"、"Seewo" 是由广州视睿电子科技有限公司所持有的商标。HugoWidget所有子项目与广州视睿电子科技有限公司无关。
>
> HugoWidgets 及其他项目遵循 GNU GPL-3.0 许可证开源。

### 视频教程：

<iframe width="100%" height="468"
  src="//player.bilibili.com/player.html?bvid=BV1dTGB6NEBm&p=1&autoplay=0"
  scrolling="no" border="0" frameborder="no"
  framespacing="0" allowfullscreen="true">
</iframe>

## IceMelt

::github{repo="chenjintang-shrimp/IceMelt"}
用 KDU 与 WinDisk 破防各类冰点 / 还原软件

WinDisk 是内核驱动，直接构造 SCSI 请求下发到磁盘 miniport，绕过文件系统，也绕过还原软件挂在上层的过滤驱动。 KDU 关掉驱动签名强制，让没有签名的 WinDisk 能加载 —— 只在装载真的被 577 拒绝时才用得上 （判据见下：装载返回码，不是任何查询接口的读数）。

两者配合，在 NTFS 层面摘掉还原软件的注册表痕迹、换掉 SYSTEM hive，然后交回给你重启。不替换任何驱动文件。
> [!CAUTION] 免责声明
> 涉及内核驱动加载与裸盘写入，误用可导致数据损坏或系统无法启动。仅在你有权操作的机器与磁盘上 使用。第 8 步之后一旦开始写入就没有回滚路径：出错时程序会中止并报出"系统状态未知"，然后提示 你自行重启（本工具不触发任何复位）。