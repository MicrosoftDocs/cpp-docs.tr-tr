---
title: Kalıcı Olmayan İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 71cca82e667ddbf5cfc4c2abb5880cd69c7fafae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388494"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma

Kalıcı olmayan iletişim kutusu için kendi Genel oluşturucu iletişim sınıfınızı sağlamanız gerekir. Modsuz iletişim kutusu oluşturmak için ortak oluşturucusunu ve ardından iletişim nesnenin çağrı [Oluştur](../mfc/reference/cdialog-class.md#create) üye işlevi, iletişim kutusu kaynağı yüklenemedi. Çağırabilirsiniz **Oluştur** sırasında veya sonrasında oluşturucu çağrısı. İletişim kaynağını özelliği varsa **ws_vısıble**, hemen iletişim kutusu görüntülenir. Değil, çağırmalıdır, kendi [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
