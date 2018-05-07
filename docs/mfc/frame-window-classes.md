---
title: Çerçeve penceresi sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b9003ba503e0a78e5f223e766346d63679d9959
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes"></a>Çerçeve Penceresi Sınıfları
Her uygulama bir "ana çerçeve penceresi", genellikle kendi başlıkta uygulama adına sahip bir masaüstü penceresi sahiptir. Her bir belgenin genellikle bir "belge çerçeve penceresi." sahip Belge çerçeve penceresi belgenin verileri sunan en az bir görünümü içerir.  
  
## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Çerçeve pencereleri SDI ve MDI uygulamaları  
 SDI uygulamaya ait sınıfından türetilen bir çerçeve penceresi yok [CFrameWnd](../mfc/reference/cframewnd-class.md). Bu, ana çerçeve penceresi ve belge çerçeve penceresi penceredir. MDI uygulamaya ait ana çerçeve penceresi sınıfından türetilir [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), ve MDI alt pencereleri olan belge çerçeve pencereleri sınıfından türetilen [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="use-the-frame-window-class-or-derive-from-it"></a>Çerçeve pencere sınıfı kullanın ya da bundan türetir  
 Bu sınıfların çoğu uygulamalarınız için gereksinim duyduğunuz çerçeve penceresi işlevsellik sağlar. Normal koşullar altında varsayılan davranış ve görünümünü sağladıkları gereksinimlerinize uygun. Ek işlevler gerekiyorsa, bu sınıflardan türetilir.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Uygulama Sihirbazı tarafından oluşturulan çerçeve pencere sınıfları](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
-   [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencereleri](../mfc/frame-windows.md)

