---
title: CTreeCtrl vs. CTreeView | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs: C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb0c1b7a7bf73ab70bbccca6f2a9ccc2ab385516
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl vs. CTreeView
Ağaç denetimleri kapsülleyen iki sınıf MFC sağlar: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md). Her sınıf farklı durumlarda yararlıdır.  
  
 Kullanım `CTreeCtrl` düz alt pencere denetim; gerektiğinde bir iletişim kutusunda örneği için. Özellikle kullanmak isteyebilirsiniz `CTreeCtrl` olacaksa diğer alt denetimleri penceresinde, olduğu gibi tipik iletişim kutusu.  
  
 Kullanım `CTreeView` belge/görünüm mimarisinin bir Görünüm penceresinde gibi davranacak şekilde Ağaç denetimi ve aynı zamanda ağaç denetimi istediğinizde. A `CTreeView` bir çerçeve penceresi veya Bölümlendirici pencere tüm istemci alanını kaplar. Bu, kendi üst penceresi boyutlandırılır ve menüleri, Hızlandırıcı tuşları ve araç çubuklarını komut iletileri işleyebilmesi için otomatik olarak boyutlandırılır. Ağaç denetimi ağaç görüntülemek gereken verileri içerdiğinden, ilgili belge nesnesi karmaşık olması gerekmez — bile kullanabileceğinizi [CDocument](../mfc/reference/cdocument-class.md) belge türü, belge şablonu olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

