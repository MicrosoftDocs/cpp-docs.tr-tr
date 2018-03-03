---
title: "Devre dışı iken fare etkileşimi sağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2f8991b6cc827c35c94b0989ef82e32422fd5c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="providing-mouse-interaction-while-inactive"></a>Devre Dışı İken Fare Etkileşimi Sağlama
Denetim hemen etkinleştirilmemişse hala işlemek istediğiniz `WM_SETCURSOR` ve `WM_MOUSEMOVE` kendi pencere denetim olmasına rağmen iletileri. Bu etkinleştirerek gerçekleştirilebilir `COleControl`'s uyarlamasını `IPointerInactive` varsayılan olarak devre dışıdır arabirimi. (Bkz *ActiveX SDK* bu arabirim açıklaması.) Etkinleştirmek için dahil `pointerInactive` tarafından döndürülen bayraklar kümesi bayrağı [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 Seçerseniz bu bayrak eklemek için kodu otomatik olarak oluşturulan **fare işaretçisini bildirimleri, etkin olmayan** seçeneği [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında denetiminizi ile oluştururken**MFC ActiveX Denetim Sihirbazı**.  
  
 Zaman `IPointerInactive` arabirimi etkin olduğunda, kapsayıcı temsilcileri `WM_SETCURSOR` ve `WM_MOUSEMOVE` ona iletileri. `COleControl`kişinin uyarlamasını `IPointerInactive` fare ayarlama uygun şekilde düzenler sonra denetiminizin ileti eşlemesi üzerinden ileti gönderir. İleti eşlemesi karşılık gelen girdilere ekleyerek sıradan pencere iletileri gibi iletileri işleyebilir. Bu iletiler, işleyicileri kullanmaktan kaçının `m_hWnd` üye değişkeni (veya bunu kullanan herhangi bir üye işlevini) denetlemeden ilk değeri olmayan **NULL**.  
  
 OLE sürükle ve bırak işlemi hedefi için etkin olmayan bir denetimi de isteyebilirsiniz. Bu denetimin penceresi bir bırakma hedefi olarak kaydedilebilir böylece kullanıcı bir nesne bunun üzerine sürüklediği anda denetimi etkinleştirme gerektirir. Etkinleştirme sırasında bir Sürükle oluşmasına neden olmak için geçersiz kılma [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)ve geri dönüp **POINTERINACTIVE_ACTIVATEONDRAG** bayrağı:  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 Etkinleştirme `IPointerInactive` arabirimi genellikle anlamına gelir denetim her zaman fare iletileri işleyebilen istiyor. Desteklemeyen bir kapsayıcıda bu davranışı elde etmek üzere `IPointerInactive` arabirimi, denetiminizi görünür olduğunda, her zaman etkin olması gerekir denetimi yani içermelidir **OLEMISC_ACTIVATEWHENVISIBLE** arasında bayrak çeşitli bayraklar. Ancak, bu bayrağı önlemek için etkili bir kapsayıcıda alma desteğini `IPointerInactive`, ayrıca belirtebilirsiniz **OLEMISC_IGNOREACTIVATEWHENVISIBLE** bayrağı:  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

