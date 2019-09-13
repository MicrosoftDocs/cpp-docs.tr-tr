---
title: İletişim Sınıfınızı Oluşturma
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 424d18196063456245e2a4841b42e6e447bded17
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907322"
---
# <a name="creating-your-dialog-class"></a>İletişim Sınıfınızı Oluşturma

Programınızdaki her iletişim kutusu için, iletişim kaynağı ile çalışmak üzere yeni bir iletişim kutusu sınıfı oluşturun.

[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md) , yeni bir iletişim kutusu sınıfının nasıl oluşturulacağını açıklar. [Sınıf sihirbazıyla](reference/mfc-class-wizard.md)bir iletişim kutusu sınıfı oluşturduğunuzda, belirttiğiniz. h ve. cpp dosyalarına aşağıdaki öğeleri Yazar:

. H dosyasında:

- İletişim kutusu sınıfı için bir sınıf bildirimi. Sınıf [CDialog](../mfc/reference/cdialog-class.md)'tan türetilir.

. Cpp dosyasında:

- Sınıf için bir ileti eşlemi.

- İletişim kutusu için standart Oluşturucu.

- [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) üye işlevinin bir geçersiz kılması. Bu işlevi düzenleyin. İletişim kutusu [veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha sonra açıklandığı gibi iletişim kutusu veri değişimi ve doğrulama özellikleri için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazları ile İletişim Kutusu Sınıfı Oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
