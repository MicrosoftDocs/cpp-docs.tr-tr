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
ms.openlocfilehash: 1f68fb62335219ea498163e6124c8e91e49f2938
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511028"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları

Bu makale ailesi, [CFrameWnd](../mfc/reference/cframewnd-class.md)'den türetilmemiş bir pencerede bulunan denetimler için araç ipuçlarının etkinleştirilmesini içerir. [Araç çubukları araç ipuçları](../mfc/toolbar-tool-tips.md) , içindeki `CFrameWnd`denetimler için araç ipuçları hakkında bilgi sağlar.

Bu makale ailesinde yer almayan konular şunlardır:

- [Araç İpuçlarını Etkinleştirme](../mfc/enabling-tool-tips.md)

- [Araç İpuçları için TTN_NEEDTEXT Bildirimini İşleme](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md)

Araç ipuçları, ' den `CFrameWnd`türetilmiş bir üst pencerede bulunan düğmeler ve diğer denetimler için otomatik olarak görüntülenir. Bunun nedeni `CFrameWnd` , denetimleriyle ilişkili araç ipucu denetimlerinden **TTN_NEEDTEXT** bildirimlerini işleyen [TTN_GETDISPINFO](/windows/win32/Controls/ttn-getdispinfo) bildirimi için varsayılan bir işleyicidir.

Ancak, bu varsayılan işleyici, bir iletişim kutusu veya form görünümü gibi olmayan bir `CFrameWnd`penceredeki bir denetimle ilişkili bir araç ipucu denetiminden TTN_NEEDTEXT bildirimi gönderildiğinde çağrılmaz. Bu nedenle, alt denetimler için araç ipuçlarını göstermek üzere **TTN_NEEDTEXT** bildirim iletisi için bir işleyici işlevi sağlamanız gerekir.

[CWnd:: Enabletooltip 'ler](../mfc/reference/cwnd-class.md#enabletooltips) tarafından Windows için sunulan varsayılan araç ipuçları kendileriyle ilişkili metin içermez. Araç ipucu görüntülenecek metni almak için, **TTN_NEEDTEXT** bildirimi araç ipucu penceresi görüntülenmeden hemen önce araç ipucu denetiminin üst penceresine gönderilir. Bu ileti için **araç** Ipucu yapısının *pszText* üyesine bazı bir değer atayabilmesi için bir işleyici yoksa, araç ipucu için hiçbir metin görüntülenmeyecektir.

## <a name="see-also"></a>Ayrıca bkz.

[Araç İpuçları](../mfc/tool-tips.md)
