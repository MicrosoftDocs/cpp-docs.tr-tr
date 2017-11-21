---
title: "Bir iletişim kutusunu test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca6e6cd8dd9f7d67ba8a000f33143a12c0978a25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="testing-a-dialog-box"></a>İletişim Kutusunu Test Etme
Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derleme olmadan çalışma zamanı davranışını sınama. Bu modda, şunları yapabilirsiniz:  
  
-   Bir metin yazın, birleşik giriş kutusu listelerden seçin, seçenekleri Aç veya kapat ve komutları seçin.  
  
-   Sekme sırasını test edin.  
  
-   Radyo düğmeleri ve onay kutuları gibi denetimleri gruplandırma sınayın.  
  
-   Denetimler için klavye kısayolları iletişim kutusunda sınayın.  
  
    > [!NOTE]
    >  İletişim kutusu kodu sihirbazları kullanarak yapılan bağlantılar benzetim dahil edilmez.  
  
 Bir iletişim kutusu test ettiğinizde, genellikle bir konumdaki ana program penceresi göre görüntüler. İletişim kutusunun mutlak Align özelliği True olarak ayarladıysanız, ekranın sol üst köşesinde göre olduğu bir konuma iletişim kutusunu görüntüler.  
  
### <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu sınamak için  
  
1.  İletişim kutusu Düzenleyicisi menü çubuğunda, etkin pencereyi olduğunda seçin **biçimi**, **Test iletişim**.  
  
2.  Benzetim sonlandırmak için Esc tuşuna basın veya yalnızca seçin **Kapat** test ettiğiniz iletişim kutusunda düğme.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)   
 [Gösteren veya iletişim kutusu Düzenleyicisi araç çubuğunu gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

