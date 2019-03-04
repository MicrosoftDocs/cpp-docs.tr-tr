---
title: MDI Alt Öğe Pencerelerini Yönetme
ms.date: 11/19/2018
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
ms.openlocfilehash: d4b4a4876f47452361b13837b0279f5bf98f8658
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283689"
---
# <a name="managing-mdi-child-windows"></a>MDI Alt Öğe Pencerelerini Yönetme

MDI ana çerçeve pencereleri (uygulama başına bir adet) MDICLIENT penceresi olarak adlandırılan özel alt pencere içerir. Ana çerçeve penceresinin istemci alanına MDICLIENT penceresi yönetir ve kendini alt öğe pencerelerini belirtiyor: türetilen belge pencereleri `CMDIChildWnd`. Belge pencereleri çerçeve pencereleri kendilerini (MDI alt pencereleri) olduğundan, kendi alt öğeleri'ne de sağlayabilirsiniz. Bu durumların tümünde, ana pencereyi, kendi alt pencereleri yönetir ve onlara bazı komutlar iletir.

Bir MDI çerçeve penceresinin çerçeve penceresi, Denetim çubuklarını birlikte yeniden konumlandırma MDICLIENT penceresi yönetir. MDICLIENT penceresi tüm MDI alt çerçeve pencereleri sırayla yönetir. Aşağıdaki şekilde bir MDI çerçeve penceresinin, kendi MDICLIENT penceresi ve onun alt belge çerçeve pencereleri arasındaki ilişki gösterilmektedir.

![Bir MDI çerçeve penceresinin alt windows](../mfc/media/vc37gb1.gif "bir MDI çerçeve penceresinin içinde alt pencereler") <br/>
MDI çerçeve Windows ve alt öğeleri

Varsa bir MDI çerçeve penceresinin de geçerli MDI alt penceresi ile birlikte çalışır. Kendisini işlemek denemeden önce MDI çerçeve penceresinin MDI alt komut iletileri atar.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)
