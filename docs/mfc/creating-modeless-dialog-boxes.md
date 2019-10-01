---
title: Kalıcı olmayan Iletişim kutuları oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
ms.openlocfilehash: 7da6d82257d1407dfcf4d6d3c15cdadbb8c0fa30
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685658"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı olmayan Iletişim kutuları oluşturma

Kalıcı olmayan iletişim kutusu için, iletişim sınıfınız içinde kendi ortak oluşturucuyu sağlamanız gerekir. Kalıcı olmayan bir iletişim kutusu oluşturmak için, genel oluşturucuyu çağırın ve iletişim kutusu kaynağını yüklemek için iletişim kutusu nesnesinin üye [Oluştur](../mfc/reference/cdialog-class.md#create) işlevini çağırın. Oluşturucuyu, Oluşturucu **çağrısı sırasında veya sonrasında çağırabilirsiniz.** İletişim kutusu kaynağı **WS_VISIBLE**özelliğine sahipse, iletişim kutusu hemen görünür. Aksi takdirde, [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) üye işlevini çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
