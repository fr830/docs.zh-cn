---
title: SQL Server Express 安全性
ms.date: 03/30/2017
ms.assetid: cf9cf6d9-4b05-43e9-ac7b-6cefbfcd6d4e
ms.openlocfilehash: f4291de89b397f60aedd35b89d6aa3130d348be5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174546"
---
# <a name="sql-server-express-security"></a>SQL Server Express 安全性
Microsoft SQL Server Express Edition (SQL Server Express) 基于 Microsoft SQL Server，支持数据库引擎的大多数功能。 它如此设计旨在默认情况下关闭不重要的功能和网络连接。 这可减少恶意用户可以利用的攻击面。  
  
 SQL Server Express 通常作为命名实例安装。 默认实例名称为 `SQLExpress`。 命名实例由计算机的网络名称加上安装时指定的实例名称来标识。  
  
## <a name="network-access"></a>网络访问  
 出于安全原因，默认情况下，SQL Server Express 中禁用网络协议。 这可防止由于外部用户攻击而危及承载 SQL Server Express 的计算机。 您必须显式启用网络连接并启动 SQL Server Browser 服务才能从其他计算机连接到 SQL Server Express 实例。  
  
 一旦启用了网络连接，SQL Server Express 实例将具有与其他版本的 SQL Server 相同的安全要求。  
  
## <a name="user-instances"></a>用户实例  
 用户实例是由 SQL Server Express 的父实例生成的单独的 SQL Server Express 数据库引擎实例。 用户实例的主要目的是让那些在最低特权帐户下运行 Windows 的用户在其本地计算机上对 SQL Server Express 实例具有系统管理员 (`sysadmin`) 特权。 用户实例不适用于在自己的计算机上是系统管理员的用户。  
  
 用户实例是从 SQL Server 或 SQL Server Express 的主实例代表用户生成的。 它在用户的 Windows 安全上下文下作为用户进程运行，而不作为服务运行。 不允许 SQL Server 登录；仅支持 Windows 登录。 这可防止在用户实例上运行的软件进行用户无权限进行的系统范围的更改。 用户实例也称为子实例或客户端实例，有时可通过使用“run as normal user”（作为正常用户运行）的首字母缩略词 RANU 来引用。  
  
 每个用户实例均独立于其父实例和运行于同一计算机上的其他用户实例。 安装在用户实例上的数据库仅以单用户模式打开；多用户无法连接到这些数据库。 对用户实例禁用复制、分布式查询和远程连接。 当连接到用户实例时，用户在父 SQL Server Express 实例上没有任何特权。  
  
## <a name="external-resources"></a>外部资源  
 有关 SQL Server Express 的更多信息，请参见以下资源。  
  
|||  
|-|-|  
|[Microsoft SQL Server 2005 Express Edition Books Online（Microsoft SQL Server 2005 Express Edition 联机丛书）](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms165706(v=sql.90))|SQL Server 2005 Express Edition 的完整文档。|  
|[非管理员的用户实例](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms143684(v=sql.100))SQL Server 联机丛书中|说明如何创建和部署用户实例。|  
|[SQL Server Express 用户实例](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)|说明 ADO.NET 应用程序中的用户实例功能。 提供有关如何启用用户实例、使用 <xref:System.Data.SqlClient.SqlConnection> 连接到用户实例、用户实例生存期和用户实例方案的信息。|  
  
## <a name="see-also"></a>请参阅

- [SQL Server 安全性](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)
- [SQL Server Express 用户实例](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)
- [ADO.NET 托管提供程序和 DataSet 开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
