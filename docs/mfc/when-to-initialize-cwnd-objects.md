---
title: "CWnd nesneleri başlatılacağı zaman | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d1efceb4fa826d5cd2bf8dc900180eb36cea4de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd Nesneleri Ne Zaman Başlatılır?
Windows, kendi alt oluşturamaz veya herhangi bir Windows API işlevleri oluşturucuda çağrısı bir `CWnd`-türetilmiş bir nesne içermelidir. Bunun nedeni, `HWND` için `CWnd` nesne henüz oluşturulmadı. Alt öğe pencerelerini ekleme gibi en Windows'a özgü başlatma Bitti, bir [OnCreate](../mfc/reference/cwnd-class.md#oncreate) ileti işleyicisi.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)  
  
-   [Belge/görünüm oluşturma](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

