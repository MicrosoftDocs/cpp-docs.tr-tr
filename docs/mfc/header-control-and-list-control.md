---
title: "Üstbilgi denetimi ve liste denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 213d2eeec7628c54d68bbd8f636ae85d90e7e8de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="header-control-and-list-control"></a>Üstbilgi Denetimi ve Liste Denetimi
Çoğu durumda, katıştırılmış üstbilgi denetimi kullanacağı bir [CListCtrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) nesnesi. Ancak, ayrı bir üstbilgi denetim nesnesi olduğu arzu sütunlara veya satırlara, düzenlenmiş veri düzenleme gibi durumlarda vardır bir [CView](../mfc/reference/cview-class.md)-türetilmiş bir nesne içermelidir. Bu durumlarda, katıştırılmış üstbilgi denetimi varsayılan davranışı ve görünümü üzerinde daha fazla denetim gerekir.  
  
 Standart sağlamak için bir üstbilgi denetimi istediğiniz ortak durumda varsayılan davranışı, kullanmak istediğiniz [CListCtrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) yerine. Kullanım `CListCtrl` katıştırılmış bir liste görünümü ortak denetiminde varsayılan üstbilgi denetimi işlevselliğini istediğinizde. Kullanım [CListView](../mfc/reference/clistview-class.md) bir görünüm nesnesini embedded varsayılan üstbilgi denetimi işlevselliğini istediğinizde.  
  
> [!NOTE]
>  Liste Görünümü denetimi kullanarak oluşturduysanız, bu denetimlerin yalnızca yerleşik üstbilgi denetimi dahil `LVS_REPORT` stili.  
  
 Çoğu durumda, katıştırılmış üstbilgi denetiminin görünümünü içeren liste görünümü denetimi stilleri değiştirerek değiştirilebilir. Ayrıca, üstbilgi denetimi hakkında bilgi üst liste görünümü denetimi üye işlevleri alınabilir. Ancak, tam denetim ve erişim katıştırılmış üstbilgi denetimi stillerini ve öznitelikleri için üstbilgi denetim nesnesi için bir işaretçi alınması önerilir.  
  
 Katıştırılmış üstbilgi denetim nesnesi herhangi birinden erişilebilir **CListCtrl** veya `CListView` ilgili sınıfın çağrısıyla `GetHeaderCtrl` üye işlevi. Aşağıdaki kod bu gösterir:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Üstbilgi denetimleriyle resim listeleri kullanma](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

