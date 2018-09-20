---
title: Bir CStatusBarCtrl nesnesinde araç ipuçları kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f17dff6680209664e9d029404e4ef012b9f12046
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392365"
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

