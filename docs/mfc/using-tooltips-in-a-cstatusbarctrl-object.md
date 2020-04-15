---
title: Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 29d326c708743424686d616bbaf172ccd72481ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374702"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma

Durum çubuğu denetimi için araç uçlarını `CStatusBarCtrl` etkinleştirmek için nesneyi SBT_TOOLTIPS stiliyle oluşturun.

> [!NOTE]
> Durum çubuğunuzu `CStatusBar` uygulamak için bir nesne kullanıyorsanız, `CStatusBar::CreateEx` işlevi kullanın. Katıştılmış `CStatusBarCtrl` nesne için ek stiller belirtmenizi sağlar.

Nesne `CStatusBarCtrl` başarıyla oluşturulduktan sonra, belirli bir bölme için ipucu metnini ayarlamak ve almak için [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl::GetTipText'i](../mfc/reference/cstatusbarctrl-class.md#gettiptext) kullanın.

Araç ipucu ayarlandıktan sonra, yalnızca parçada bir simge varsa ve metin yoksa veya metnin tamamı parçanın içinde görüntülenemiyorsa görüntülenir. Araç ipuçları basit modda desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
