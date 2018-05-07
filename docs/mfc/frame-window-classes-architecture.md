---
title: Çerçeve penceresi sınıfları (Mimari) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7de72b77be9be90ca876cfef943500a0312d183
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

