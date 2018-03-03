---
title: "Menüler ve kaynaklar: kapsayıcı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
dev_langs:
- C++
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 654efeaacd08e0d2c8c51cee012fd58dcbf071ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-container-additions"></a>Menüler ve Kaynaklar: Kapsayıcı Ekleme
Bu makalede menüleri ve diğer kaynaklara bir görsel düzenleme kapsayıcı uygulamasında yapılması gereken değişiklikleri açıklar.  
  
 Yapılacak değişiklikler iki tür kapsayıcı uygulamalarda gerekir: OLE görsel düzenleme ve yerinde etkinleştirme için kullanılan yeni kaynaklar desteklemek için varolan kaynakları yapılan değişiklikler. Kapsayıcı uygulamanızı oluşturmak için Uygulama Sihirbazı'nı kullanırsanız adımları sizin için yapılır, ancak bazı özelleştirme gerektirebilir.  
  
 Uygulama Sihirbazı'nı kullanmıyorsanız OCLIENT aramak isteyebilirsiniz. RC, bu değişikliklerin nasıl uygulandığı görmek için OCLIENT örnek uygulama için kaynak komut dosyası. MFC OLE örnek bkz [OCLIENT](../visual-cpp-samples.md).  
  
 Bu makalede ele alınan konular şunlardır:  
  
-   [Kapsayıcı menüsü ekleme](#_core_container_menu_additions)  
  
-   [Hızlandırıcı tablo ekleme](#_core_container_application_accelerator_table_additions)  
  
-   [Dize tablo ekleme](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a>Kapsayıcı menüsü ekleme  
 Düzen menüsü aşağıdaki öğeleri eklemeniz gerekir:  
  
|Öğe|Amaç|  
|----------|-------------|  
|**Yeni Nesne Ekle**|Belgeye bağlı veya katıştırılmış bir öğe eklemek için OLE Nesne Ekle iletişim kutusunu açar.|  
|**Bağlantı Yapıştır**|Öğesine bağlantı Pano'ya belgeye gönderebilir.|  
|**OLE eylemi**|Seçilen öğenin birincil fiil çağırır. Seçilen öğenin birincil fiil yansıtmak üzere bu menü öğesi değişikliklerini metin.|  
|**Bağlantılar**|Varolan bağlı öğeleri değiştirmek için OLE bağlantıları Düzenle iletişim kutusunu açar.|  
  
 Bu makalede listelenen değişikliklerin yanı sıra, kaynak dosyanızı AFXOLECL eklemeniz gerekir. RC için Microsoft Foundation Class Kitaplığı uygulaması gereklidir. Yeni nesne eklemeyi yalnızca gerekli menü ektir. Diğer öğeler eklenebilir, ancak burada listelenen en yaygın olanlardır.  
  
 Yerinde etkinleştirme içerilen öğelerin desteklemek istiyorsanız, kapsayıcı uygulamanız için yeni bir menü oluşturmanız gerekir. Bu menü dosyaları açık, ancak aralarında yerleştirilen iki ayırıcı sahip kullanılan penceresi açılır menüler ve aynı dosya menüsü oluşur. Bu ayırıcılar (uygulama) sunucusu (Bileşen) öğesini yerinde etkinleştirildiğinde menülerini nereye belirtmek için kullanılır. Bu menü birleştirme teknik hakkında daha fazla bilgi için bkz: [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md).  
  
##  <a name="_core_container_application_accelerator_table_additions"></a>Kapsayıcı uygulama Hızlandırıcı tablo ekleme  
 Bir kapsayıcı uygulama Hızlandırıcı tablosu kaynaklarına küçük değişikliklere yerinde etkinleştirme destekleniyorsa gereklidir. İlk değişiklik (ESC) yerinde düzenleme modunu iptal etmek için ESC tuşuna basın olanak tanır. Şu girdiyi ana Hızlandırıcı tabloya ekleyin:  
  
|Kimlik|Anahtar|Tür|  
|--------|---------|----------|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
 İkinci yerinde etkinleştirme için oluşturulan yeni menü kaynağa karşılık gelen yeni bir Hızlandırıcı tablosu oluşturmak için farklıdır. Bu tablo için ek olarak dosya ve pencere menüleri girişlerine sahip **VK_ESCAPE** yukarıdaki girişi. Aşağıdaki örnek MFC örnek yerinde etkinleştirme için oluşturulan Hızlandırıcı tablodur [KAPSAYICI](../visual-cpp-samples.md):  
  
|Kimlik|Anahtar|Tür|  
|--------|---------|----------|  
|`ID_FILE_NEW`|CTRL + N|**VIRTKEY**|  
|`ID_FILE_OPEN`|CTRL+O|**VIRTKEY**|  
|**ID_FILE_SAVE**|CTRL+S|**VIRTKEY**|  
|**ID_FILE_PRINT**|CTRL + P|**VIRTKEY**|  
|**ID_NEXT_PANE**|VK_F6|**VIRTKEY**|  
|**ID_PREV_PANE**|SHIFT + VK_F6|**VIRTKEY**|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a>Dize tablo eklemeleri için kapsayıcı uygulamaları  
 Dize tabloları kapsayıcı uygulamaları için yapılan değişiklikler çoğunu karşılık belirtilen ek menü öğelerini [kapsayıcı menü eklemeleri](#_core_container_menu_additions). Bunlar, her bir menü öğesi görüntülendiğinde durum çubuğunda görüntülenen metni sağlayın. Örnek olarak, Uygulama Sihirbazı'nın ürettiği dize tablosu girdileri şunlardır:  
  
|Kimlik|Dize|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE başlatma başarısız oldu. OLE kitaplıklarının sürümünün doğru olduğundan emin olun.|  
|**IDP_FAILED_TO_CREATE**|Nesne oluşturma başarısız oldu. Nesnenin sistem kayıt defterinde girildiğinden emin olun.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)   
 [Menüler ve Kaynaklar: Sunucu Ekleme](../mfc/menus-and-resources-server-additions.md)

