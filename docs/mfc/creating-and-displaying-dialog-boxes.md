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
ms.openlocfilehash: 437fb934e95ce527a77038d643e9cee86b6f1f2c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387750"
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

