---
title: İletişim Kutusunu Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: a695a8e331eb8a4f22394deb65857bf93ecab41e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617202"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma

Kullanıcı düğmelerinden birini seçtiğinde kalıcı iletişim kutusu kapanır, genellikle Tamam düğmesi veya Iptal düğmesi. Tamam veya Iptal düğmesi seçildiğinde, Windows 'un iletişim kutusu nesnesine bir **BN_CLICKED** Control-Notification iletisi gönderilmesi, **IDOK** ya da **IDCANCEL**. `CDialog`Şu iletiler için varsayılan işleyici işlevlerini sağlar: `OnOK` ve `OnCancel` . Varsayılan işleyiciler, `EndDialog` iletişim penceresini kapatmak için üye işlevini çağırır. `EndDialog`Kendi kodınızdan da çağrı yapabilirsiniz. Daha fazla bilgi için MFC başvurusu içindeki sınıfın [EndDialog](reference/cdialog-class.md#enddialog) üye işlevine bakın `CDialog` . *MFC Reference*

Kalıcı olmayan bir iletişim kutusunu kapatmak ve silmek için düzenlemek üzere `PostNcDestroy` **Bu** işaretçi üzerinde **Delete** işlecini geçersiz kılın ve çağırın. [Iletişim kutusunun yok edilmesi,](destroying-the-dialog-box.md) sonraki ne olduğunu açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
