---
title: Çerçeve Windows neler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf97fb086f9ede43f9679e66a7c917b800f97dc8
ms.sourcegitcommit: e4a690bf33b44432179de0bc537e26616d13c553
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48892195"
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

