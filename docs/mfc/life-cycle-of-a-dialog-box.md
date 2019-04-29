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
ms.openlocfilehash: a3772a180e35a57c997446fcf2268d84bec2daa5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365350"
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

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)
