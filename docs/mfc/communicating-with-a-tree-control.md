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
ms.workload: cplusplus
ms.openlocfilehash: 2ef1188c9519e57c8132a2b20fc3b272d6c0ac51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim
Üye işlevleri çağırmak için farklı yöntemler kullanın bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:  
  
-   Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` iletişim kutusu sınıfında oluşturun.  
  
-   Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesne (veya işaretçi) nesnesi oluşturmak için kullandığınız.  
  
-   Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi başvuru alınamıyor. Bu değer ile başka bir başvuru başlatmak veya başvuru adresi atamak bir `CTreeCtrl` işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

