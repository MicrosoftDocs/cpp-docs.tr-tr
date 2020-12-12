---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutusunu yok etme'
title: İletişim Kutusunu Yok Etme
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
ms.openlocfilehash: f46c86e5f3e869f321b8306470e5821658ceafcb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327849"
---
# <a name="destroying-the-dialog-box"></a>İletişim Kutusunu Yok Etme

Kalıcı iletişim kutuları normalde yığın çerçevesinde oluşturulur ve bunları oluşturan işlev sona erdiğinde yok edilir. Nesne kapsam dışına geçtiğinde iletişim kutusu nesnesinin yıkıcısı çağrılır.

Kalıcı olmayan iletişim kutuları normalde bir üst görünüm veya çerçeve penceresi — uygulamanın ana çerçeve penceresi veya bir belge çerçevesi penceresi tarafından oluşturulur ve aittir. Varsayılan [OnClose](reference/cwnd-class.md#onclose) işleyicisi, iletişim kutusu penceresini yok etmek Için [DestroyWindow](reference/cwnd-class.md#destroywindow)'u çağırır. İletişim kutusu tek başına temsil ederseniz, bu veya başka bir özel sahiplik semantiğine işaretçi olmadan, C++ iletişim nesnesini yok etmek için [PostNcDestroy](reference/cwnd-class.md#postncdestroy) 'u geçersiz kılmanız gerekir. Ayrıca [OnCancel](reference/cdialog-class.md#oncancel) ve içinden çağrısını geçersiz kılmanız gerekir `DestroyWindow` . Aksi takdirde, iletişim kutusunun sahibi artık gerekli olmadığında C++ nesnesini yok eder.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
