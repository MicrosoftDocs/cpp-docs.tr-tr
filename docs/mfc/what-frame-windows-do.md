---
description: 'Hakkında daha fazla bilgi edinin: çerçeve pencereleri'
title: Çerçeve Pencerelerinin Görevi
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 8f70bbe55b15310133688079236fe57459679090
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142837"
---
# <a name="what-frame-windows-do"></a>Çerçeve Pencerelerinin Görevi

Yalnızca bir görünümün çerçevelendirme yanı sıra, çerçeve pencereleri, çerçevesini görünümüyle ve uygulamayla koordine eden çok sayıda görevden sorumludur. [Cmdiframewnd](../mfc/reference/cmdiframewnd-class.md) ve [Cmdictepdwnd](../mfc/reference/cmdichildwnd-class.md) , [CFrameWnd](../mfc/reference/cframewnd-class.md)öğesinden devralınır ve bu sayede, bunlara `CFrameWnd` eklenen yeni yetenekler de vardır. Alt pencereler gibi görünümler, düğmeler ve liste kutuları gibi denetimler, denetim çubukları ve araç çubukları, durum çubukları ve İletişim çubukları dahil olmak üzere bir dizi örnek.

Çerçeve penceresi, alt pencerelerinin yerleşimini yönetmekten sorumludur. MFC çerçevesinde, bir çerçeve penceresi, istemci alanı içindeki tüm denetim çubuklarını, görünümleri ve diğer alt pencereleri konumlandırır.

Çerçeve penceresi ayrıca komutları görünümlerine iletir ve denetim pencerelerinin bildirim iletilerine yanıt verebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Denetim çubukları (çerçeve penceresine nasıl uydukları)](../mfc/control-bars.md)

- [Menüleri, denetim çubuklarını ve hızlandırıcıları yönetme (çerçeve penceresine nasıl uyum)](../mfc/managing-menus-control-bars-and-accelerators.md)

- [Komut yönlendirme (çerçeve penceresinden görünümüne ve diğer komut hedeflerine)](../mfc/command-routing.md)

- [Belge/View mimarisi](../mfc/document-view-architecture.md)

- [Denetim çubukları](../mfc/control-bars.md)

- [Denetimler](../mfc/controls-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencereleri](../mfc/frame-windows.md)
