---
description: 'Hakkında daha fazla bilgi edinin: CWnd nesneleri ne zaman başlatılıyor'
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
ms.openlocfilehash: 89d40b826507574fddd41364ac6cecc526663519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142772"
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd Nesneleri Ne Zaman Başlatılır?

Kendi alt pencerelerini oluşturamaz veya türetilmiş bir nesne oluşturucusunda herhangi bir Windows API işlevini çağırabilirsiniz `CWnd` . Bunun nedeni `HWND` `CWnd` nesne için henüz oluşturulmamıştır. Alt pencereler ekleme gibi Windows 'a özgü çoğu başlatmanın bir [OnCreate](../mfc/reference/cwnd-class.md#oncreate) ileti işleyicisinde yapılması gerekir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Belge/görünüm oluşturma](../mfc/document-view-creation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)
