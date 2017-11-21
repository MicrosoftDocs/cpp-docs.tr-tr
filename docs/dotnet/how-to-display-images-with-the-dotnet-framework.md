---
title: "Nasıl yapılır: .NET Framework ile resimleri görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 23e8445e5a407e71061a971bccfb77d6b4170a35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-display-images-with-the-net-framework"></a>Nasıl yapılır: .NET Framework ile Görüntüleri Görüntüleme
Aşağıdaki kod örneğinde bir işaretçi almak için OnPaint olay işleyicisini değiştirmektedir <xref:System.Drawing.Graphics> ana form için nesne. <xref:System.Windows.Forms.Form.OnPaint%2A> İşlevi, büyük olasılıkla bir Visual Studio uygulama sihirbazıyla oluşturulmuş bir Windows Forms uygulaması için tasarlanmıştır.  
  
 Görüntü tarafından temsil edilen <xref:System.Drawing.Image> sınıfı. Görüntü verilerini kullanarak bir .jpg dosya yüklendi <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> yöntemi. Görüntü forma çizilmeden önce form görüntüye yetecek boyutlandırılır. Resim çizim ile gerçekleştirilen <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> yöntemi.  
  
 <xref:System.Drawing.Graphics> Ve <xref:System.Drawing.Image> sınıflardır hem de <xref:System.Drawing?displayProperty=fullName> ad alanı.  
  
> [!NOTE]
>  GDI + ile Windows XP dahil edilmiştir ve Windows NT 4.0 SP 6, Windows 2000, Windows 98 ve Windows Me için yeniden dağıtılabilir olarak kullanılabilir En son yeniden yüklemek için bkz [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232).   
  
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
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)