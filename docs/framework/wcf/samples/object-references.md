---
title: 对象引用
ms.date: 03/30/2017
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
ms.openlocfilehash: 2a2da82d913d43aa9bc3ccfeb9f1f1eda12b0562
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300666"
---
# <a name="object-references"></a>对象引用
此示例演示如何在服务器与客户端之间通过引用来传递对象。 此示例使用模拟*社交网络*。 社会网络由一个 `Person` 类组成，该类包含一个朋友列表，其中每个朋友都是 `Person` 类的一个实例，并有自己的朋友列表。 这将创建一个对象图。 服务在这些社会网络上公开操作。  
  
 在本示例中，服务是由 Internet 信息服务 (IIS) 承载的，客户端是一个控制台应用程序 (.exe)。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
## <a name="service"></a>服务  
 `Person` 类应用了 <xref:System.Runtime.Serialization.DataContractAttribute> 属性，<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 字段设置为 `true` 以将其声明为引用类型。 所有属性 (Property) 都应用了 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性 (Attribute)。  
  
```csharp
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 `GetPeopleInNetwork` 操作采用一个 `Person` 类型的参数，并返回网络中的所有人；也就是说，返回 `friends` 列表中的所有人、朋友的朋友等等（没有重复项）。  
  
```csharp
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 `GetMutualFriends` 采用一个 `Person` 类型的参数，返回列表中所有符合以下条件的朋友：在其 `friends` 列表中也包含这个人。  
  
```csharp
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 `GetCommonFriends` 操作采用一个 `Person` 类型的列表。 该列表应当有两个 `Person` 对象。 该操作返回 `Person` 对象的列表，这些对象位于输入列表中的 `friends` 对象的 `Person` 列表中。  
  
```csharp
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a>客户端  
 使用创建客户端代理**添加服务引用**Visual Studio 的功能。  
  
 创建了一个由五个 `Person` 对象组成的社会网络。 客户端在服务中调用三个方法中的每一个。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- [可互操作的对象引用](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)
