---
title: MDI Alt Öğe Pencerelerini Yönetme
ms.date: 11/04/2016
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: 2055c215392c6805791de729ff6ab8c6a9057308
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629417"
---
# <a name="managing-mdi-child-windows"></a>MDI Alt Öğe Pencerelerini Yönetme

MDI ana çerçeve pencereleri (uygulama başına bir adet) MDICLIENT penceresi olarak adlandırılan özel alt pencere içerir. Ana çerçeve penceresinin istemci alanına MDICLIENT penceresi yönetir ve kendini alt öğe pencerelerini belirtiyor: türetilen belge pencereleri `CMDIChildWnd`. Belge pencereleri çerçeve pencereleri kendilerini (MDI alt pencereleri) olduğundan, kendi alt öğeleri'ne de sağlayabilirsiniz. Bu durumların tümünde, ana pencereyi, kendi alt pencereleri yönetir ve onlara bazı komutlar iletir.

Bir MDI çerçeve penceresinin çerçeve penceresi, Denetim çubuklarını birlikte yeniden konumlandırma MDICLIENT penceresi yönetir. MDICLIENT penceresi tüm MDI alt çerçeve pencereleri sırayla yönetir. Aşağıdaki şekilde bir MDI çerçeve penceresinin, kendi MDICLIENT penceresi ve onun alt belge çerçeve pencereleri arasındaki ilişki gösterilmektedir.

![Bir MDI çerçeve penceresinin alt windows](../mfc/media/vc37gb1.gif "vc37gb1") MDI çerçeve Windows ve alt öğeleri

Varsa bir MDI çerçeve penceresinin de geçerli MDI alt penceresi ile birlikte çalışır. Kendisini işlemek denemeden önce MDI çerçeve penceresinin MDI alt komut iletileri atar.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

