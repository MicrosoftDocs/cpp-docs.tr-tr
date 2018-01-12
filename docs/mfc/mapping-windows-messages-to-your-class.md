---
title: "Windows iletilerini sınıfınıza eşleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4701b0ae9f71099febb1a239cea6285fb0a7b229
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-windows-messages-to-your-class"></a>Windows İletilerini Sınıfınıza Eşleme
Windows iletilerini işlemek için iletişim kutusunu gerekiyorsa, uygun işleyici işlevleri geçersiz kılar. Bunu yapmak için Özellikler penceresini kullanın [ileti eşlemesi](../mfc/reference/mapping-messages-to-functions.md) iletişim kutusu sınıflarına. Bu, her ileti için ileti eşleme girişi yazar ve sınıfı için ileti işleyicisi üye işlevleri ekler. İleti işleyicileri kod yazmak için Visual C++ kaynak kodu Düzenleyicisi'ni kullanın.  
  
 Üye işlevlerini geçersiz kılabilirsiniz [CDialog](../mfc/reference/cdialog-class.md) ve temel sınıflarının, özellikle [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)  
  
-   [Yaygın olarak geçersiz kılınan üye işlevleri](../mfc/commonly-overridden-member-functions.md)  
  
-   [Yaygın olarak eklenen üye işlevleri](../mfc/commonly-added-member-functions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

