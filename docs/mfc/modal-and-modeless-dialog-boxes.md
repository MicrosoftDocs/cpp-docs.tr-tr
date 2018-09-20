---
title: Kalıcı ve kalıcı olmayan iletişim kutuları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e355c3bcef9edb68e49903dafbf4719fe0aa925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417533"
---
# <a name="modal-and-modeless-dialog-boxes"></a>Kalıcı ve Kalıcı Olmayan İletişim Kutuları

Sınıf kullanabileceğiniz [CDialog](../mfc/reference/cdialog-class.md) iletişim kutularının iki tür yönetmek için:

- *Kalıcı iletişim kutuları*, programın devam etmeden önce yanıt vermek kullanıcı gerektirir

- *Kalıcı olmayan iletişim kutuları*, kullanmak istediğiniz zaman kullanılabilir ve ekran kalır, ancak diğer kullanıcı etkinlikleri izin

Kaynak düzenleme ve bir iletişim şablonunu oluşturmayla ilgili yordamlar kalıcı ve kalıcı olmayan iletişim kutuları için aynıdır.

Programınız için bir iletişim kutusu oluşturmak için aşağıdaki adımları gerektirir:

1. Kullanım [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) iletişim kutusu tasarlayıp iletişim şablon kaynağı oluşturun.

1. İletişim kutusu sınıfı oluşturma.

1. Connect [iletişim kaynağın denetimleri için ileti işleyicileri](../windows/adding-event-handlers-for-dialog-box-controls.md) iletişim kutusu sınıfı içinde.

1. Belirtmek için iletişim kutusunun denetimleri ile ilişkili veri üyeleri ekleme [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md) ve [iletişim kutusu veri doğrulama](../mfc/dialog-data-validation.md) denetimleri.

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

