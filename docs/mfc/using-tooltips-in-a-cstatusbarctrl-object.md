---
title: "Bir CStatusBarCtrl nesnesinde araç ipuçları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

