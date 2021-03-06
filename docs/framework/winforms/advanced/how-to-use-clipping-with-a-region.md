---
title: 如何：对区域使用剪裁
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163730"
---
# <a name="how-to-use-clipping-with-a-region"></a>如何：对区域使用剪裁
属性之一<xref:System.Drawing.Graphics>类是剪辑区域。 通过完成的所有绘制给定<xref:System.Drawing.Graphics>对象被限制为的剪辑区域<xref:System.Drawing.Graphics>对象。 可以通过调用设置的剪辑区域<xref:System.Drawing.Graphics.SetClip%2A>方法。  
  
## <a name="example"></a>示例  
 下面的示例构造包含单个多边形的路径。 然后，代码构造的区域，根据该路径。 在区域传递给<xref:System.Drawing.Graphics.SetClip%2A>方法的<xref:System.Drawing.Graphics>绘制对象，然后两个字符串。  
  
 下图显示了裁剪后的字符串。  
  
 ![Clip](./media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅

- [GDI+ 中的区域](regions-in-gdi.md)
- [使用区域](using-regions.md)
