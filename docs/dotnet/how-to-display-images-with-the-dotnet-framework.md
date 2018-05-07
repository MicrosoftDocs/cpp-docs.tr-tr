---
title: 'Nasıl yapılır: .NET Framework ile resimleri görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4a7f3ed2d8fe90501b5ef3d0ae5028890fe5290e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>Nasıl yapılır: .NET Framework ile Görüntüleri Görüntüleme
Aşağıdaki kod örneğinde bir işaretçi almak için OnPaint olay işleyicisini değiştirmektedir <xref:System.Drawing.Graphics> ana form için nesne. <xref:System.Windows.Forms.Form.OnPaint%2A> İşlevi, büyük olasılıkla bir Visual Studio uygulama sihirbazıyla oluşturulmuş bir Windows Forms uygulaması için tasarlanmıştır.  
  
 Görüntü tarafından temsil edilen <xref:System.Drawing.Image> sınıfı. Görüntü verilerini kullanarak bir .jpg dosya yüklendi <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> yöntemi. Görüntü forma çizilmeden önce form görüntüye yetecek boyutlandırılır. Resim çizim ile gerçekleştirilen <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> yöntemi.  
  
 <xref:System.Drawing.Graphics> Ve <xref:System.Drawing.Image> sınıflardır hem de <xref:System.Drawing?displayProperty=fullName> ad alanı.  
  
## <a name="example"></a>Örnek  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing?displayProperty=fullName>   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)