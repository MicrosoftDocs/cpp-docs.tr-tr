---
title: İletişim Kutusunu Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 07e4159eccde1fab89d4a5ffadee4e6d11fc20f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326852"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma

Kullanıcı düğmeleri, genellikle Tamam düğmesine veya İptal düğmesini seçtiğinde, kalıcı bir iletişim kutusu kapanır. Neden olan iletişim nesnesi göndermek Windows Tamam'ı veya İptal düğmesini seçerek bir **BN_CLICKED** düğmesi denetimi bildirim iletisi kimliği ya da kullanıcının **IDOK** veya **IDCANCEL**. `CDialog` Varsayılan için bu ileti işleyici işlevleri sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyicileri çağrı `EndDialog` iletişim penceresini kapatmak için üye işlevi. Ayrıca, çağırabilirsiniz `EndDialog` kendi kod. Daha fazla bilgi için [EndDialog](../mfc/reference/cdialog-class.md#enddialog) sınıfının üye işlevinde `CDialog` içinde *MFC başvurusu*.

Kapatma ve modsuz iletişim kutusu silme için düzenlemek için geçersiz kılma `PostNcDestroy` ve çağırma **Sil** işlecinin **bu** işaretçi. [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md) ne olacağını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
