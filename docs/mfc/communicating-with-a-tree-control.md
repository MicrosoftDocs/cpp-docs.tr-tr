---
title: "Ağaç denetimi ile iletişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33835dcaa40b217e9248e5c03b775f968332b687
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim
Üye işlevleri çağırmak için farklı yöntemler kullanın bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:  
  
-   Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` iletişim kutusu sınıfında oluşturun.  
  
-   Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesne (veya işaretçi) nesnesi oluşturmak için kullandığınız.  
  
-   Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi başvuru alınamıyor. Bu değer ile başka bir başvuru başlatmak veya başvuru adresi atamak bir `CTreeCtrl` işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

