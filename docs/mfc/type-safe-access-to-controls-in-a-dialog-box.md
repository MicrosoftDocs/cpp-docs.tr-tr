---
title: Bir iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a876be701b680de0559f123aaaaa68d4c006e41a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381377"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim
Bir iletişim kutusu denetimleri MFC denetim sınıfları arabirimleri gibi kullanabilir `CListBox` ve `CEdit`. Denetim nesnesi oluşturabilir ve iletişim denetimine ekleyebilirsiniz. Ardından denetim üzerinde çalışmaları için üye işlevlerini çağırarak kendi sınıf arabirimi üzerinden denetime erişebilirsiniz. Burada açıklanan yöntemler denetime tür kullanımı uyumlu erişiminizi sağlamak için tasarlanmıştır. Bu özellikle düzenleme kutuları ve liste kutuları gibi denetimler için kullanışlıdır.  
  
 Bir iletişim kutusu denetiminde bir C++ denetim üye değişkeni arasında bir bağlantı yapmak için iki yaklaşım vardır bir `CDialog`-türetilmiş sınıf:  
  
-   [Kod sihirbazları](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Kod sihirbazları ile](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim Kutuları](../mfc/dialog-boxes.md)

