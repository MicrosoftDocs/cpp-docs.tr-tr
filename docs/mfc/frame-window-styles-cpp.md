---
title: "Çerçeve pencere stilleri (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30e597a9d8587128e4de1b2bb80db15143620821
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="frame-window-styles-c"></a>Çerçeve Pencere Stilleri (C++)
Çerçevesiyle alma çerçeve pencereleri çoğu program için uygun olan, ancak Gelişmiş işlevlerini kullanarak ek esneklik kazanmadan [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) ve MFC genel işlevi [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow`bir üye işlevidir `CWnd`.  
  
 Uygularsanız **WS_HSCROLL** ve **WS_VSCROLL** ana çerçeve pencere stilleri, bunların yerine uygulanır **MDICLIENT** kullanıcılar kaydırabilirsinizşekildepenceresi**MDICLIENT** alanı.  
  
 Varsa pencerenin **fws_addtotıtle** stili biti ayarlanmış (hangi varsayılan olarak etkindir), görünüm çerçeve penceresi penceresinin başlık çubuğunda görünümün belge adına göre görüntülemek için hangi başlık söyler.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [MDI alt pencereleri (MDICLIENT) yönetme](../mfc/managing-mdi-child-windows.md), MDI alt pencereleri içeren MDI çerçevesinde penceresi  
  
-   [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Pencere stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencereleri](../mfc/frame-windows.md)

