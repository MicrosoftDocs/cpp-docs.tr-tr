---
description: 'Hakkında daha fazla bilgi edinin: CStatusBarCtrl nesnesinde araç Ipuçları kullanma'
title: Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: d77610a511698000dc70a1aa1cb1edb22fb3eb7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143253"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma

Bir durum çubuğu denetimi için araç ipuçlarını etkinleştirmek üzere `CStatusBarCtrl` SBT_TOOLTIPS stili ile nesnesini oluşturun.

> [!NOTE]
> `CStatusBar`Durum çubuğunuzu uygulamak için bir nesne kullanıyorsanız, `CStatusBar::CreateEx` işlevini kullanın. Katıştırılmış nesne için ek stiller belirtmenize olanak tanır `CStatusBarCtrl` .

`CStatusBarCtrl`Nesne başarıyla oluşturulduktan sonra, belirli bir bölme için ipucu metnini ayarlamak ve almak üzere [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) komutunu kullanın.

Araç ipucu ayarlandıktan sonra, yalnızca bölümde bir simge varsa ve metin yoksa veya metnin tamamı bölüm içinde görüntülenemediğinde görüntülenir. Araç ipuçları basit modda desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
