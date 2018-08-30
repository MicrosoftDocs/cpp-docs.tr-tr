---
title: Üstbilgi denetimine öğe ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6450d99b8df436c64337e52fc14244ecbb0edfc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206153"
---
# <a name="adding-items-to-the-header-control"></a>Üstbilgi Denetimine Öğe Ekleme
Sonra üstbilgi denetimi oluşturma ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) kendi üst penceresinde "gereksinim duyduğunuz kadar çok üstbilgi öğeleri" ekleyin: genellikle bir sütun başına.  
  
### <a name="to-add-a-header-item"></a>Üstbilgi öğesi eklemek için  
  
1.  Hazırlama bir [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) yapısı.  
  
2.  Çağrı [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), yapısı geçirme.  
  
3.  Adım 1 ve 2 ek öğeler için yineleyin.  
  
 Daha fazla bilgi için [bir üstbilgi denetimine öğe ekleme](/windows/desktop/Controls/header-controls) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

