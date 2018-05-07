---
title: İletişim kutusunun yaşam döngüsü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: faf204f05c03e742e0f491fb3991b56d3405ebc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="life-cycle-of-a-dialog-box"></a>Bir İletişim Kutusunun Yaşam Döngüsü
Bir iletişim kutusunun yaşam döngüsü sırasında kullanıcı iletişim kutusunu çağırır, genellikle oluşturan ve iletişim nesnesini başlatır bir komut işleyici içinde kullanıcı iletişim kutusu ile etkileşim kurar ve iletişim kutusunu kapatır.  
  
 Kalıcı iletişim kutuları için herhangi bir veri iletişim kutusunu kapatır sonra girilen kullanıcı işleyicinizi toplar. İletişim kutusu penceresinin kapattıktan sonra iletişim nesnesi mevcut olmadığından, veri ayıklamak için basitçe iletişim sınıfınızı üye değişkenleri kullanabilirsiniz.  
  
 İletişim kutusu görüntülenmeye olsa kalıcı olmayan iletişim kutuları için genellikle veri iletişim nesnesinden extract. Belirli bir noktada iletişim nesnesi yok; Bu durumda, koduna bağlıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [İletişim kutuları oluşturma ve görüntüleme](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Kalıcı iletişim kutuları oluşturma](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Kalıcı olmayan iletişim kutuları oluşturma](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [Bellekteki bir iletişim şablonunu kullanma](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [İletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md)  
  
-   [İletişim kutusunu başlatma](../mfc/initializing-the-dialog-box.md)  
  
-   [İletişim kutunuzda Windows iletilerini işleme](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [İletişim nesnesinden veriyi geri alma](../mfc/retrieving-data-from-the-dialog-object.md)  
  
-   [İletişim kutusunu kapatma](../mfc/closing-the-dialog-box.md)  
  
-   [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md)  
  
-   [İletişim kutusu veri değişimi (DDX) ve doğrulama (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Özellik sayfası iletişim kutuları](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim Kutuları](../mfc/dialog-boxes.md)

