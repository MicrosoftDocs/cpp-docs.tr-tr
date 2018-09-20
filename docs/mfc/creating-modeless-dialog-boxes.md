---
title: Kalıcı olmayan iletişim kutuları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77b80f66f2956e71b90e4d939a0fb74aef28edb1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407042"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma

Kalıcı olmayan iletişim kutusu için kendi Genel oluşturucu iletişim sınıfınızı sağlamanız gerekir. Modsuz iletişim kutusu oluşturmak için ortak oluşturucusunu ve ardından iletişim nesnenin çağrı [Oluştur](../mfc/reference/cdialog-class.md#create) üye işlevi, iletişim kutusu kaynağı yüklenemedi. Çağırabilirsiniz **Oluştur** sırasında veya sonrasında oluşturucu çağrısı. İletişim kaynağını özelliği varsa **ws_vısıble**, hemen iletişim kutusu görüntülenir. Değil, çağırmalıdır, kendi [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

