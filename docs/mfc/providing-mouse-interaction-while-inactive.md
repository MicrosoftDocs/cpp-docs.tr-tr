---
title: Devre dışı iken fare etkileşimi sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c322493a0ee1aebd068ffe1fedb695445b6274aa
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929500"
---
# <a name="providing-mouse-interaction-while-inactive"></a>Devre Dışı İken Fare Etkileşimi Sağlama
Denetiminizi hemen etkinleştirilmemişse, kendi pencere denetim olmasına rağmen işleme WM_SETCURSOR ve WM_MOUSEMOVE iletileri isteyebilirsiniz. Bu etkinleştirerek gerçekleştirilebilir `COleControl`'s uyarlamasını `IPointerInactive` varsayılan olarak devre dışıdır arabirimi. (Bkz *ActiveX SDK* bu arabirim açıklaması.) Etkinleştirmek için tarafından döndürülen bayraklar kümesi pointerInactive bayrağı dahil [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 Seçerseniz bu bayrak eklemek için kodu otomatik olarak oluşturulan **fare işaretçisini bildirimleri, etkin olmayan** seçeneği [denetim ayarlarını](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında denetiminizi ile oluştururken**MFC ActiveX Denetim Sihirbazı**.  
  
 Zaman `IPointerInactive` arabirimi etkinleştirildiğinde, kapsayıcı WM_SETCURSOR ve WM_MOUSEMOVE iletileri ona atar. `COleControl`kişinin uyarlamasını `IPointerInactive` fare ayarlama uygun şekilde düzenler sonra denetiminizin ileti eşlemesi üzerinden ileti gönderir. İleti eşlemesi karşılık gelen girdilere ekleyerek sıradan pencere iletileri gibi iletileri işleyebilir. Bu iletiler, işleyicileri kullanmaktan kaçının *m_hWnd* üye değişkeni (veya bunu kullanan herhangi bir üye işlevini) denetlemeden ilk değeri olmayan **NULL**.  
  
 OLE sürükle ve bırak işlemi hedefi için etkin olmayan bir denetimi de isteyebilirsiniz. Bu denetimin penceresi bir bırakma hedefi olarak kaydedilebilir böylece kullanıcı bir nesne bunun üzerine sürüklediği anda denetimi etkinleştirme gerektirir. Etkinleştirme sırasında bir Sürükle oluşmasına neden olmak için geçersiz kılma [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)ve POINTERINACTIVE_ACTIVATEONDRAG bayrağı döndürür:  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 Etkinleştirme `IPointerInactive` arabirimi genellikle anlamına gelir denetim her zaman fare iletileri işleyebilen istiyor. Desteklemeyen bir kapsayıcıda bu davranışı elde etmek üzere `IPointerInactive` arabirimi, denetiminizi görünür olduğunda, her zaman etkin olması gerekir denetimi başka bir deyişle, çeşitli bayraklarının arasında OLEMISC_ACTIVATEWHENVISIBLE bayrağı içermelidir. Ancak, bu bayrağı önlemek için etkili bir kapsayıcıda alma desteğini `IPointerInactive`, OLEMISC_IGNOREACTIVATEWHENVISIBLE bayrağını da belirtebilirsiniz:  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

