---
title: Kalıcı İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed7cc94982a46e542a5174d4d46b8013cc84ffa4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622976"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma

Kalıcı bir iletişim kutusu oluşturmak için [CDialog](reference/cdialog-class.md)'da belirtilen iki ortak oluşturucudan birini çağırın. Ardından, iletişim kutusunu göstermek ve Kullanıcı Tamam ' ı seçinceye veya Iptal edilene kadar etkileşimi yönetmek için iletişim kutusu nesnesinin [DoModal](reference/cdialog-class.md#domodal) üye işlevini çağırın. Bu yönetim, `DoModal` iletişim kutusunu kalıcı hale getirir. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağını yükler.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
