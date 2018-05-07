---
title: Ağaç denetimi ile iletişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af0b248d5e32b535c23cc17b48efdd551dad7a2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim
Üye işlevleri çağırmak için farklı yöntemler kullanın bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:  
  
-   Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` iletişim kutusu sınıfında oluşturun.  
  
-   Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesne (veya işaretçi) nesnesi oluşturmak için kullandığınız.  
  
-   Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi başvuru alınamıyor. Bu değer ile başka bir başvuru başlatmak veya başvuru adresi atamak bir `CTreeCtrl` işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

