---
description: 'Hakkında daha fazla bilgi edinin: araç Ipuçları oluşturma yöntemleri'
title: Araç İpuçları Oluşturma Yöntemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: fc710f569e78f9698cdc924a071489c03b2975b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203113"
---
# <a name="methods-of-creating-tool-tips"></a>Araç İpuçları Oluşturma Yöntemleri

MFC araç ipucu denetimini oluşturmak ve yönetmek için üç sınıf sağlar: [CWnd](reference/cwnd-class.md), [CToolBarCtrl](reference/ctoolbarctrl-class.md), [CToolTipCtrl](reference/ctooltipctrl-class.md) ve [CMFCToolTipCtrl](reference/cmfctooltipctrl-class.md). Bu sınıflardaki araç ipucu üye işlevleri Windows ortak denetim API 'sini sarmalıdır. Sınıf `CToolBarCtrl` ve sınıf sınıfından `CToolTipCtrl` türetilir `CWnd` .

`CWnd` Araç ipuçlarını oluşturmak ve yönetmek için dört üye işlevi sağlar: [Enabletooltip](reference/cwnd-class.md#enabletooltips), [canceltooltip](reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](reference/cwnd-class.md#filtertooltipmessage)ve [OnToolHitTest](reference/cwnd-class.md#ontoolhittest). Araç ipuçlarını nasıl uygutıkları hakkında daha fazla bilgi için bu bireysel üye işlevlerine bakın.

Kullanarak bir araç çubuğu oluşturursanız `CToolBarCtrl` , şu üye işlevlerini kullanarak doğrudan bu araç çubuğu için araç ipuçları uygulayabilirsiniz: [GetToolTip](reference/ctoolbarctrl-class.md#gettooltips) 'Ler ve [SetToolTip](reference/ctoolbarctrl-class.md#settooltips)'ler. Araç ipuçlarını nasıl uygulayacağıyla ilgili daha fazla bilgi için bu bireysel üye işlevleri ve [Işleme aracı Ipucu bildirimlerine](handling-tool-tip-notifications.md) bakın.

`CToolTipCtrl`Sınıfı, Windows ortak araç ipucu denetimi işlevlerini sağlar. Tek bir araç ipucu denetimi, birden fazla araç için bilgi sağlayabilir. Bir araç, alt pencere veya denetim gibi bir pencere ya da bir pencerenin istemci alanı içindeki uygulama tanımlı dikdörtgen bir alandır. [CMFCToolTipCtrl](reference/cmfctooltipctrl-class.md) sınıfı öğesinden türetilir `CToolTipCtrl` ve ek görsel stilleri ve işlevleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](using-ctooltipctrl.md)<br/>
[Denetimler](controls-mfc.md)
