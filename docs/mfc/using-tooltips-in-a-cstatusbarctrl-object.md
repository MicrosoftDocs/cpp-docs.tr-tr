---
title: Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: a607a5fb8c9470df42d12c771865b924891b2dac
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442546"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma

Bir durum çubuğu denetimi için araç ipuçlarını etkinleştirmek üzere SBT_TOOLTIPS stili ile `CStatusBarCtrl` nesnesini oluşturun.

> [!NOTE]
>  Durum çubuğunuzu uygulamak için bir `CStatusBar` nesnesi kullanıyorsanız, `CStatusBar::CreateEx` işlevini kullanın. Katıştırılmış `CStatusBarCtrl` nesnesi için ek stiller belirtmenize olanak tanır.

`CStatusBarCtrl` nesnesi başarıyla oluşturulduktan sonra, belirli bir bölme için ipucu metnini ayarlamak ve almak üzere [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) kullanın.

Araç ipucu ayarlandıktan sonra, yalnızca bölümde bir simge varsa ve metin yoksa veya metnin tamamı bölüm içinde görüntülenemediğinde görüntülenir. Araç ipuçları basit modda desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
