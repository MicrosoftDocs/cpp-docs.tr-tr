---
title: MDI alt öğe pencerelerini yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ddef11e56da760bbecaa47f03dfa6c57dfa3ed
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929487"
---
# <a name="managing-mdi-child-windows"></a>MDI Alt Öğe Pencerelerini Yönetme
MDI ana çerçeve pencereleri (uygulama başına bir tane) MDICLIENT penceresi adlı özel alt pencere içerir. İstemci alanını ana çerçeve penceresi MDICLIENT penceresi yönetir ve kendi alt öğe pencerelerini var.: türetilmiş belge pencereleri `CMDIChildWnd`. Belge pencereleri çerçeve pencereleri kendilerini (MDI alt pencereleri) olduğundan, ayrıca kendi alt öğelerini olabilir. Bu durumların tümünde, ana pencereyi alt windows yönetir ve bunlara bazı komutlar iletir.  
  
 MDI çerçevesi penceresinde, çerçeve penceresi denetim çubukları ile birlikte yeniden konumlandırma MDICLIENT penceresi yönetir. MDICLIENT penceresi sırayla tüm MDI alt çerçeve pencereleri yönetir. Aşağıdaki şekilde bir MDI çerçeve penceresi, kendi MDICLIENT penceresi ve onun alt belge çerçeve pencereleri arasındaki ilişkiyi gösterir.  
  
 ![Alt pencereler MDI çerçeve penceresinde](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI çerçeve pencereleri ve alt öğeleri  
  
 Varsa bir MDI çerçeve penceresi de geçerli MDI alt pencere ile birlikte çalışır. Kendisini işlemek denemeden önce MDI çerçeve penceresi MDI alt komut iletileri atar.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

