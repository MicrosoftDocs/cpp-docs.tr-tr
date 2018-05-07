---
title: Üstbilgi öğeleri için sürükle ve bırak desteği sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50cd19d4828269d0591afd0b46768e9917b96906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama
Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak üzere belirtin `HDS_DRAGDROP` stili. Üstbilgi öğeleri için sürükle ve bırak desteği kullanıcı üstbilgi denetimi üstbilgi öğeleri yeniden sıralama olanağı sağlar. Üstbilgi öğesi kesilirse varsayılan davranışı sürüklenen üstbilgi öğesi yarı saydam Sürükle görüntüsünü ve yeni konumu görsel bir gösterge sağlar.  
  
 Ortak sürükle ve bırak işlevselliği ile işleyerek varsayılan sürükle ve bırak davranışı genişletebilirsiniz gibi **HDN_BEGINDRAG** ve **HDN_ENDDRAG** bildirimleri. Geçersiz kılarak Sürükle resmin görünümünü özelleştirebilirsiniz [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevi.  
  
> [!NOTE]
>  Liste denetimi katıştırılmış üstbilgi denetimindeki için sürükle ve bırak desteği sağlama, genişletilmiş stili bölümüne bakın. [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md) konu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

