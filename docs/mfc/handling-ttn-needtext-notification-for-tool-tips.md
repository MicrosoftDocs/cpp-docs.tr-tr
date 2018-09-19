---
title: Araç ipuçları için TTN_NEEDTEXT bildirimini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TTN_NEEDTEXT
dev_langs:
- C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ddfe6660854ae4cbdba2398aa4102fd612d17ddc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114585"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme
Bir parçası olarak [araç ipuçlarını etkinleştirme](../mfc/enabling-tool-tips.md), ele **TTN_NEEDTEXT** sahibi pencerenin ileti eşlemesi için şu girdiyi ekleyerek, ileti:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
*memberFxn*<br/>
Bu düğme için metin gerektiğinde çağrılacak üye işlevi.  
  
 Bir araç ipucu kimliği her zaman olduğuna dikkat edin 0.  
  
 Sınıf tanımında, işleyici işlevi şu şekilde bildirin:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 Burada italik Parametreler şunlardır:  
  
*id*<br/>
Bildirim gönderilen denetim tanımlayıcısı. Kullanılmadı. Denetim Kimliği alınır **NMHDR** yapısı.  
  
*pNMHDR*<br/>
Bir işaretçi [NMTTDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagnmttdispinfoa) yapısı. Bu yapı ayrıca ele alınan ayrıntılı olarak [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md).  
  
*pResult*<br/>
Sonuç kodu için bir işaretçi, dönmeden önce ayarlayabilirsiniz. **TTN_NEEDTEXT** işleyicileri yok sayabilirsiniz *pResult* parametresi.  
  
 Bir form görünümü bildirim işleyici, örneğin:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Çağrı `EnableToolTips` (alınan bu parçasını `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

