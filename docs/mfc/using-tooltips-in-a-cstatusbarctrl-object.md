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
ms.openlocfilehash: a5ebefe3d5daab9917cdb1db7eface09c78b456a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438798"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma

Durum çubuğu denetimi için araç ipuçları etkinleştirmek için oluşturma `CStatusBarCtrl` SBT_TOOLTIPS stiliyle nesne.

> [!NOTE]
>  Kullanıyorsanız bir `CStatusBar` kullanın, durum çubuğu uygulamak için nesne `CStatusBar::CreateEx` işlevi. Embedded için ek stilleri belirtmenize olanak tanır `CStatusBarCtrl` nesne.

Bir kez `CStatusBarCtrl` nesne başarıyla oluşturuldu, kullanın [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) ayarlayın ve belirli bir bölme ipucu metnini almak için.

Araç İpucu ayarladıktan sonra bu bölümü yalnızca bir simge ve metin varsa ya da tüm metin bölümü içinde görüntülenemiyor görüntülenir. Araç ipuçları, basit modunda desteklenmez.

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

