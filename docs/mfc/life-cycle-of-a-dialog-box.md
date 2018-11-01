---
title: Bir İletişim Kutusunun Yaşam Döngüsü
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: e92489499a3a5aaaf2fb97e8908cb30d5e168240
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577625"
---
# <a name="life-cycle-of-a-dialog-box"></a>Bir İletişim Kutusunun Yaşam Döngüsü

Bir iletişim kutusunun yaşam döngüsü sırasında kullanıcı iletişim kutusunu çağırır ve genellikle kullanıcı oluşturur ve başlatır iletişim nesnesi, bir komut işleyici içinde iletişim kutusu ile etkileşim iletişim kutusu kapanır.

Kalıcı iletişim kutuları için işleyicinizi iletişim kutusu kapatıldıktan sonra girilen kullanıcı verileri toplar. İletişim nesnesi, iletişim penceresini kapattıktan sonra mevcut olmadığından, verileri ayıklamak için yalnızca iletişim sınıfınızın bir üye değişkenleri kullanabilirsiniz.

İletişim kutusu hala görülebilir ancak kalıcı olmayan iletişim kutuları için genellikle veri iletişim nesnesinden ayıklar. Belirli bir noktada, iletişim nesnesi yok; Bu durumda, kodunuz üzerinde bağlıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [İletişim kutuları oluşturma ve görüntüleme](../mfc/creating-and-displaying-dialog-boxes.md)

- [Kalıcı iletişim kutuları oluşturma](../mfc/creating-modal-dialog-boxes.md)

- [Kalıcı olmayan iletişim kutuları oluşturma](../mfc/creating-modeless-dialog-boxes.md)

- [Bellekteki bir iletişim şablonunu kullanma](../mfc/using-a-dialog-template-in-memory.md)

- [İletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md)

- [İletişim kutusunu başlatma](../mfc/initializing-the-dialog-box.md)

- [İletişim kutunuzda Windows iletilerini işleme](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [İletişim nesnesinden veriyi geri alma](../mfc/retrieving-data-from-the-dialog-object.md)

- [İletişim kutusunu kapatma](../mfc/closing-the-dialog-box.md)

- [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulama (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Özellik sayfası iletişim kutuları](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)

