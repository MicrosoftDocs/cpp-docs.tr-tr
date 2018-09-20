---
title: İletişim kutusunu kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9ad4b8af63b68912c232767bf1fd14070fda261
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409057"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma

Kullanıcı düğmeleri, genellikle Tamam düğmesine veya İptal düğmesini seçtiğinde, kalıcı bir iletişim kutusu kapanır. Neden olan iletişim nesnesi göndermek Windows Tamam'ı veya İptal düğmesini seçerek bir **BN_CLICKED** düğmesi denetimi bildirim iletisi kimliği ya da kullanıcının **IDOK** veya **IDCANCEL**. `CDialog` Varsayılan için bu ileti işleyici işlevleri sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyicileri çağrı `EndDialog` iletişim penceresini kapatmak için üye işlevi. Ayrıca, çağırabilirsiniz `EndDialog` kendi kod. Daha fazla bilgi için [EndDialog](../mfc/reference/cdialog-class.md#enddialog) sınıfının üye işlevinde `CDialog` içinde *MFC başvurusu*.

Kapatma ve modsuz iletişim kutusu silme için düzenlemek için geçersiz kılma `PostNcDestroy` ve çağırma **Sil** işlecinin **bu** işaretçi. [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md) ne olacağını açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

