---
title: "CWnd nesneleri başlatılacağı zaman | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c2e9d99fe2f01111308a9a7a002aeefbf472a0b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd Nesneleri Ne Zaman Başlatılır?
Windows, kendi alt oluşturamaz veya herhangi bir Windows API işlevleri oluşturucuda çağrısı bir `CWnd`-türetilmiş bir nesne içermelidir. Bunun nedeni, `HWND` için `CWnd` nesne henüz oluşturulmadı. Alt öğe pencerelerini ekleme gibi en Windows'a özgü başlatma Bitti, bir [OnCreate](../mfc/reference/cwnd-class.md#oncreate) ileti işleyicisi.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Belge/görünüm oluşturma](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)

