---
title: "İletişim kutusunu kapatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4c311a8d09ac3e1329b495fc321028e9f674993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-the-dialog-box"></a>İletişim Kutusunu Kapatma
Kullanıcı düğmeleri, genellikle Tamam düğmesine veya iptal düğmesi seçtiğinde modal bir iletişim kutusu kapanır. Neden olan Windows iletişim nesnesi göndermek Tamam'ı veya İptal düğmesini seçerek bir **BN_CLICKED** düğme denetim bildirimi iletisiyle kullanıcının kimliği, ya da **IDOK** veya **IDCANCEL**. `CDialog`Varsayılan bu iletiler için işleyici işlevleri sağlar: `OnOK` ve `OnCancel`. Varsayılan işleyicileri çağrısı `EndDialog` üye işlevi iletişim penceresini kapatın. Ayrıca, çağırabilirsiniz `EndDialog` kendi kodundan. Daha fazla bilgi için bkz: [EndDialog](../mfc/reference/cdialog-class.md#enddialog) sınıfının üye işlevini `CDialog` içinde *MFC başvurusu*.  
  
 Kapatma ve kalıcı olmayan iletişim kutusu silmek için düzenlemek için geçersiz kılma `PostNcDestroy` ve çağırma **silmek** işlecinin **bu** işaretçi. [İletişim kutusunu yok etme](../mfc/destroying-the-dialog-box.md) ne olacağını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

