---
title: MFC’de İletişim Kutularıyla çalışma
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: d365be21ef19a6779df649e9368fdc0cda4851df
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621441"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>MFC’de İletişim Kutularıyla çalışma

Bir iletişim kutusunun yaşam döngüsü boyunca Kullanıcı iletişim kutusunu çağırır, genellikle iletişim kutusu nesnesini oluşturan ve Başlatan bir komut işleyici içinde Kullanıcı iletişim kutusuyla etkileşime girer ve iletişim kutusu kapanır.

Kalıcı iletişim kutuları için, işleyiciniz, iletişim kutusu kapandığında kullanıcının girdiği verileri toplar. İletişim kutusu, iletişim kutusu penceresi kapatıldıktan sonra mevcut olduğundan, verileri ayıklamak için iletişim kutusu sınıfınızın üye değişkenlerini kullanmanız yeterlidir.

Kalıcı olmayan iletişim kutuları için, iletişim kutusu hala görünmezken iletişim kutusu nesnesinden verileri genellikle ayıklayabiliriz. Bir noktada iletişim kutusu nesnesi yok edilir; Bu gerçekleştiğinde kodunuza bağlı olur.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [İletişim kutuları oluşturma ve görüntüleme](creating-and-displaying-dialog-boxes.md)

- [Kalıcı iletişim kutuları oluşturma](creating-modal-dialog-boxes.md)

- [Kalıcı olmayan iletişim kutuları oluşturma](creating-modeless-dialog-boxes.md)

- [Bellekte bir iletişim kutusu şablonu kullanma](using-a-dialog-template-in-memory.md)

- [İletişim kutusunun arka plan rengini ayarlama](setting-the-dialog-boxs-background-color.md)

- [İletişim kutusunu başlatma](initializing-the-dialog-box.md)

- [İletişim kutusunda Windows iletilerini işleme](handling-windows-messages-in-your-dialog-box.md)

- [İletişim nesnesinden veriyi geri alma](retrieving-data-from-the-dialog-object.md)

- [İletişim kutusu kapatılıyor](closing-the-dialog-box.md)

- [İletişim kutusunu yok etme](destroying-the-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV)](dialog-data-exchange-and-validation.md)

- [Özellik sayfası iletişim kutuları](property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](dialog-boxes.md)
