---
title: Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
ms.openlocfilehash: 9b8e5aef61d1a7c7277f2a6bd37b81bd156bb837
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181624"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim

Bir iletişim kutusu denetimleri gibi MFC denetim sınıflarının arabirimlerini kullanabilir `CListBox` ve `CEdit`. Denetim nesnesi oluşturabilir ve iletişim denetimine ekleyebilirsiniz. Ardından denetim üzerinde çalışmaları için üye işlevlerini çağırarak kendi sınıf arabirimi üzerinden denetime erişebilirsiniz. Burada açıklanan yöntemler denetime tür kullanımı uyumlu erişiminizi sağlamak için tasarlanmıştır. Bu özellikle düzenleme kutuları ve liste kutuları gibi denetimler için kullanışlıdır.

İletişim kutusunda bir denetimi ve bir C++ denetim üye değişkeni arasında bağlantı yapmak için iki yaklaşım vardır bir `CDialog`-türetilmiş sınıf:

- [Kod sihirbazları](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [Kod sihirbazlarıyla](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)
