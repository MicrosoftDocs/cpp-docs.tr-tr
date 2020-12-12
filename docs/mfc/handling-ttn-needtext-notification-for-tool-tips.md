---
description: 'Hakkında daha fazla bilgi edinin: araç Ipuçları için TTN_NEEDTEXT bildirimi Işleme'
title: Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 793f6c42e0e43c341884b999e5e1aed0be448b00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326424"
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

*id*<br/>
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
