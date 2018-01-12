---
title: "Ağaç denetim öğesi konumu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db47e27ad0b556e08f51685bf84b6bd998722239
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-position"></a>Ağaç Denetim Öğesi Konumu
Ağaç denetim öğesi eklendiğinde, bir öğenin ilk konumu ayarlanır ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kullanarak `InsertItem` üye işlevi. Üye işlev çağrısı üst öğesi tanıtıcısı ve sonra yeni öğe eklenecek madde tanıtıcısı belirtir. İkinci işleyici verilen üst ya da bir alt öğesi tanımlamanız gerekir veya bu değerlerden birini: `TVI_FIRST`, `TVI_LAST`, veya `TVI_SORT`.  
  
 Zaman `TVI_FIRST` veya `TVI_LAST` belirtilirse, belirtilen üst öğenin alt öğeleri listesi başında veya sonunda yeni öğe ağaç denetimi yerleştirir. Zaman `TVI_SORT` belirtilirse, ağaç denetimi yeni öğe öğe etiketlerini metne göre alfabetik sırada alt öğe listesi ekler.  
  
 Çağırarak bir üst öğenin alt öğeleri listesi alfabetik koyabilirsiniz [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) üye işlevi. Bu işlev tüm düzeylerini verilen üst öğesinden azalan alt öğeleri de alfabetik sıraya göre sıralı olup olmadığını belirten bir parametre içerir.  
  
 [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) üye işlevi alt öğeleri tanımladığınız ölçütlere göre sıralamak sağlar. Bu işlev çağırdığınızda, iki alt öğeleri göreli sıralamasını kampanyanızın olması gerektiğinde, ağaç denetimi çağırabilirsiniz bir uygulama tanımlı geri çağırma işlevi belirtin. Geri çağırma işlevi iki 32 bit uygulama tanımlı değerler karşılaştırılan öğeleri için ve çağrılırken belirttiğiniz üçüncü bir 32-bit değeri alan `SortChildrenCB`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

