---
title: Kalıcı Olmayan İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7a6125e84438b0ef2ad541c26bda33051d483c8d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619637"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma

Kalıcı olmayan iletişim kutusu için, iletişim sınıfınız içinde kendi ortak oluşturucuyu sağlamanız gerekir. Kalıcı olmayan bir iletişim kutusu oluşturmak için, genel oluşturucuyu çağırın ve iletişim kutusu kaynağını yüklemek için iletişim kutusu nesnesinin üye [Oluştur](reference/cdialog-class.md#create) işlevini çağırın. Oluşturucuyu, Oluşturucu **çağrısı sırasında veya sonrasında çağırabilirsiniz.** İletişim kutusu kaynağının özelliği **WS_VISIBLE**varsa, iletişim kutusu hemen görünür. Aksi takdirde, [ShowWindow](reference/cwnd-class.md#showwindow) üye işlevini çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
