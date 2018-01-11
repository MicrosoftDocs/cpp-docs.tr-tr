---
title: "Özellik bölümleri ve özellik sayfaları (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 877d83a6833b9505c326bc5312d2f151add07cb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-mfc"></a>Özellik Bölümleri ve Özellik Sayfaları (MFC)
Bir MFC [iletişim kutusu](../mfc/dialog-boxes.md) "iletişim sekmesinde" bir görünüm üzerinde özellik bölümleri ve özellik sayfaları ekleme alabilir. "Özellik sayfası" adı verilen MFC'de dosya klasörleri yedeklemek için ön veya bir grup art arda windows görülen yığınını benzediğini sekmeli sayfaları yığınını içerecek şekilde bu tür bir Microsoft Word, Excel ve Visual C++, birçok iletişim kutularında benzer iletişim kutusu görüntülenir. Ön sekmesindeki denetimleri görünür; Yalnızca etiketli sekme arka sekmelerde görülebilir. Özellik sayfaları çok sayıda özellikleri veya oldukça düzgün çeşitli gruplar halinde kalan ayarlarını yönetmek için özellikle yararlıdır. Genellikle, bir özellik sayfasını, birçok ayrı iletişim kutuları değiştirerek bir kullanıcı arabirimi basitleştirebilir.  
  
 MFC sürüm 4. 0'dan sonra özellik bölümleri ve özellik sayfaları Windows 95 ve Windows NT sürüm ile 3.51 ve daha sonra gelen ortak denetimleri kullanma uygulanır.  
  
 Özellik sayfaları sınıflarıyla uygulanır [CPropertySheet](../mfc/reference/cpropertysheet-class.md) ve [CPropertyPage](../mfc/reference/cpropertypage-class.md) (açıklanan *MFC başvurusu*). `CPropertySheet`"birden çok sayfa temel" içerebilir genel iletişim kutusu, tanımlar `CPropertyPage`.  
  
 Oluşturma ve özellik sayfaları ile çalışma hakkında daha fazla bilgi için Ek Yardım konusuna [özellik sayfalarını](../mfc/property-sheets-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [Özellik sayfaları ve MFC'de özellik sayfaları](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Veri Değişimi](../mfc/exchanging-data.md)   
 [Kalıcı olmayan özellik sayfası oluşturma](../mfc/creating-a-modeless-property-sheet.md)   
 [Uygula Düğmesini İşleme](../mfc/handling-the-apply-button.md)

