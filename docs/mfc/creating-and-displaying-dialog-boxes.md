---
title: İletişim kutuları oluşturma ve görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fcac345a572f8b33d76692d6852e2dc28698367
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342468"
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

