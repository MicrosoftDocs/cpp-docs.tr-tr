---
title: "İletişim sınıfınızı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd80d55df3ae9adc4a586d1cc5387ee6d1f53282
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-your-dialog-class"></a>İletişim Sınıfınızı Oluşturma
Programınızdaki her iletişim kutusu için iletişim kutusu kaynağı ile çalışmak için yeni bir iletişim kutusu sınıfı oluşturun.  
  
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md) yeni iletişim kutusu sınıfı oluşturma açıklanmaktadır. Sınıf Ekleme Sihirbazı'nı iletişim kutusu sınıfı oluşturduğunuzda, aşağıdaki öğeleri yazar. H ve. Belirttiğiniz CPP dosyaları:  
  
 İçinde. H dosyası:  
  
-   İletişim kutusu sınıfı için sınıf bildirimi. Sınıfın türetildiği [CDialog](../mfc/reference/cdialog-class.md).  
  
 İçinde. CPP dosyası:  
  
-   Sınıfı için ileti eşlemesi.  
  
-   İletişim kutusu için standart bir oluşturucu.  
  
-   Geçersiz kılma [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) üye işlevi. Bu işlev düzenleyin. Daha sonra açıklandığı gibi iletişim kutusu veri değişimi ve doğrulaması özellikleri için kullanılan [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazları ile iletişim kutusu sınıfı oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

