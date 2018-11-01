---
title: İletişim Kutusunu Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: fe57c5603f1b0e9ea0b6fb9e6ea8d80bec961f6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448119"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma

Kullanıcı düğmeleri, genellikle Tamam düğmesine veya İptal düğmesini seçtiğinde, kalıcı bir iletişim kutusu kapanır. Neden olan iletişim nesnesi göndermek Windows Tamam'ı veya İptal düğmesini seçerek bir **BN_CLICKED** düğmesi denetimi bildirim iletisi kimliği ya da kullanıcının **IDOK** veya **IDCANCEL**. `CDialog` Varsayılan için bu ileti işleyici işlevleri sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyicileri çağrı `EndDialog` iletişim penceresini kapatmak için üye işlevi. Ayrıca, çağırabilirsiniz `EndDialog` kendi kod. Daha fazla bilgi için [EndDialog](../mfc/reference/cdialog-class.md#enddialog) sınıfının üye işlevinde `CDialog` içinde *MFC başvurusu*.

Kapatma ve modsuz iletişim kutusu silme için düzenlemek için geçersiz kılma `PostNcDestroy` ve çağırma **Sil** işlecinin **bu** işaretçi. [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md) ne olacağını açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

