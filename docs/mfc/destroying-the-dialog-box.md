---
title: Iletişim kutusunu yok etme
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: 8b407c6e832dde7a5865146e7cc12d1840d3234a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685840"
---
# <a name="destroying-the-dialog-box"></a>Iletişim kutusunu yok etme

Kalıcı iletişim kutuları normalde yığın çerçevesinde oluşturulur ve bunları oluşturan işlev sona erdiğinde yok edilir. Nesne kapsam dışına geçtiğinde iletişim kutusu nesnesinin yıkıcısı çağrılır.

Kalıcı olmayan iletişim kutuları normalde bir üst görünüm veya çerçeve penceresi — uygulamanın ana çerçeve penceresi veya bir belge çerçevesi penceresi tarafından oluşturulur ve aittir. Varsayılan [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi, iletişim kutusu penceresini yok etmek Için [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)'u çağırır. İletişim kutusu tek başına temsil ederseniz, bu veya başka bir özel sahiplik semantiğine işaretçi olmadan, C++ iletişim kutusu nesnesini yok etmek Için [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) 'u geçersiz kılmanız gerekir. Ayrıca [OnCancel](../mfc/reference/cdialog-class.md#oncancel) öğesini geçersiz kılmanız ve içinden `DestroyWindow` ' i çağırmanız gerekir. Aksi takdirde, iletişim kutusunun sahibi artık gerekli olmadığında C++ nesneyi yok eder.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
