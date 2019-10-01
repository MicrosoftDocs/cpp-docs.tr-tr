---
title: MFC 'de Iletişim kutularıyla çalışma
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: ad15250cf9a8dd663072cf9423263260bbb40a0e
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685732"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>MFC 'de Iletişim kutularıyla çalışma

Bir iletişim kutusunun yaşam döngüsü boyunca Kullanıcı iletişim kutusunu çağırır, genellikle iletişim kutusu nesnesini oluşturan ve Başlatan bir komut işleyici içinde Kullanıcı iletişim kutusuyla etkileşime girer ve iletişim kutusu kapanır.

Kalıcı iletişim kutuları için, işleyiciniz, iletişim kutusu kapandığında kullanıcının girdiği verileri toplar. İletişim kutusu, iletişim kutusu penceresi kapatıldıktan sonra mevcut olduğundan, verileri ayıklamak için iletişim kutusu sınıfınızın üye değişkenlerini kullanmanız yeterlidir.

Kalıcı olmayan iletişim kutuları için, iletişim kutusu hala görünmezken iletişim kutusu nesnesinden verileri genellikle ayıklayabiliriz. Bir noktada iletişim kutusu nesnesi yok edilir; Bu gerçekleştiğinde kodunuza bağlı olur.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [İletişim kutuları oluşturma ve görüntüleme](../mfc/creating-and-displaying-dialog-boxes.md)

- [Kalıcı iletişim kutuları oluşturma](../mfc/creating-modal-dialog-boxes.md)

- [Kalıcı olmayan iletişim kutuları oluşturma](../mfc/creating-modeless-dialog-boxes.md)

- [Bellekte bir iletişim kutusu şablonu kullanma](../mfc/using-a-dialog-template-in-memory.md)

- [İletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md)

- [İletişim kutusu başlatılıyor](../mfc/initializing-the-dialog-box.md)

- [İletişim kutusunda Windows iletilerini işleme](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [İletişim nesnesinden verileri alma](../mfc/retrieving-data-from-the-dialog-object.md)

- [İletişim kutusu kapatılıyor](../mfc/closing-the-dialog-box.md)

- [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [Özellik sayfası iletişim kutuları](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)
