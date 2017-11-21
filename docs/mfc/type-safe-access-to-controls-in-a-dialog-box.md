---
title: "Bir iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0eab819ab1e0fcb9d0b710c430c30e5332bdf94b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim
Bir iletişim kutusu denetimleri MFC denetim sınıfları arabirimleri gibi kullanabilir `CListBox` ve `CEdit`. Denetim nesnesi oluşturabilir ve iletişim denetimine ekleyebilirsiniz. Ardından denetim üzerinde çalışmaları için üye işlevlerini çağırarak kendi sınıf arabirimi üzerinden denetime erişebilirsiniz. Burada açıklanan yöntemler denetime tür kullanımı uyumlu erişiminizi sağlamak için tasarlanmıştır. Bu özellikle düzenleme kutuları ve liste kutuları gibi denetimler için kullanışlıdır.  
  
 Bir iletişim kutusu denetiminde bir C++ denetim üye değişkeni arasında bir bağlantı yapmak için iki yaklaşım vardır bir `CDialog`-türetilmiş sınıf:  
  
-   [Kod sihirbazları](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Kod sihirbazları ile](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)

