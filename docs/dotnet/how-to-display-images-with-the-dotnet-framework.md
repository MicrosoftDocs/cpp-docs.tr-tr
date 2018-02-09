---
title: "Nasıl yapılır: .NET Framework ile resimleri görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f50659832e04c3b8938c50bedc47b3ac770a52eb
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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