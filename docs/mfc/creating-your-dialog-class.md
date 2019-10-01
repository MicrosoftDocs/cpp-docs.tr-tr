---
title: Iletişim sınıfınızı oluşturma
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: b8275754d46e9d76933624af55335e956736319a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685654"
---
# <a name="creating-your-dialog-class"></a>Iletişim sınıfınızı oluşturma

Programınızdaki her iletişim kutusu için, iletişim kaynağı ile çalışmak üzere yeni bir iletişim kutusu sınıfı oluşturun.

[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md) , yeni bir iletişim kutusu sınıfının nasıl oluşturulacağını açıklar. [Sınıf sihirbazıyla](reference/mfc-class-wizard.md)bir iletişim kutusu sınıfı oluşturduğunuzda, belirttiğiniz. h ve. cpp dosyalarına aşağıdaki öğeleri Yazar:

. H dosyasında:

- İletişim kutusu sınıfı için bir sınıf bildirimi. Sınıf [CDialog](../mfc/reference/cdialog-class.md)'tan türetilir.

. Cpp dosyasında:

- Sınıf için bir ileti eşlemi.

- İletişim kutusu için standart Oluşturucu.

- [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) üye işlevinin bir geçersiz kılması. Bu işlevi düzenleyin. İletişim kutusu [veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha sonra açıklandığı gibi iletişim kutusu veri değişimi ve doğrulama özellikleri için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Kod sihirbazları ile Iletişim kutusu sınıfı oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
