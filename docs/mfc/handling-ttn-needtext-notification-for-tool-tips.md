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
ms.openlocfilehash: 75850dbf92587cf654d4f7a39ea54af1fd9dd5bd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620076"
---
# <a name="handling-ttn_needtext-notification-for-tool-tips"></a>Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme

[Araç ipuçlarının etkinleştirilmesi](enabling-tool-tips.md)kapsamında, sahip pencerenizin ileti eşlemesine aşağıdaki girişi ekleyerek **TTN_NEEDTEXT** iletisini işleyebilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#40](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*memberFxn*<br/>
Bu düğme için metin gerektiğinde çağrılacak üye işlev.

Araç ipucu KIMLIĞININ her zaman 0 olduğunu unutmayın.

Aşağıdaki gibi, sınıf tanımında işleyici işlevinizi bildirin:

[!code-cpp[NVC_MFCControlLadenDialog#53](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

italik parametrelerin bulunduğu yer:

*numarasını*<br/>
Bildirimi gönderen denetimin tanımlayıcısı. Kullanılmadı. Denetim kimliği, **nmhdr** yapısından alınır.

*pNMHDR*<br/>
[Nmttdispınfo](/windows/win32/api/commctrl/ns-commctrl-nmttdispinfow) yapısına yönelik bir işaretçi. Bu yapı ayrıca [araç Ipucu yapısında](tooltiptext-structure.md)daha da tartışılır.

*pResult*<br/>
Döndürmeden önce ayarlayabileceğiniz sonuç kodu işaretçisi. **TTN_NEEDTEXT** işleyiciler *pResult* parametresini yoksayabilir.

Bir form-görünüm bildirim işleyicisine örnek olarak:

[!code-cpp[NVC_MFCControlLadenDialog#54](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

Çağrı `EnableToolTips` (Bu parçanın alındığı yer `OnInitDialog` ):

[!code-cpp[NVC_MFCControlLadenDialog#55](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd 'den türetilmemiş pencerelerin araç Ipuçları](tool-tips-in-windows-not-derived-from-cframewnd.md)
