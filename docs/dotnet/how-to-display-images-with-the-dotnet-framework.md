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
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7c12d6a67f6fbe73802d3b876621a2ea606af553
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>Nasıl yapılır: .NET Framework ile Görüntüleri Görüntüleme
Aşağıdaki kod örneğinde bir işaretçi almak için OnPaint olay işleyicisini değiştirmektedir <xref:System.Drawing.Graphics> ana form için nesne. <xref:System.Windows.Forms.Form.OnPaint%2A> İşlevi, büyük olasılıkla bir Visual Studio uygulama sihirbazıyla oluşturulmuş bir Windows Forms uygulaması için tasarlanmıştır.  
  
 Görüntü tarafından temsil edilen <xref:System.Drawing.Image> sınıfı. Görüntü verilerini kullanarak bir .jpg dosya yüklendi <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> yöntemi. Görüntü forma çizilmeden önce form görüntüye yetecek boyutlandırılır. Resim çizim ile gerçekleştirilen <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> yöntemi.  
  
 <xref:System.Drawing.Graphics> Ve <xref:System.Drawing.Image> sınıflardır hem de <xref:System.Drawing?displayProperty=fullName> ad alanı.  
  
> [!NOTE]
>  GDI + ile Windows XP dahil edilmiştir ve Windows NT 4.0 SP 6, Windows 2000, Windows 98 ve Windows Me için yeniden dağıtılabilir olarak kullanılabilir En son yeniden yüklemek için bkz [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232).   
  
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