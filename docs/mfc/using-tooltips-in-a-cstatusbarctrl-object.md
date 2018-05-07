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
ms.openlocfilehash: 323f2861da9fcc498e34792c30c763b4dffb2fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinde Araç İpuçları Kullanma
Durum çubuğu denetimi için araç ipuçları'ı etkinleştirmek üzere oluşturduğunuz `CStatusBarCtrl` nesnesi ile **SBT_TOOLTIPS** stili.  
  
> [!NOTE]
>  Kullanıyorsanız bir `CStatusBar` durum çubuğu uygulamak, kullanmak için nesne `CStatusBar::CreateEx` işlevi. Katıştırılmış için ek stiller belirtmenize olanak tanır **CStatusBarCtrl** nesnesi.  
  
 Bir kez `CStatusBarCtrl` nesne başarıyla oluşturuldu, kullanın [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) ve [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) ayarlamak ve belirli bir bölme ipucu metnini almak için.  
  
 Araç İpucu ayarladıktan sonra yalnızca bölüm bir simge ve metin varsa ya da tüm metni bölümü görüntülenemiyor görüntülenir. Araç ipuçları basit modunda desteklenmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

