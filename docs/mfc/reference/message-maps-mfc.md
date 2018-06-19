---
title: İleti eşlemeleri (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1479ac7cb119ef206f8c20b6fa53bf7017b8ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371718"
---
# <a name="message-maps-mfc"></a>İleti Eşlemeleri (MFC)
Bu başvuru bölümü tüm listeler [ileti eşleme makroları](../../mfc/reference/message-map-macros-mfc.md) ve tüm [CWnd](../../mfc/reference/cwnd-class.md) karşılık gelen üye yanı sıra ileti eşleme girişleri işlev prototipleri:  
  
|Kategori|Açıklama|  
|--------------|-----------------|  
|ON\_KOMUTU ileti işleyicisi|İşleme `WM_COMMAND` kullanıcı menü seçimlerini veya menü erişim tuşları tarafından üretilen iletileri.|  
|[Alt Pencere Bildirim İletisi İşleyicileri](../../mfc/reference/child-window-notification-message-handlers.md)|Alt Windows bildirim iletilerini işleme.|  
|[WM_ ileti işleyicileri](../../mfc/reference/handlers-for-wm-messages.md)|İşleme `WM_` gibi iletilerini `WM_PAINT`.|  
|[Kullanıcı tarafından tanımlanan ileti işleyicileri](../../mfc/reference/user-defined-handlers.md)|Kullanıcı tanımlı iletileri işleyin.|  
  
 (Bu başvuruda kullanılan kuralları ve terminolojisi genel açıklaması için bkz: [ileti eşleme çapraz başvurusunu kullanma](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)  
  
 Windows bir iletiye yönelik işletim sistemi olduğundan ileti işleme programlama Windows ortamı için büyük bölümünü içerir. Her oluştuğunda bir tuş vuruşu veya fare gibi bir olay'ı tıklatın, sonra olay işlemesi uygulamaya bir ileti gönderilir.  
  
 Microsoft Foundation Class Kitaplığı ileti tabanlı programlama için en iyi hale getirilmiş bir programlama modeli sunar. Bu modelde, "eşlemeleri iletisi" hangi işlevleri belirli bir sınıf için çeşitli iletileri işleyecek atamak için kullanılır. İleti eşlemeleri hangi işlevleri tarafından hangi iletilerin işleneceğini belirten bir veya daha fazla makroları içerir. Örneğin, bir ileti eşleme içeren bir `ON_COMMAND` makrosu şöyle görünebilir:  
  
 [!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]  
  
 `ON_COMMAND` Makrosu menüleri, düğmeler ve Hızlandırıcı tuşları tarafından oluşturulan komut iletileri işlemek için kullanılır. [Makroları](../../mfc/reference/message-map-macros-mfc.md) aşağıdaki eşleştirmek kullanılabilir:  
  
## <a name="windows-messages"></a>Windows iletileri  
  
-   Denetim bildirimleri  
  
-   Kullanıcı tanımlı iletiler  
  
## <a name="command-messages"></a>Komut iletileri  
  
-   Kayıtlı kullanıcı tanımlı iletiler  
  
-   Kullanıcı arabirimi güncelleştirme iletileri  
  
## <a name="ranges-of-messages"></a>İleti aralıkları  
  
-   Komutlar  
  
-   Güncelleştirme işleyici iletileri  
  
-   Denetim bildirimleri  
  
 İleti eşleme makroları önemli olsa da, genellikle doğrudan kullanmanız gerekmez. İleti işleme işlevleri iletileri ile ilişkilendirmek için kullandığınızda Özellikler penceresini ileti eşleme girişleri Kaynak dosyalarınız otomatik olarak oluşturur. olmasıdır. Düzenlemek veya bir ileti eşleme girdisi eklemek için istediğiniz zaman Özellikler penceresini kullanabilirsiniz.  
  
> [!NOTE]
>  Özellikler penceresini ileti eşleme aralıkları desteklemez. Bu ileti eşleme girişleri kendiniz yazmanız gerekir.  
  
 Ancak, ileti eşlemeleri Microsoft Foundation Class Kitaplığı, önemli bir parçasıdır. Ne yaptıklarını anlamanız gerekir ve belgeleri için sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

