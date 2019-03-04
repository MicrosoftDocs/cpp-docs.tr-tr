---
title: Kalıcı ve Kalıcı Olmayan İletişim Kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: c3a5263736324d7fe25066e8879d13b3a41768de
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268674"
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

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
