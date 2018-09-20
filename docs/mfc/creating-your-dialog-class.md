---
title: İletişim sınıfınızı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9cec6ac40834e8cd3ccc9e0eadb18630ee507b92
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442051"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Kod Sihirbazları ile İletişim Kutusu Sınıfı Oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

