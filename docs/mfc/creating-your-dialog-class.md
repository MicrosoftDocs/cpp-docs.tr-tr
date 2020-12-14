---
description: 'Hakkında daha fazla bilgi edinin: Iletişim sınıfınızı oluşturma'
title: İletişim Sınıfınızı Oluşturma
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: d135d6acaefbc73f435e48db8f72add7081fdac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309452"
---
# <a name="creating-your-dialog-class"></a>İletişim Sınıfınızı Oluşturma

Programınızdaki her iletişim kutusu için, iletişim kaynağı ile çalışmak üzere yeni bir iletişim kutusu sınıfı oluşturun.

[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md) , yeni bir iletişim kutusu sınıfının nasıl oluşturulacağını açıklar. [Sınıf sihirbazıyla](reference/mfc-class-wizard.md)bir iletişim kutusu sınıfı oluşturduğunuzda, belirttiğiniz. h ve. cpp dosyalarına aşağıdaki öğeleri Yazar:

. H dosyasında:

- İletişim kutusu sınıfı için bir sınıf bildirimi. Sınıf [CDialog](reference/cdialog-class.md)'tan türetilir.

. Cpp dosyasında:

- Sınıf için bir ileti eşlemi.

- İletişim kutusu için standart Oluşturucu.

- [DoDataExchange](reference/cwnd-class.md#dodataexchange) üye işlevinin bir geçersiz kılması. Bu işlevi düzenleyin. İletişim kutusu [veri değişimi ve doğrulaması](dialog-data-exchange-and-validation.md)konusunda daha sonra açıklandığı gibi iletişim kutusu veri değişimi ve doğrulama özellikleri için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Kod sihirbazları ile Iletişim kutusu sınıfı oluşturma](creating-a-dialog-class-with-code-wizards.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
