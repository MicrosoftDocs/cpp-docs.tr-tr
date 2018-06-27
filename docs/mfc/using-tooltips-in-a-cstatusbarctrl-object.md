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
ms.openlocfilehash: 9cce98e4a3b3ffd506607529b9fea6f0c1114cc3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951274"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
Durum çubuğu denetimi için araç ipuçları'ı etkinleştirmek üzere oluşturduğunuz `CStatusBarCtrl` SBT_TOOLTIPS stiliyle nesnesi.  
  
> [!NOTE]
>  Kullanıyorsanız bir `CStatusBar` durum çubuğu uygulamak, kullanmak için nesne `CStatusBar::CreateEx` işlevi. Katıştırılmış için ek stiller belirtmenize olanak tanır `CStatusBarCtrl` nesnesi.  
  
 Bir kez `CStatusBarCtrl` nesne başarıyla oluşturuldu, kullanın [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) ayarlamak ve belirli bir bölme ipucu metnini almak için.  
  
 Araç İpucu ayarladıktan sonra yalnızca bölüm bir simge ve metin varsa ya da tüm metni bölümü görüntülenemiyor görüntülenir. Araç ipuçları basit modunda desteklenmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

