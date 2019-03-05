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
ms.openlocfilehash: e0b7ff31576b345ac2911e62a6e10469845eecba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302331"
---
# <a name="creating-and-displaying-dialog-boxes"></a>İletişim Kutuları Oluşturma ve Görüntüleme

İletişim nesnesi oluşturulurken iki aşamalı bir işlemdir. İlk olarak, iletişim nesnesi oluşturun ve ardından iletişim penceresi oluştur. Kalıcı ve kalıcı olmayan iletişim kutuları oluşturmak ve bunları görüntülemek için kullanılan işlem olarak biraz farklılık gösterir. Aşağıdaki tablo nasıl kalıcı ve kalıcı olmayan iletişim kutuları normalde oluşturulur ve görüntülenir listeler.

### <a name="dialog-creation"></a>İletişim kutusu oluşturma

|İletişim türü|Bu oluşturma|
|-----------------|----------------------|
|[Engelleyici olmayan](../mfc/creating-modeless-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağırın `Create` üye işlevi.|
|[Kalıcı](../mfc/creating-modal-dialog-boxes.md)|Oluşturmak `CDialog`, ardından çağırın `DoModal` üye işlevi.|

İsterseniz, iletişim kutusundan oluşturabilirsiniz bir [bellek içi iletişim şablonu](../mfc/using-a-dialog-template-in-memory.md) oluşturulan yerine bir iletişim şablon kaynağı. Gelişmiş bir konu, ancak budur.

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
