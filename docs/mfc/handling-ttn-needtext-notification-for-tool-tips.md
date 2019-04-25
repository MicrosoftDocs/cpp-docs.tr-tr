---
title: Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 97db98322cd7c0d14e46f54a055bbc646c90d785
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240395"
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

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
