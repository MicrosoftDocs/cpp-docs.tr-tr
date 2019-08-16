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
ms.openlocfilehash: a63154f3da539676f31709899568b6486dc6017e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508527"
---
# <a name="handling-ttn_needtext-notification-for-tool-tips"></a>Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme

[Araç ipuçlarının etkinleştirilmesi](../mfc/enabling-tool-tips.md)kapsamında, sahip pencerenizin ileti eşlemesine aşağıdaki girdiyi ekleyerek **TTN_NEEDTEXT** iletisini işleyebilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*memberFxn*<br/>
Bu düğme için metin gerektiğinde çağrılacak üye işlev.

Araç ipucu KIMLIĞININ her zaman 0 olduğunu unutmayın.

Aşağıdaki gibi, sınıf tanımında işleyici işlevinizi bildirin:

[!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

italik parametrelerin bulunduğu yer:

*id*<br/>
Bildirimi gönderen denetimin tanımlayıcısı. Kullanılmadı. Denetim kimliği, **nmhdr** yapısından alınır.

*pNMHDR*<br/>
[Nmttdispınfo](/windows/win32/api/commctrl/ns-commctrl-nmttdispinfow) yapısına yönelik bir işaretçi. Bu yapı ayrıca [araç Ipucu yapısında](../mfc/tooltiptext-structure.md)daha da tartışılır.

*pResult*<br/>
Döndürmeden önce ayarlayabileceğiniz sonuç kodu işaretçisi. **TTN_NEEDTEXT** işleyicileri *pResult* parametresini yoksayabilir.

Bir form-görünüm bildirim işleyicisine örnek olarak:

[!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

Çağrı `EnableToolTips` (Bu parçanın alındığı yer `OnInitDialog`):

[!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
