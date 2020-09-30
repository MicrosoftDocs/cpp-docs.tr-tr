---
title: Kalıcı ve Kalıcı Olmayan İletişim Kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: d3497a19ab14dcc9f14dc0419eb65ea033135b6e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508853"
---
# <a name="modal-and-modeless-dialog-boxes"></a>Kalıcı ve Kalıcı Olmayan İletişim Kutuları

İki tür iletişim kutusunu yönetmek için class [CDialog](reference/cdialog-class.md) kullanabilirsiniz:

- Kullanıcının programa devam etmeden önce yanıt vermesini gerektiren *kalıcı iletişim kutuları*

- Ekranda yer alan ve diğer Kullanıcı etkinliklerine izin veren, ekranda geçen ve *kalıcı olmayan iletişim kutuları*

İletişim kutusu şablonu oluşturmak için kaynak düzenlemesi ve yordamları, kalıcı ve kalıcı olmayan iletişim kutuları için aynıdır.

Programınız için bir iletişim kutusu oluşturmak aşağıdaki adımları gerektirir:

1. İletişim kutusunu tasarlamak ve iletişim kutusu-şablon kaynağını oluşturmak için [iletişim kutusu düzenleyicisini](../windows/dialog-editor.md) kullanın.

1. İletişim kutusu sınıfı oluşturun.

1. İletişim kutusu sınıfının denetimlerini iletişim kutusunda [ileti işleyicilerine](../windows/adding-editing-or-deleting-controls.md) bağlayın.

1. İletişim kutusu denetimleriyle ilişkili veri üyeleri ekleyin ve denetimler için [iletişim kutusu veri değişimi](dialog-data-exchange.md) ve iletişim kutusu [verileri doğrulamaları](dialog-data-validation.md) belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
