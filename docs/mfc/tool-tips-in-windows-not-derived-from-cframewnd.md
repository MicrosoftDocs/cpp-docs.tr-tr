---
description: "Hakkında daha fazla bilgi edinin: CFrameWnd 'den türetilmemiş pencerelerin araç Ipuçları"
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
ms.openlocfilehash: 1d5d2ba744800424a9dce325f9d4341956bc22ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264433"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları

Bu makale ailesi, [CFrameWnd](../mfc/reference/cframewnd-class.md)'den türetilmemiş bir pencerede bulunan denetimler için araç ipuçlarının etkinleştirilmesini içerir. [Araç çubukları araç ipuçları](../mfc/toolbar-tool-tips.md) , içindeki denetimler için araç ipuçları hakkında bilgi sağlar `CFrameWnd` .

Bu makale ailesinde yer almayan konular şunlardır:

- [Araç Ipuçlarını etkinleştirme](../mfc/enabling-tool-tips.md)

- [Araç Ipuçları için TTN_NEEDTEXT Bildirimini İşleme](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT yapısı](../mfc/tooltiptext-structure.md)

Araç ipuçları, ' den türetilmiş bir üst pencerede bulunan düğmeler ve diğer denetimler için otomatik olarak görüntülenir `CFrameWnd` . Bunun nedeni `CFrameWnd` , denetimleriyle ilişkili araç ipucu denetimlerinin **TTN_NEEDTEXT** bildirimlerini işleyen [TTN_GETDISPINFO](/windows/win32/Controls/ttn-getdispinfo) bildirimi için varsayılan bir işleyicidir.

Ancak, bu varsayılan işleyici, bir  `CFrameWnd` iletişim kutusu veya form görünümü gibi olmayan bir penceredeki bir denetimle ilişkili bir araç ipucu denetiminden TTN_NEEDTEXT bildirimi gönderildiğinde çağrılmaz. Bu nedenle, alt denetimler için araç ipuçlarını göstermek üzere **TTN_NEEDTEXT** bildirim iletisi için bir işleyici işlevi sağlamanız gerekir.

[CWnd:: Enabletooltip 'ler](../mfc/reference/cwnd-class.md#enabletooltips) tarafından Windows için sunulan varsayılan araç ipuçları kendileriyle ilişkili metin içermez. Araç ipucu görüntülenecek metni almak için, **TTN_NEEDTEXT** bildirimi araç ipucu penceresi görüntülenmeden hemen önce araç ipucu denetiminin üst penceresine gönderilir. Bu ileti için **araç** Ipucu yapısının *pszText* üyesine bazı bir değer atayabilmesi için bir işleyici yoksa, araç ipucu için hiçbir metin görüntülenmeyecektir.

## <a name="see-also"></a>Ayrıca bkz.

[Araç Ipuçları](../mfc/tool-tips.md)
