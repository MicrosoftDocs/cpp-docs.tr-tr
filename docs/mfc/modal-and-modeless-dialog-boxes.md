---
title: "Kalıcı ve kalıcı olmayan iletişim kutuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 450a7576556cb1ecec394339c1e2d63264c5340b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="modal-and-modeless-dialog-boxes"></a>Kalıcı ve Kalıcı Olmayan İletişim Kutuları
Sınıf kullanabilirsiniz [CDialog](../mfc/reference/cdialog-class.md) iletişim kutuları iki tür yönetmek için:  
  
-   *Kalıcı iletişim kutuları*, program devam etmeden önce yanıt kullanıcının gerektiren  
  
-   *Kalıcı olmayan iletişim kutuları*, hangi ekran ve herhangi bir zamanda kullanmak için kullanılabilir kalır ancak diğer kullanıcı etkinlikleri izin ver  
  
 Kaynak düzenleme ve iletişim şablonu oluşturmayla ilgili yordamlar kalıcı ve kalıcı olmayan iletişim kutuları için aynıdır.  
  
 Bir iletişim kutusu programınızın oluşturmak için aşağıdaki adımları gerekir:  
  
1.  Kullanım [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) tasarımı iletişim kutusu ve iletişim şablonu kaynağı oluşturun.  
  
2.  İletişim kutusu sınıfı oluşturun.  
  
3.  Bağlantı [ileti işleyicileri iletişim kaynağın denetimlere](../windows/adding-event-handlers-for-dialog-box-controls.md) iletişim sınıfında.  
  
4.  Belirtmek için iletişim kutusunun denetimleri ile ilişkili veri üye eklemek [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md) ve [iletişim kutusu veri doğrulama](../mfc/dialog-data-validation.md) denetimleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

