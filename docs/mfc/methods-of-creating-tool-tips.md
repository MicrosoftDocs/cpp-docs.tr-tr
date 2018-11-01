---
title: Araç İpuçları Oluşturma Yöntemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: 80c826b3c9a4f9e24ebd201eaa9d775f9ad9f8cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663820"
---
# <a name="methods-of-creating-tool-tips"></a>Araç İpuçları Oluşturma Yöntemleri

MFC ipucu denetimi oluşturmak ve Aracı'nı yönetmek için üç sınıf sunar: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) ve [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Windows ortak denetim API'si bu sınıflardaki araç ipucu üye işlevleri kaydır. Sınıf `CToolBarCtrl` ve sınıf `CToolTipCtrl` sınıfından türetilen `CWnd`.

`CWnd` oluşturmak ve araç ipuçları yönetmek için dört üye işlevleri sağlar: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), ve [OnToolHitTest ](../mfc/reference/cwnd-class.md#ontoolhittest). Bu tek tek üye işlevleri araç ipuçları nasıl uyguladıkları hakkında daha fazla bilgi için bkz.

Bir araç kullanarak oluşturursanız `CToolBarCtrl`, aşağıdaki üye işlevleri kullanarak doğrudan bu araç için araç ipuçları uygulayabilir: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) ve [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). Bu tek tek üye işlevleri ve [araç ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md) araç ipuçları nasıl uyguladıkları hakkında daha fazla bilgi.

`CToolTipCtrl` Sınıfı Windows ortak araç ipucu denetimi işlevlerini sağlar. Tek araç ipucunu denetimini birden fazla aracı için bilgi sağlayabilir. Bir pencerenin istemci alanı içindeki uygulama tarafından tanımlanan dikdörtgen alan bir alt pencere veya denetim gibi bir ya da pencere bir araçtır. [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) sınıf türetilir `CToolTipCtrl` ve ek görsel stilleri ve işlevleri sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

