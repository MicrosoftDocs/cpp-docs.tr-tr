---
title: İletişim Sınıfınızı Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: bacedc49fcdabdd5dc7fb0f392a66afd3baadd06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241771"
---
# <a name="creating-your-dialog-class"></a>İletişim Sınıfınızı Oluşturma

Programınızda her iletişim kutusu için iletişim kutusu kaynağı ile çalışmak için yeni bir iletişim kutusu sınıfı oluşturma.

[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md) yeni iletişim kutusu sınıfı oluşturma açıklanır. Sınıf Ekleme Sihirbazı'nı bir iletişim kutusu sınıfı oluşturduğunuzda, aşağıdaki öğeleri yazar. H ve. Belirttiğiniz CPP dosyaları:

İçinde. H dosyası:

- İletişim kutusu sınıfı için sınıf bildirimi. Sınıf türetilir [CDialog](../mfc/reference/cdialog-class.md).

İçinde. CPP dosyasına:

- Sınıfı için ileti eşlemesi.

- İletişim kutusu için standart bir oluşturucu.

- Geçersiz kılma [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) üye işlevi. Bu işlev düzenleyin. Daha sonra açıklandığı iletişim kutusu veri değişimi ve doğrulaması özellikleri için kullanılan [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazları ile İletişim Kutusu Sınıfı Oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
