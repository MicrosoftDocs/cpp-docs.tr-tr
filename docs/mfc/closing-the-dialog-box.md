---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutusunu kapatma'
title: İletişim Kutusunu Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 4e60bdfb1ecb6968996d6c657f0c667ad2686a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338373"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma

Kullanıcı düğmelerinden birini seçtiğinde kalıcı iletişim kutusu kapanır, genellikle Tamam düğmesi veya Iptal düğmesi. Tamam veya Iptal düğmesi seçildiğinde, Windows 'un iletişim kutusu nesnesine bir **BN_CLICKED** Control-Notification iletisi gönderilmesi, **IDOK** ya da **IDCANCEL**. `CDialog` Şu iletiler için varsayılan işleyici işlevlerini sağlar: `OnOK` ve `OnCancel` . Varsayılan işleyiciler, `EndDialog` iletişim penceresini kapatmak için üye işlevini çağırır. `EndDialog`Kendi kodınızdan da çağrı yapabilirsiniz. Daha fazla bilgi için MFC başvurusu içindeki sınıfın [EndDialog](reference/cdialog-class.md#enddialog) üye işlevine bakın `CDialog` . 

Kalıcı olmayan bir iletişim kutusunu kapatmayı ve silmeyi düzenlemek için, `PostNcDestroy` **`delete`** işaretçi üzerinde işleci geçersiz kılın ve çağırın **`this`** . [Iletişim kutusunun yok edilmesi,](destroying-the-dialog-box.md) sonraki ne olduğunu açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
