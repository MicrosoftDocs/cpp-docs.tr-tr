---
title: "Dizeye biçimlendirme veya özel karakterler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 023f5e2ac4b74bb489ee5ef4ef2acffb01a05f55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>Dizeye Biçimlendirme veya Özel Karakterler Ekleme
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Dizeye biçimlendirme veya özel karakterler eklemek için  
  
1.  Dize tablosu simgesini çift tıklatarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Değiştirmek istediğiniz dizeyi seçin.  
  
3.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), herhangi bir standart kaçış sıraları aşağıda listelenen metinde eklemek **resim yazısı** kutusu ve tuşuna **ENTER**.  
  
    |Bu almak için|Bunu yazın|  
    |-----------------|---------------|  
    |Yeni satır|\n|  
    |satır başı|\r|  
    |Tab|\t|  
    |Ters eğik çizgi (\\)|\\\|  
    |ASCII karakter|\ddd (sekizlik biçim)|  
    |Uyarı (zil)|\a|  
  
> [!NOTE]
>  Dize Düzenleyicisi'ni Atlanan ASCI karakter kümesini desteklemiyor. Yalnızca Yukarıda listelenenler kullanabilirsiniz.  
  
 Kaynakları yönetilen projelere (olanlar ortak dil çalışma zamanı hedef) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynakları dizeleri özelliklerine atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme kaynaklarını kullanan](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize Düzenleyicisi](../windows/string-editor.md)   

