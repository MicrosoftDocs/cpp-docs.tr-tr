---
title: Iletişim kutuları oluşturma ve görüntüleme
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 6d23e4d2c9249ce248eb8092963036f2ba5cacac
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685747"
---
# <a name="creating-and-displaying-dialog-boxes"></a>Iletişim kutuları oluşturma ve görüntüleme

İletişim kutusu nesnesi oluşturma iki aşamalı bir işlemdir. İlk olarak, iletişim kutusunu oluşturun ve ardından iletişim kutusu penceresini oluşturun. Kalıcı ve kalıcı olmayan iletişim kutuları, bunları oluşturmak ve göstermek için kullanılan işlemde biraz farklılık gösterir. Aşağıdaki tabloda, kalıcı ve kalıcı olmayan iletişim kutularının normal şekilde oluşturulması ve gösterilmesi listelenmektedir.

### <a name="dialog-creation"></a>İletişim kutusu oluşturma

|İletişim kutusu türü|Nasıl oluşturulur?|
|-----------------|----------------------|
|[Suz](../mfc/creating-modeless-dialog-boxes.md)|@No__t-0 oluşturun ve sonra `Create` üye işlevini çağırın.|
|[Modal](../mfc/creating-modal-dialog-boxes.md)|@No__t-0 oluşturun ve sonra `DoModal` üye işlevini çağırın.|

İsterseniz, iletişim kutusunu bir iletişim kutusu şablonu kaynağından değil, oluşturduğunuz [bellek içi bir iletişim şablonundan](../mfc/using-a-dialog-template-in-memory.md) oluşturabilirsiniz. Ancak bu gelişmiş bir konudur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
