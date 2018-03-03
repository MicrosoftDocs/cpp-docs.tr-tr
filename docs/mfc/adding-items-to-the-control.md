---
title: "Denetime öğe ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d117aa06f82da1024d11af38cc4277916c6bca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-items-to-the-control"></a>Denetime Öğe Ekleme
Liste denetimi öğeler eklemek için ([CListCtrl](../mfc/reference/clistctrl-class.md)), birkaç sürümlerinden birini çağrısı [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) , hangi bilgilere bağlı olarak üye işlevi. Bir sürüm alır bir [LV_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) hazırlamanız yapısı. Çünkü `LV_ITEM` yapısı çok sayıda üye içeren, liste denetim öğesi özniteliklerini daha fazla denetime sahip olursunuz.  
  
 (İn regard to rapor görünümü) iki önemli üyeleri `LV_ITEM` yapılar `iItem` ve `iSubItem` üyeleri. `iItem` Üyesidir yapısı başvurduğu öğenin sıfır tabanlı dizini ve `iSubItem` üyesi ise bir alt ya da sıfır tabanlı dizin yapısı bir öğesiyle ilgili bilgileri içerir. Bu iki üyeleriyle, öğesi, türü ve liste denetimi rapor görünümünde olduğunda görüntülenen alt bilgi değerini belirler. Daha fazla bilgi için bkz: [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem).  
  
 Ek üyeleri öğesi'nin metin, simge, durumu ve öğe verileri belirtin. "Öğe verileri" bir liste görünümü öğesi ile ilişkili bir uygulama tanımlı değeri. Hakkında daha fazla bilgi için `LV_ITEM` yapısı için bkz: [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem).  
  
 Diğer sürümleri `InsertItem` üyelerine karşılık gelen bir veya daha fazla ayrı değerleri alır `LV_ITEM` yapısı, yalnızca desteklemek istediğiniz üyeleri başlatma olanak sağlar. Genellikle, liste öğeleri için depolama liste denetimi yönetir, ancak bazı bilgiler uygulamanızda bunun yerine, "geri çağrı öğeleri" kullanarak depolayabileceğiniz Daha fazla bilgi için bkz: [geri çağrı öğeleri ve geri çağrı maskesi](../mfc/callback-items-and-the-callback-mask.md) Bu konu başlığı ve [geri çağrı öğeleri ve geri çağrı maskesi](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [liste görünümü öğeleri ekleme ve alt öğeler](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

