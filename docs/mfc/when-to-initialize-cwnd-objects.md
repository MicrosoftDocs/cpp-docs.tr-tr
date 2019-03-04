---
title: CWnd Nesneleri Ne Zaman Başlatılır?
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: aa396ade2e8ab4e1245e161423de7bd5bfafaaf8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291357"
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd Nesneleri Ne Zaman Başlatılır?

Kendi alt pencereler oluşturma veya oluşturucusunun içinde herhangi bir Windows API işlevleri çağırmak bir `CWnd`-türetilmiş bir nesneye. Bunun nedeni, `HWND` için `CWnd` nesne henüz oluşturulmadı. Alt öğe pencerelerini ekleme gibi en Windows özel başlatma yapılmalıdır bir [OnCreate](../mfc/reference/cwnd-class.md#oncreate) ileti işleyicisi.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Belge/görünüm oluşturma](../mfc/document-view-creation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)
