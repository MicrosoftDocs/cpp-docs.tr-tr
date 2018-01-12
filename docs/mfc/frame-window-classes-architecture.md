---
title: "Çerçeve penceresi sınıfları (Mimari) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.frame
dev_langs: C++
helpviewer_keywords: frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1caf8e4b93e18675b810ced962df6e8adcf521a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="frame-window-classes-architecture"></a>Çerçeve Penceresi Sınıfları (Mimari)
Belge/görünüm mimarisi çerçeve pencereleri bir Görünüm penceresi içeren windows ' dir. Bunlar ayrıca sahip denetim çubukları kendisine bağlı destekler.  
  
 Birden çok belge arabirimi (MDI) uygulamaları, ana pencereyi türetildiği `CMDIFrameWnd`. Dolaylı olarak olan belgeleri çerçeveleri içeren `CMDIChildWnd` nesneleri. `CMDIChildWnd` Nesneleri, buna karşılık, belgeleri görünümleri içerir.  
  
 Tek belge arabirimi (SDI) uygulamalarında ana penceresinde, türetilen `CFrameWnd`, geçerli belge görünümünü içerir.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 SDI uygulamanın ana çerçeve penceresi için temel sınıf. Ayrıca için temel sınıf diğer çerçeve penceresi sınıfları.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI uygulamanın ana çerçeve penceresi için temel sınıf.  
  
 [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI uygulamanın belge çerçeve pencereleri için temel sınıf.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Bir sunucu belge yerinde düzenlendiğinde çerçeve penceresi için bir görünüm sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

