---
title: Iletişim kutusu kapatılıyor
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 48ea954552b3ea9aa7193a47fc2a66d731312d77
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685375"
---
# <a name="closing-the-dialog-box"></a>Iletişim kutusu kapatılıyor

Kullanıcı düğmelerinden birini seçtiğinde kalıcı iletişim kutusu kapanır, genellikle Tamam düğmesi veya Iptal düğmesi. Tamam veya Iptal düğmesi seçildiğinde, Windows 'un iletişim kutusu nesnesine bir **BN_CLICKED** Control-Notification iletisi gönderilmesi, **IDOK** veya **IDCANCEL**. `CDialog` şu iletiler için varsayılan işleyici işlevlerini sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyiciler, iletişim penceresini kapatmak için `EndDialog` üye işlevini çağırır. Ayrıca, kendi kodınızdan `EndDialog` ' yı çağırabilirsiniz. Daha fazla bilgi için *MFC başvurusunda*`CDialog` sınıfının [EndDialog](../mfc/reference/cdialog-class.md#enddialog) üye işlevine bakın.

Kalıcı olmayan bir iletişim kutusunu kapatmayı ve silmeyi düzenlemek için, `PostNcDestroy` ' ı geçersiz kılın ve **Bu** işaretçinin üzerinde **Delete** işlecini çağırın. [Iletişim kutusunun yok edilmesi,](../mfc/destroying-the-dialog-box.md) sonraki ne olduğunu açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
