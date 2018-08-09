---
title: İletişim kutusunu test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf9e5e24e77a14b3baf86c1b83d653dd833ebbbb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652077"
---
# <a name="testing-a-dialog-box"></a>İletişim Kutusunu Test Etme
Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derlemeden çalışma zamanı davranışını sınama. Bu modda şunları yapabilirsiniz:  
  
-   Bir metin yazın, birleşik giriş kutusu listelerinden seçin, seçeneklerini açıp kapatabilir ve komutları seçin.  
  
-   Sekme sırasını test edin.  
  
-   Radyo düğmeleri ve onay kutuları gibi gruplandırmalarını test edin.  
  
-   İletişim kutusundaki denetimlerin klavye kısayollarını test.  
  
    > [!NOTE]
    >  Sihirbazları kullanarak yapılan iletişim kutusu kodu bağlantıları benzetime dahil edilmez.  
  
 Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresiyle ilişkili bir konumda görüntüler. İletişim kutusunun ayarladıysanız **mutlak hizalama** özelliğini **True**, ekranın sol üst köşesine göre olan konumda iletişim kutusunu görüntüler.  
  
### <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu test etmek için  
  
1.  İletişim kutusu Düzenleyicisi etkin pencere menü çubuğunda, olduğunda seçin **biçimi**, **Test iletişim**.  
  
2.  Benzetimi bitirmek için basın **Esc**, veya yalnızca seçin **Kapat** test ettiğiniz iletişim kutusundaki düğmesi.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)   
 [İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)