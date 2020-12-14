---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutuları oluşturma ve görüntüleme'
title: İletişim Kutuları Oluşturma ve Görüntüleme
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
ms.openlocfilehash: 9865e43392021cc7ba1349a73bffb8e47f4cca9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309835"
---
# <a name="creating-and-displaying-dialog-boxes"></a>İletişim Kutuları Oluşturma ve Görüntüleme

İletişim kutusu nesnesi oluşturma iki aşamalı bir işlemdir. İlk olarak, iletişim kutusunu oluşturun ve ardından iletişim kutusu penceresini oluşturun. Kalıcı ve kalıcı olmayan iletişim kutuları, bunları oluşturmak ve göstermek için kullanılan işlemde biraz farklılık gösterir. Aşağıdaki tabloda, kalıcı ve kalıcı olmayan iletişim kutularının normal şekilde oluşturulması ve gösterilmesi listelenmektedir.

### <a name="dialog-creation"></a>İletişim kutusu oluşturma

|İletişim kutusu türü|Nasıl oluşturulur?|
|-----------------|----------------------|
|[Suz](creating-modeless-dialog-boxes.md)|`CDialog`Sonra üye işlevini oluşturun ve çağırın `Create` .|
|[Modal](creating-modal-dialog-boxes.md)|`CDialog`Sonra üye işlevini oluşturun ve çağırın `DoModal` .|

İsterseniz, iletişim kutusunu bir iletişim kutusu şablonu kaynağından değil, oluşturduğunuz [bellek içi bir iletişim şablonundan](using-a-dialog-template-in-memory.md) oluşturabilirsiniz. Ancak bu gelişmiş bir konudur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
