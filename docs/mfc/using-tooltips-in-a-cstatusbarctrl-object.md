---
title: Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 3f9a1fec7eb951fa76c542e09df751b4c58ddb16
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265099"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma

Durum çubuğu denetimi için araç ipuçları etkinleştirmek için oluşturma `CStatusBarCtrl` SBT_TOOLTIPS stiliyle nesne.

> [!NOTE]
>  Kullanıyorsanız bir `CStatusBar` kullanın, durum çubuğu uygulamak için nesne `CStatusBar::CreateEx` işlevi. Embedded için ek stilleri belirtmenize olanak tanır `CStatusBarCtrl` nesne.

Bir kez `CStatusBarCtrl` nesne başarıyla oluşturuldu, kullanın [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) ayarlayın ve belirli bir bölme ipucu metnini almak için.

Araç İpucu ayarladıktan sonra bu bölümü yalnızca bir simge ve metin varsa ya da tüm metin bölümü içinde görüntülenemiyor görüntülenir. Araç ipuçları, basit modunda desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
