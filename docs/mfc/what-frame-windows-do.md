---
title: Çerçeve Pencerelerinin Görevi
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: ea35b98e5234c10a10143bad1d35fdd1b4510ced
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508777"
---
# <a name="what-frame-windows-do"></a>Çerçeve Pencerelerinin Görevi

Yalnızca bir görünüm çerçeveleme yanı sıra, çerçeve pencereleri uygulama ve onun görünümü ile çerçeve koordine içinde çeşitli görevleri sorumludur. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) devralınacak [CFrameWnd](../mfc/reference/cframewnd-class.md), sahip oldukları `CFrameWnd` özellikleri ve bunun yanı sıra, eklediğiniz yeni özellikler. Alt öğe pencerelerini örnekleri, görünümler, düğmeler ve liste kutuları ve araç çubuklarını ve durum çubukları iletişim kutusu çubukları dahil olmak üzere, Denetim çubukları gibi denetimler içerir.

Çerçeve penceresi, kendi alt pencereleri düzenini yönetmekten sorumludur. MFC çerçevesi içinde kendi istemci alanı içinde herhangi bir denetim çubukları, görünümler ve diğer alt pencereleri bir çerçeve penceresi yerleştirir.

Çerçeve penceresi görünümlerini komutları da iletir ve bildirim iletileri için Denetim Windows'dan yanıt verebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Denetim çubukları (nasıl bunlar çerçeve penceresine sığacak)](../mfc/control-bars.md)

- [Menüleri, Denetim çubuklarını ve Hızlandırıcıları (nasıl bunlar çerçeve penceresine sığacak) yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)

- [Komut yönlendirme (Başlangıç, çerçeve penceresinin görünümünü ve diğer komut hedefleri için)](../mfc/command-routing.md)

- [Belge/View mimarisi](../mfc/document-view-architecture.md)

- [Denetim çubukları](../mfc/control-bars.md)

- [Denetimler](../mfc/controls-mfc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve Pencereleri](../mfc/frame-windows.md)

