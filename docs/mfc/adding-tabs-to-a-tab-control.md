---
title: Sekme denetimine sekmeler ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb8caad0b7d1f632a2d97e4ea6bda7c93a2b4d74
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218303"
---
# <a name="adding-tabs-to-a-tab-control"></a>Sekme Denetimine Sekmeler Ekleme
Sekme denetimi oluşturduktan sonra ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), ihtiyacınız kadar sekme ekleyin.  
  
### <a name="to-add-a-tab-item"></a>Sekme öğesi eklemek için  
  
1.  Hazırlama bir [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) yapısı.  
  
2.  Çağrı [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), yapısı geçirme.  
  
3.  Adım 1 ve 2 ek sekme öğeleri için yineleyin.  
  
 Daha fazla bilgi için [sekme denetimi oluşturma](/windows/desktop/Controls/tab-controls) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

