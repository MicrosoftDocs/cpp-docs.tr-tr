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
ms.openlocfilehash: c800c204fd09057585064397d459f92c9ded272d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341751"
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma
Kullanıcı düğmeleri, genellikle Tamam düğmesine veya iptal düğmesi seçtiğinde modal bir iletişim kutusu kapanır. Neden olan Windows iletişim nesnesi göndermek Tamam'ı veya İptal düğmesini seçerek bir **BN_CLICKED** düğme denetim bildirimi iletisiyle kullanıcının kimliği, ya da **IDOK** veya **IDCANCEL**. `CDialog` Varsayılan bu iletiler için işleyici işlevleri sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyicileri çağrısı `EndDialog` üye işlevi iletişim penceresini kapatın. Ayrıca, çağırabilirsiniz `EndDialog` kendi kodundan. Daha fazla bilgi için bkz: [EndDialog](../mfc/reference/cdialog-class.md#enddialog) sınıfının üye işlevini `CDialog` içinde *MFC başvurusu*.  
  
 Kapatma ve kalıcı olmayan iletişim kutusu silmek için düzenlemek için geçersiz kılma `PostNcDestroy` ve çağırma **silmek** işlecinin **bu** işaretçi. [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md) ne olacağını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

