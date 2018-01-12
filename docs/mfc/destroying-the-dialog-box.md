---
title: "İletişim kutusunu yok etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b1b6c94c4c7efe3bc3300d6c8c5c34fbe890fb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-dialog-box"></a>İletişim Kutusunu Yok Etme
Kalıcı iletişim kutuları normalde yığın çerçevesi oluşturulur ve onları oluşturan işlevi sona erdiğinde yok. Nesne kapsam dışına çıktığında iletişim nesnenin yıkıcı adı verilir.  
  
 Kalıcı olmayan iletişim kutuları normal olarak oluşturulan ve bir ana görünüm veya çerçeve pencere tarafından sahip olunan — uygulamanın ana çerçeve penceresi veya belge çerçeve penceresi. Varsayılan [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), iletişim kutusunun penceresi yok eder. İletişim kutusu tek başına veya diğer özel sahipliği semantiği hiçbir işaretçilerle anlamına gelir, geçersiz kılmalısınız [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) C++ iletişim nesnesi yok etmek için. Ayrıca kılmalıdır [OnCancel](../mfc/reference/cdialog-class.md#oncancel) ve arama `DestroyWindow` gelen içindeki. Aksi durumda, artık gerekli olmadığında iletişim kutusu sahibi C++ nesne yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

