---
title: "MDI alt öğe pencerelerini yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MDICLIENT
dev_langs: C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1489fa4ec75b94c9daad7216a28599c6ef67e5a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="managing-mdi-child-windows"></a>MDI Alt Öğe Pencerelerini Yönetme
MDI ana çerçeve pencereleri (uygulama başına bir tane) olarak adlandırılan özel alt pencere içeren **MDICLIENT** penceresi. **MDICLIENT** penceresi ana çerçeve penceresi istemci alanını yönetir ve kendi alt öğe pencerelerini var.: türetilmiş belge pencereleri `CMDIChildWnd`. Belge pencereleri çerçeve pencereleri kendilerini (MDI alt pencereleri) olduğundan, ayrıca kendi alt öğelerini olabilir. Bu durumların tümünde, ana pencereyi alt windows yönetir ve bunlara bazı komutlar iletir.  
  
 Çerçeve penceresi bir MDI çerçeve penceresinde yönetir **MDICLIENT** denetim çubukları ile birlikte yeniden konumlandırma penceresi. **MDICLIENT** penceresinde, buna karşılık, tüm MDI alt çerçeve pencereleri yönetir. Aşağıdaki şekilde bir MDI çerçeve penceresi ilişkiyi gösterir, **MDICLIENT** penceresi ve onun alt belge çerçeve pencereleri.  
  
 ![Alt pencereler MDI çerçeve penceresinde](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI çerçeve pencereleri ve alt öğeleri  
  
 Varsa bir MDI çerçeve penceresi de geçerli MDI alt pencere ile birlikte çalışır. Kendisini işlemek denemeden önce MDI çerçeve penceresi MDI alt komut iletileri atar.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)

