---
title: "Araç ipuçları için TTN_NEEDTEXT bildirimini işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TTN_NEEDTEXT
dev_langs: C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26a3b74ca0bc11b169e195599c5172b245cf0529
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme
Bir parçası olarak [araç ipuçlarını etkinleştirme](../mfc/enabling-tool-tips.md), size işlemek **TTN_NEEDTEXT** sahibi pencerenin ileti eşlemesi için şu girdiyi ekleyerek ileti:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 Metin için bu düğmeyi gerektiğinde çağrılacak üye işlevi.  
  
 Araç İpucu kimliği her zaman olduğuna dikkat edin 0.  
  
 Sınıf tanımı İşleyici işlevinizde gibi bildirin:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 Burada italik Parametreler şunlardır:  
  
 `id`  
 Bildirimi tarafından gönderilen denetim tanımlayıcısı. Kullanılmadı. Denetim Kimliği alınırlar **NMHDR** yapısı.  
  
 `pNMHDR`  
 Bir işaretçi [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) yapısı. Bu yapı da ele alınmıştır daha ayrıntılı olarak [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Sonuç kodu için bir işaretçi dönmek önce ayarlayabilirsiniz. **TTN_NEEDTEXT** işleyicileri yoksayabilirsiniz `pResult` parametresi.  
  
 Form görünümünde bildirim işleyicisinin örnek olarak:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Çağrı `EnableToolTips` (alınan bu parçasını `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

