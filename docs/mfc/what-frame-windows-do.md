---
title: "Çerçeve pencerelerinin görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5143bab1ea84392efe1bd5783889c45375365ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="what-frame-windows-do"></a>Çerçeve Pencerelerinin Görevi
Yalnızca bir görünüm çerçeveleme yanı sıra, çerçeve pencereleri çok sayıda görevleri çerçevenin kendi Görünüm ve uygulama ile iletişime katılan sorumludur. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) devralınmalıdır [CFrameWnd](../mfc/reference/cframewnd-class.md), sahip oldukları için `CFrameWnd` ekledikleri yeni özellikler yanı sıra özellikleri. Alt pencereler örnekleri görünümleri, düğmeler ve liste kutuları ve araç çubukları, durum çubukları ve iletişim kutusu çubukları gibi denetim çubukları gibi denetimleri içerir.  
  
 Çerçeve penceresi, kendi alt öğe pencerelerini düzenini yönetilmesinden sorumludur. MFC çerçevesi bir çerçeve penceresinde kendi istemci alanı içinde herhangi bir denetim çubukları, görünümleri ve diğer alt windows yerleştirir.  
  
 Çerçeve penceresi de görünümlerini komutları iletir ve bildirim iletileri için Denetim Windows'dan yanıt verebilir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Denetim çubukları (nasıl bunlar çerçeve penceresine sığacak)](../mfc/control-bars.md)  
  
-   [Menüleri, Denetim çubuklarını ve Hızlandırıcıları (nasıl bunlar çerçeve penceresine sığacak) yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Komut yönlendirme (penceresinden çerçeve kendi görüntülemek ve diğer komut hedefleri için)](../mfc/command-routing.md)  
  
-   [Belge/View mimarisi](../mfc/document-view-architecture.md)  
  
-   [Denetim çubukları](../mfc/control-bars.md)  
  
-   [Denetimler](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencereleri](../mfc/frame-windows.md)

