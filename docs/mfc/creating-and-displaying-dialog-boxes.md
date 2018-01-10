---
title: "İletişim kutuları oluşturma ve görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d436301a979dbba2bc4a922f8427f355a398f654
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-displaying-dialog-boxes"></a>İletişim Kutuları Oluşturma ve Görüntüleme
İletişim nesnesi oluşturma iki aşamalı bir işlemdir. İlk olarak, iletişim nesnesi oluşturun, sonra iletişim penceresi oluşturun. Kalıcı ve kalıcı olmayan iletişim kutuları oluşturmak ve bunları görüntülemek için kullanılan işleminde biraz farklılık gösterir. Aşağıdaki tabloda nasıl kalıcı ve kalıcı olmayan iletişim kutuları normal olarak oluşturulur ve görüntülenir listeler.  
  
### <a name="dialog-creation"></a>İletişim kutusu oluşturma  
  
|İletişim türü|Bu oluşturma|  
|-----------------|----------------------|  
|[Engelleyici olmayan](../mfc/creating-modeless-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağıran **oluşturma** üye işlevi.|  
|[Kalıcı](../mfc/creating-modal-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağıran `DoModal` üye işlevi.|  
  
 İsterseniz, iletişim kutusundan oluşturabilirsiniz bir [bellek içi iletişim şablonu](../mfc/using-a-dialog-template-in-memory.md) oluşturulan yerine bir iletişim kutusu şablon kaynağı. Bu ileri düzeyde, ancak bir konudur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

