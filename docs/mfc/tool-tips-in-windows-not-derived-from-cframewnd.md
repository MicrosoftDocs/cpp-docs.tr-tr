---
title: CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları
ms.date: 11/04/2016
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
ms.openlocfilehash: 3d44f2c503b689360f040e6804d319c331d5c0ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168030"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları

Bu makalede ailesi türünden türetilmediğinden bir pencerede bulunan denetimler için etkinleştirme araç ipuçları kapsar [CFrameWnd](../mfc/reference/cframewnd-class.md). Makaleyi [araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md) denetimler için araç ipuçları hakkında bilgi sağlayan bir `CFrameWnd`.

Bu makalede ailesinde ele alınan konular:

- [Araç İpuçlarını Etkinleştirme](../mfc/enabling-tool-tips.md)

- [Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md)

Araç ipuçları için düğmeler otomatik olarak görüntülenir ve diğer denetimleri ana pencerede kapsanan türetilen `CFrameWnd`. Bunun nedeni, `CFrameWnd` için bir varsayılan işleyici sahip [TTN_GETDISPINFO](/windows/desktop/Controls/ttn-getdispinfo) işleyen bildirim **TTN_NEEDTEXT** bildirimleri aracından ipucu denetimleri ile ilişkili denetimler.

Ancak, bu varsayılan işleyici ne zaman çağrılmaz **TTN_NEEDTEXT** bir denetiminde olmayan bir pencere ile ilişkili bir araç ipucu denetiminden bildirim gönderilir bir `CFrameWnd`, bir iletişim kutusu veya bir form görünümü denetimi gibi. Bu nedenle, sizin için bir işleyici işlevi sağlamak için gerekli olan **TTN_NEEDTEXT** alt denetimler için araç ipuçları görüntülemek için bildirim iletisi.

Windows tarafından sağlanan varsayılan araç ipuçları [CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) ilişkili metin izniniz yok. Görüntülenecek araç ipucu metnini almak için **TTN_NEEDTEXT** yalnızca araç ipucu penceresi görüntülenmeden önce bildirim için araç ipucu denetiminin üst penceresine gönderilir. Bu ileti için bir değer atamak için işleyici yok ise *pszText* üyesi **TOOLTIPTEXT** yapısı, araç ipucu için görüntülenen metin olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Araç İpuçları](../mfc/tool-tips.md)
