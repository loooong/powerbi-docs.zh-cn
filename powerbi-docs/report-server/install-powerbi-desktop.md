---
title: 安装更适合 Power BI 报表服务器的 Power BI Desktop
description: 了解如何安装更适合 Power BI 报表服务器的 Power BI Desktop
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 02/13/2020
ms.openlocfilehash: 3f4538639765f62387fe6b4e493886f85ba22c3d
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239344"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>安装更适合 Power BI 报表服务器的 Power BI Desktop

若要为 Power BI 报表服务器创建 Power BI 报表，需要下载并安装已针对 Power BI 报表服务器进行优化的 Power BI Desktop 版本。 此版本不同于用于 Power BI 服务的 Power BI Desktop。 例如，用于 Power BI 服务的 Power BI Desktop 版本包含预览功能，而这些功能在正式发布后才包含在 Power BI 报表服务器版本中。 使用此版本可确保报表服务器能够与已知版本的报表和模型交互。 

好消息是，可在同一台计算机上并行安装 Power BI Desktop 以及针对 Power BI 报表服务器进行了优化的 Power BI Desktop。

## <a name="download-and-install-power-bi-desktop"></a>下载并安装 Power BI Desktop

确保使用已针对 Power BI 报表服务器进行优化的最新 Power BI Desktop 版本的最简单方法是从报表服务器的 Web 门户启动。

1. 在报表服务器 Web 门户中，选择“下载”箭头 >“Power BI Desktop”。  

    ![从 Web 门户下载 Power BI Desktop](media/install-powerbi-desktop/report-server-download-web-portal.png)

    或转到 [Power BI 报表服务器](https://powerbi.microsoft.com/report-server/)主页，然后选择“高级下载选项”  。

2. 在“下载中心”页中，选择一种语言，然后选择“下载”  。

3. 根据所用的计算机选择： 

    - **PBIDesktopRS.msi**（32 位版本）或
    - **PBIDesktopRS_x64.msi**（64 位版本）。

1. 下载安装程序后，运行 Power BI Desktop（2019 年 9 月版）安装向导。

2. 安装结束时，选择“启动 Power BI Desktop”  。

    此时，它会自动启动，可以开始使用了。

## <a name="verify-youre-using-the-correct-version"></a>验证当前使用的版本是否正确。
简单操作即可验证你是否在使用正确的 Power BI Desktop：查看 Power BI Desktop 中的启动屏幕或标题栏。 根据标题栏中显示的“Power BI Desktop (2019 年 9 月版)”，便知道使用了正确的版本  。 此外，Power BI 徽标的颜色也会颠倒，在黑色上面显示黄色而不是在黄色上面显示黑色。

![Power BI Desktop 2019 年 9 月版](media/install-powerbi-desktop/power-bi-report-server-desktop-sept-2019.png)

适用于 Power BI 服务的 Power BI Desktop 版本不会在标题栏中显示发行月份和年份。

## <a name="file-extension-association"></a>文件扩展名关联
如果在同一计算机上同时安装 Power BI Desktop 以及针对 Power BI 报表服务器进行了优化的 Power BI Desktop，则最新安装的 Power BI Desktop 具有与 .pbix 文件关联的文件。 因此，当你双击 .pbix 文件时，它会启动你最近安装的 Power BI Desktop。

如果你具有 Power BI Desktop，然后再安装针对 Power BI 报表服务器进行了优化的 Power BI Desktop，则所有 .pbix 文件均在针对 Power BI 报表服务器进行了优化的 Power BI Desktop 中默认打开。 如果你更希望在打开 .pbix 文件时默认启动 Power BI Desktop，请[从 Microsoft Store 重新安装 Power BI Desktop](https://aka.ms/pbidesktopstore)。

始终可以打开要优先使用的 Power BI Desktop 版本。 然后，在 Power BI Desktop 中打开文件。

如果在 Power BI 报表服务器中编辑 Power BI 报表，或者通过 Web 门户创建新的 Power BI 报表，请始终打开 Power BI Desktop 的正确版本。

## <a name="considerations-and-limitations"></a>注意事项和限制

在 Power BI 报表服务器、Power BI 服务 (`https://app.powerbi.com`) 和 Power BI 移动应用中，Power BI 报表的行为几乎完全相同，但有一些功能不同。

### <a name="selecting-a-language"></a>选择语言

对于已针对 Power BI 报表服务器进行优化的 Power BI Desktop，请选择安装应用时所用的语言。 以后将无法更改，但可以安装其他语言的版本。

### <a name="report-visuals-in-a-browser"></a>浏览器中的报表视觉对象

Power BI 报表服务器报表支持几乎所有可视化效果，包括 Power BI 视觉对象。 Power BI 报表服务器报表不支持：

* R 视觉对象
* ArcGIS 地图
* 痕迹导航栏
* Power BI Desktop 预览功能

### <a name="reports-in-the-power-bi-mobile-apps"></a>Power BI 移动应用中的报表

Power BI 报表服务器报表支持 [Power BI 移动应用](../consumer/mobile/mobile-apps-for-mobile-devices.md)中的所有基本功能，其中包括：

* [手机报表布局](../create-reports/desktop-create-phone-report.md)：可以优化 Power BI 移动应用的报表。 在移动手机上，优化后的报表具有一个特定图标 ![手机报表布局图标](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png) 和布局。
  
    ![针对手机优化后的报表](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Power BI 报表服务器报表不支持 Power BI 移动应用中的如下功能：

* R 视觉对象
* ArcGIS 地图
* Power BI 视觉对象
* 痕迹导航栏
* 地理位置筛选或条码

### <a name="custom-security"></a>自定义安全性

针对 Power BI 报表服务器进行优化的 Power BI Desktop 不支持自定义安全性。 如果你的 Power BI 报表服务器配置了自定义安全扩展，则不能将 Power BI 报表从 Power BI Desktop（已针对 Power BI 报表服务器进行优化）保存到 Power BI 报表服务器实例。 需要从 Power BI Desktop 保存 .pbix 报表文件，并将其上传到 Power BI 报表服务器门户站点。

### <a name="saving-reports-to-a-power-bi-report-server-in-a-different-domain"></a>将报表保存到不同域中的 Power BI 报表服务器

将 Power BI 报表保存到 Power BI 报表服务器时，会使用你的 Windows 凭据。 不支持直接保存到与 Windows 凭据不同的域中的报表服务器。 可以改为使用 Web 浏览器查看报表服务器，然后手动从计算机上传文件。

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>适用于早期版本 Power BI 报表服务器的 Power BI Desktop

如果报表服务器是早期版本的，则需要相应版本的 Power BI Desktop。 以下是用于下载之前版本的链接。

- Microsoft Power BI Desktop（[已针对 Power BI 报表服务器进行优化 - 2019 年 9 月版](https://go.microsoft.com/fwlink/?linkid=2103723)）

## <a name="next-steps"></a>后续步骤

至此，已安装 Power BI Desktop，可以开始创建 Power BI 报表了。

[为 Power BI 报表服务器创建 Power BI 报表](quickstart-create-powerbi-report.md)  
[什么是 Power BI 报表服务器？](get-started.md)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)

