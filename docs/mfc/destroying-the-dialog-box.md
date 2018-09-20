---
title: İletişim kutusunu yok etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 863b70f3bf4e9828d69024b838dce43abbba26be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425918"
---
# <a name="destroying-the-dialog-box"></a>İletişim Kutusunu Yok Etme

Kalıcı iletişim kutuları normalde yığın çerçevesini oluşturulur ve bunları oluşturduğunuz işlev sona erdiğinde yok. Nesne kapsam dışına çıktığında iletişim nesnenin yok Edicisi çağrılır.

Kalıcı olmayan iletişim kutuları normalde oluşturulan ve bir üst görünüm veya çerçeve penceresi tarafından sahip olunan — uygulamanın ana çerçeve penceresi veya belge çerçeve penceresi. Varsayılan [OnClose](../mfc/reference/cwnd-class.md#onclose) işleyicisi çağrılarını [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), iletişim kutusu penceresini yok eder. İletişim kutusu tek başına veya diğer özel sahipliği semantikler hiçbir işaretçilerle anlamına gelir, geçersiz kılmalıdır [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) C++ iletişim nesneyi yok etmek için. Geçersiz kılmalıdır [OnCancel](../mfc/reference/cdialog-class.md#oncancel) ve çağrı `DestroyWindow` gelen içindeki. Aksi durumda, artık gerekli olmadığında iletişim kutusunun sahibi C++ nesne yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

