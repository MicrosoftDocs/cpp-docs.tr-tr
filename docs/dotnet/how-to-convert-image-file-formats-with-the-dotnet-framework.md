---
title: "Nasıl yapılır: .NET Framework ile resim dosyası biçimlerini dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eff94d00f92fe0a52162c986662209168974e072
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>Nasıl yapılır: .NET Framework ile Görüntü Dosyası Biçimlerini Dönüştürme
Aşağıdaki kod örneğinde gösterilmektedir <xref:System.Drawing.Image?displayProperty=fullName> sınıfı ve <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> resim dosyalarını dönüştürmek ve kaydetmek için kullanılan numaralandırması. Aşağıdaki kod bir .jpg dosyasından görüntüyü yükler ve .gif ve .bmp dosya biçimlerinde kaydeder.  
  
> [!NOTE]
>  GDI + Windows XP, Windows Server 2003 ve Windows Vista ile dahil edilmiştir ve Windows 2000 için yeniden dağıtılabilir olarak kullanılabilir. En son yeniden yüklemek için bkz [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232).   
  
## <a name="example"></a>Örnek  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing>   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)