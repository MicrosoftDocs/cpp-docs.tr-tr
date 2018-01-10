---
title: "Üstbilgi denetimine öğe ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4de62d534da103f17df113b04b88021561739cfc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-items-to-the-header-control"></a>Üstbilgi Denetimine Öğe Ekleme
Üstbilgi denetimi oluşturduktan sonra ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) kendi üst penceresinde "gerektiği kadar üstbilgi öğeleri" ekleyin: genellikle bir sütun başına.  
  
### <a name="to-add-a-header-item"></a>Üstbilgi öğesi eklemek için  
  
1.  Hazırlama bir [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) yapısı.  
  
2.  Çağrı [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), yapısı geçirme.  
  
3.  Adım 1 ve 2 ek öğeler için yineleyin.  
  
 Daha fazla bilgi için bkz: [bir üstbilgi denetimine öğe ekleme](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

