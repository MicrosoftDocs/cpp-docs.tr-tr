---
title: Kalıcı ve kalıcı olmayan Iletişim kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: 886229a2b66968bf76129ecb1da838bd36e66215
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685179"
---
# <a name="modal-and-modeless-dialog-boxes"></a>Kalıcı ve kalıcı olmayan Iletişim kutuları

İki tür iletişim kutusunu yönetmek için class [CDialog](../mfc/reference/cdialog-class.md) kullanabilirsiniz:

- Kullanıcının programa devam etmeden önce yanıt vermesini gerektiren *kalıcı iletişim kutuları*

- Ekranda yer alan ve diğer Kullanıcı etkinliklerine izin veren, ekranda geçen ve *kalıcı olmayan iletişim kutuları*

İletişim kutusu şablonu oluşturmak için kaynak düzenlemesi ve yordamları, kalıcı ve kalıcı olmayan iletişim kutuları için aynıdır.

Programınız için bir iletişim kutusu oluşturmak aşağıdaki adımları gerektirir:

1. İletişim kutusunu tasarlamak ve iletişim kutusu-şablon kaynağını oluşturmak için [iletişim kutusu düzenleyicisini](../windows/dialog-editor.md) kullanın.

1. İletişim kutusu sınıfı oluşturun.

1. İletişim kutusu sınıfının denetimlerini iletişim kutusunda [ileti işleyicilerine](../windows/adding-event-handlers-for-dialog-box-controls.md) bağlayın.

1. İletişim kutusu denetimleriyle ilişkili veri üyeleri ekleyin ve denetimler için [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md) ve iletişim kutusu [verileri doğrulamaları](../mfc/dialog-data-validation.md) belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
