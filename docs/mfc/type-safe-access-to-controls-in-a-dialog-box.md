---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutusundaki denetimlere erişim Type-Safe'
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
ms.openlocfilehash: 1c8b3482ee723e95142c9cd19fa6068f32f4ebd0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263835"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim

İletişim kutusundaki denetimler, ve gibi MFC denetim sınıflarının arabirimlerini kullanabilir `CListBox` `CEdit` . Denetim nesnesi oluşturabilir ve iletişim denetimine ekleyebilirsiniz. Ardından denetim üzerinde çalışmaları için üye işlevlerini çağırarak kendi sınıf arabirimi üzerinden denetime erişebilirsiniz. Burada açıklanan yöntemler denetime tür kullanımı uyumlu erişiminizi sağlamak için tasarlanmıştır. Bu özellikle düzenleme kutuları ve liste kutuları gibi denetimler için kullanışlıdır.

İletişim kutusu içindeki bir denetim ile türetilmiş bir sınıftaki C++ denetim üyesi değişkeni arasında bağlantı yapmak için iki yaklaşım vardır `CDialog` :

- [Kod sihirbazları olmadan](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [Kod sihirbazları ile](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)
