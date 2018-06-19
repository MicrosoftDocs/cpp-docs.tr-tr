---
title: 'MFC ActiveX denetimleri: Olaylar | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6c8ee059b4136ce1504117246abd12ac74a6233
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348396"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX Denetimleri: Olaylar
ActiveX denetimleri olayları bir şey denetime gerçekleştirilmedi bir kapsayıcı bildirmek için kullanın. Ortak olaylar tıklama denetimindeki, klavye ve değişiklikleri denetimin durumda kullanarak girilen veri örneklerindendir. Bu eylemler ortaya çıktığında denetimi kapsayıcı uyarmak için bir olay gönderir.  
  
 Olaylar, iletileri olarak da adlandırılır.  
  
 MFC iki tür olay destekler: stok ve özel. Stok olaylardır sınıf olayları [COleControl](../mfc/reference/colecontrol-class.md) otomatik olarak yönetir. Stok olayları tam bir listesi için bkz: [MFC ActiveX denetimleri: stok olaylar ekleme](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Özel olaylar bir denetim denetime belirli bir eylem oluştuğunda kapsayıcı bildir olanağı sağlar. Bazı örnekler bir denetimin iç durumunu veya belirli bir pencere iletinin alınması, bir değişiklik olacaktır.  
  
 Denetim olayları düzgün tetiklenecek denetim sınıfınıza ilgili olay gerçekleştiğinde, çağrılmalıdır üye işlevi için her denetim olayının eşlemeniz gerekir. Bu eşleme mekanizması (bir olay eşlemesi olarak adlandırılır) olay hakkında bilgi merkezi hale getirir ve kolay erişim ve denetim olayları işlemek Visual Studio sağlar. Bu olay eşlemesi üstbilgisinde bulunan aşağıdaki makrosu tarafından bildirilen (. H) denetim sınıf bildiriminin dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]  
  
 Olay eşlemesi bildirildikten sonra onu denetiminizin uygulamasında tanımlanmış olması gerekir (. CPP) dosyası. Aşağıdaki kod satırlarını belirli olayları yangın denetim izin vererek olay eşlemesi tanımlayın:  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]  
  
 Projeyi oluşturmak için MFC ActiveX Denetim Sihirbazı'nı kullanırsanız, bu satırları otomatik olarak ekler. MFC ActiveX Denetim Sihirbazı'nı kullanmıyorsanız, bu satırları el ile eklemeniz gerekir.  
  
 Sınıf Görünümü ile sınıfı tarafından desteklenen stok olayları ekleyebilirsiniz `COleControl` ya da tanımladığınız özel olaylar. Yeni her olay için sınıf görünümü otomatik olarak denetimin olay eşlemesi ve Denetim doğru girişi ekler. IDL dosyası.  
  
 Diğer iki makaleleri olayları ayrıntılı ele alınmıştır:  
  
-   [MFC ActiveX denetimleri: Stok olaylar ekleme](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [MFC ActiveX Denetimleri: Özel Olaylar Ekleme](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
