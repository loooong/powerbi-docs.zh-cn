---
title: 迁移报表服务器安装
description: 了解如何将现有 SQL Server Reporting Services 实例迁移到 Power BI 报表服务器实例中。
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 01/17/2019
ms.openlocfilehash: 898e2bc688e9d3e819511288484f07511c809fb8
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238025"
---
# <a name="migrate-a-report-server-installation"></a>迁移报表服务器安装

了解如何将现有 SQL Server Reporting Services (SSRS) 实例迁移到 Power BI 报表服务器实例中。

迁移的定义为将应用数据文件移到新的 Power BI 报表服务器实例中。 需要迁移安装的常见可能原因如下：

* 想要从 SQL Server Reporting Services 迁移到 Power BI 报表服务器
  
  > [!NOTE]
  > 无法从 SQL Server Reporting Services 就地升级到 Power BI 报表服务器。 必须进行迁移。

* 具有大规模部署或更新要求
* 要更改硬件或安装拓扑
* 遇到阻止升级的问题

## <a name="migrating-to-power-bi-report-server-from-ssrs-native-mode"></a>从 SSRS（本机模式）迁移到 Power BI 报表服务器

从 SSRS（本机模式）实例迁移到 Power BI 报表服务器的过程分为几步。

![从 SSRS（本机模式）迁移到 Power BI 报表服务器](media/migrate-report-server/migrate-from-ssrs-native.png "从 SSRS（本机模式）迁移到 Power BI 报表服务器")

> [!NOTE]
> SQL Server 2008 Reporting Services 及更高版本支持迁移。

* 备份数据库、应用和配置文件
* 备份加密密钥
* 克隆托管报表的报表服务器数据库
* 安装 Power BI 报表服务器。 如果使用的硬件相同，可以在 SSRS 实例所在的同一服务器上安装 Power BI 报表服务器。 若要详细了解如何安装 Power BI 报表服务器，请参阅[安装 Power BI 报表服务器](install-report-server.md)。

> [!NOTE]
> Power BI 报表服务器的实例名称为 PBIRS  。

* 使用报表服务器配置管理器配置报表服务器，并连接克隆的数据库。
* 执行 SSRS（本机模式）实例所需的任何清除操作

## <a name="migration-to-power-bi-report-server-from-ssrs-sharepoint-integrated-mode"></a>从 SSRS（SharePoint 集成模式）迁移到 Power BI 报表服务器

从 SSRS（SharePoint 集成模式）迁移到 Power BI 报表服务器并不像本机模式一样简单。 虽然这些步骤可以在一定程度上指导你如何迁移，但 SharePoint 中可能还有其他文件和资产需要进行管理，而这些步骤并未涉及。

![从 SSRS（SharePoint 集成模式）迁移到 Power BI 报表服务器](media/migrate-report-server/migrate-from-ssrs-sharepoint.png "从 SSRS（SharePoint 集成模式）迁移到 Power BI 报表服务器")

需要将特定的报表服务器内容从 SharePoint 迁移到 Power BI 报表服务器。 需要已在环境中的某个位置安装 Power BI 报表服务器。 若要详细了解如何安装 Power BI 报表服务器，请参阅[安装 Power BI 报表服务器](install-report-server.md)。

如果要将报表服务器内容从 SharePoint 环境复制到 Power BI 报表服务器中，需要使用 rs.exe 等工具来复制内容  。 下面的示例展示了用于将报表服务器内容从 SharePoint 复制到 Power BI 报表服务器的脚本。

> [!NOTE]
> 示例脚本应该会对 SharePoint 2010 及更高版本和 SQL Server 2008 Reporting Services 及更高版本产生不利影响。

### <a name="sample-script"></a>示例脚本

```
Sample Script
rs.exe
-i ssrs_migration.rss -e Mgmt2010
-s https://SourceServer/_vti_bin/reportserver
-v st="sites/bi" -v f="Shared Documents“
-u Domain\User1 -p Password
-v ts=https://TargetServer/reportserver
-v tu="Domain\User" -v tp="Password"
```

## <a name="migrating-from-one-power-bi-report-server-to-another"></a>从一个 Power BI 报表服务器迁移到另一个

从一个 Power BI 报表服务器迁移到另一个的过程与从 SSRS（本机模式）迁移一样。

![从 Power BI 报表服务器迁移到 Power BI 报表服务器](media/migrate-report-server/migrate-from-pbirs.png "从 Power BI 报表服务器迁移到 Power BI 报表服务器")

* 备份数据库、应用和配置文件
* 备份加密密钥
* 克隆托管报表的报表服务器数据库
* 安装 Power BI 报表服务器。 无法在要从其迁移的 Power BI 报表服务器所在的同一服务器上安装 Power BI 报表服务器  。 若要详细了解如何安装 Power BI 报表服务器，请参阅[安装 Power BI 报表服务器](install-report-server.md)。

> [!NOTE]
> Power BI 报表服务器的实例名称为 PBIRS  。

* 使用报表服务器配置管理器配置报表服务器，并连接克隆的数据库。
* 执行旧版 Power BI 报表服务器安装所需的任何清除操作。

## <a name="next-steps"></a>后续步骤

[管理员概述](admin-handbook-overview.md)  
[安装 Power BI 报表服务器](install-report-server.md)  
[rs.exe 实用工具脚本和 Web 服务](https://docs.microsoft.com/sql/reporting-services/tools/script-with-the-rs-exe-utility-and-the-web-service)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)