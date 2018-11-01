---
title: İletişim Kutuları Oluşturma ve Görüntüleme
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 778ee0cbb154c65b0cc74a207a175354c2e2a90b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431089"
---
# <a name="creating-and-displaying-dialog-boxes"></a>İletişim Kutuları Oluşturma ve Görüntüleme

İletişim nesnesi oluşturulurken iki aşamalı bir işlemdir. İlk olarak, iletişim nesnesi oluşturun ve ardından iletişim penceresi oluştur. Kalıcı ve kalıcı olmayan iletişim kutuları oluşturmak ve bunları görüntülemek için kullanılan işlem olarak biraz farklılık gösterir. Aşağıdaki tablo nasıl kalıcı ve kalıcı olmayan iletişim kutuları normalde oluşturulur ve görüntülenir listeler.

### <a name="dialog-creation"></a>İletişim kutusu oluşturma

|İletişim türü|Bu oluşturma|
|-----------------|----------------------|
|[Engelleyici olmayan](../mfc/creating-modeless-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağırın `Create` üye işlevi.|
|[Kalıcı](../mfc/creating-modal-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağırın `DoModal` üye işlevi.|

İsterseniz, iletişim kutusundan oluşturabilirsiniz bir [bellek içi iletişim şablonu](../mfc/using-a-dialog-template-in-memory.md) oluşturulan yerine bir iletişim şablon kaynağı. Gelişmiş bir konu, ancak budur.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

