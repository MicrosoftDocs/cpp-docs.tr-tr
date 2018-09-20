---
title: CWnd nesneleri ne zaman | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6445190ab3da6ed84dbdd83cd0acab0ba98691f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388439"
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd Nesneleri Ne Zaman Başlatılır?

Kendi alt pencereler oluşturma veya oluşturucusunun içinde herhangi bir Windows API işlevleri çağırmak bir `CWnd`-türetilmiş bir nesneye. Bunun nedeni, `HWND` için `CWnd` nesne henüz oluşturulmadı. Alt öğe pencerelerini ekleme gibi en Windows özel başlatma yapılmalıdır bir [OnCreate](../mfc/reference/cwnd-class.md#oncreate) ileti işleyicisi.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Belge/görünüm oluşturma](../mfc/document-view-creation.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

