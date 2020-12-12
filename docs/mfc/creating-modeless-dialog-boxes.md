---
description: 'Daha fazla bilgi edinin: kalıcı olmayan Iletişim kutuları oluşturma'
title: Kalıcı Olmayan İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: c754391a0f1ab2713f3ce01b5d30ccc33be4aaa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309790"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma

Kalıcı olmayan iletişim kutusu için, iletişim sınıfınız içinde kendi ortak oluşturucuyu sağlamanız gerekir. Kalıcı olmayan bir iletişim kutusu oluşturmak için, genel oluşturucuyu çağırın ve iletişim kutusu kaynağını yüklemek için iletişim kutusu nesnesinin üye [Oluştur](reference/cdialog-class.md#create) işlevini çağırın. Oluşturucuyu, Oluşturucu **çağrısı sırasında veya sonrasında çağırabilirsiniz.** İletişim kutusu kaynağının özelliği **WS_VISIBLE** varsa, iletişim kutusu hemen görünür. Aksi takdirde, [ShowWindow](reference/cwnd-class.md#showwindow) üye işlevini çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
