---
title: ADO.NET 新增功能
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: 90352d3e3d52430d515460cdcc9b6d177976c0b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191439"
---
# <a name="whats-new-in-adonet"></a>ADO.NET 新增功能
以下是 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 的新增功能。  
  
## <a name="sqlclient-data-provider"></a>SqlClient Data Provider  
 以下功能是中的新增功能[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]数据提供程序中的 SQL Server [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:  
  
-   ConnectRetryCount 和 ConnectRetryInterval 连接字符串关键字 (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) 可以让你控制空闲连接复原功能。  
  
-   流式处理支持从 SQL Server 的应用程序支持在服务器上的数据的非结构化的方案。  请参阅[SqlClient 流支持](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)有关详细信息。  
  
-   已添加了异步编程支持。  请参阅[异步编程](../../../../docs/framework/data/adonet/asynchronous-programming.md)有关详细信息。  
  
-   连接故障现在将记录在扩展事件日志中。 有关详细信息，请参阅 [ADO.NET 中的数据跟踪](../../../../docs/framework/data/adonet/data-tracing.md)。  
  
-   SqlClient 现在具有对 SQL Server 的高可用性和灾难恢复功能 AlwaysOn 的支持。 有关详细信息，请参阅[SqlClient 对高可用性和灾难恢复的支持](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)。  
  
-   密码可以作为传递<xref:System.Security.SecureString>时使用 SQL Server 身份验证。 有关更多信息，请参见<xref:System.Data.SqlClient.SqlCredential>。  
  
-   当`TrustServerCertificate`为 false 和`Encrypt`为 true，连接字符串中指定的服务器名称 （或 IP 地址），SQL Server SSL 证书中的服务器名称 （或 IP 地址） 必须完全匹配。 否则，连接尝试将失败。 有关更多信息，请参见 `Encrypt` 中 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 选项的说明。  
  
     如果此更改导致现有应用程序不再连接，可以通过以下方法之一修复应用程序：  
  
    -   颁发证书，以在公用名 (CN) 或主题备用名称 (SAN) 字段中指定短名称。 此解决方案将适用于数据库镜像。  
  
    -   添加别名，将短名称映射到完全限定的域名。  
  
    -   在连接字符串中使用完全限定的域名。  
  
-   SqlClient 支持扩展保护。 有关扩展保护的详细信息，请参阅[连接到数据库引擎使用扩展保护](https://go.microsoft.com/fwlink/?LinkId=219978)。  
  
-   SqlClient 支持连接到 LocalDB 数据库。 有关详细信息，请参阅[SqlClient 对 LocalDB 的支持](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md)。  
  
-   `Type System Version=SQL Server 2012;` 是新值将传递给`Type System Version`连接属性。 `Type System Version=Latest;` 值现已过时，它与 `Type System Version=SQL Server 2008;` 等效。 有关详细信息，请参阅 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。  
  
-   SqlClient 为稀疏列（SQL Server 2008 中新增的功能）提供额外支持。 如果应用程序已访问使用稀疏列的表中的数据，应看到性能有所提高。 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> 的 IsColumnSet 列指示某列是否为属于列集成员的稀疏列。 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 指示列是否为稀疏列 (请参阅[SQL Server 架构集合](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)有关详细信息)。 有关稀疏列的详细信息，请参阅[使用稀疏列](https://go.microsoft.com/fwlink/?LinkId=224244)。  
  
-   包含空间数据类型的程序集 Microsoft.SqlServer.Types.dll 已从 10.0 版本升级到版本 11.0。 引用此程序集的应用程序可能失败。 有关详细信息，请参阅[数据库引擎功能的重大更改](https://go.microsoft.com/fwlink/?LinkId=224367)。  
  
## <a name="adonet-entity-framework"></a>ADO.NET 实体框架  
 当与实体框架5.0 一起使用时，[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 添加启用新方案的 API。 有关 Entity Framework 5.0 中增加的改进和功能的详细信息，请参阅下列主题：[新增功能](https://go.microsoft.com/fwlink/?LinkID=251106)并[实体框架发行和版本控制](https://go.microsoft.com/fwlink/?LinkId=234899)。  
  
## <a name="see-also"></a>请参阅

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [ADO.NET 概述](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [SQL Server 和 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)
- [什么是 WCF 数据服务 5.0 中的新增功能](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
- [ADO.NET 托管提供程序和 DataSet 开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
