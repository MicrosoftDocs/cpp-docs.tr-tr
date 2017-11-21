---
title: "Uygulama Sihirbazı tarafından oluşturulan çerçeve penceresi sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CMainFrame
dev_langs: C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6cf6b49714f8549f5e5c940b00fcaccc39667933
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları
Kullandığınızda [Uygulama Sihirbazı](../ide/creating-desktop-projects-by-using-application-wizards.md) uygulama, belge ve görünüm sınıfları, ek bir iskelet uygulama oluşturmak için Uygulama Sihirbazı'nı, uygulamanızın ana çerçeve penceresi için bir türetilmiş çerçeve pencere sınıfı oluşturur. Sınıf adı verilen `CMainFrame` varsayılan ve onu içeren dosyaları tarafından MAINFRM olarak adlandırılır. H ve MAINFRM. CPP.  
  
 Uygulamanız SDI, ise, `CMainFrame` sınıfından türetilmiş sınıf [CFrameWnd](../mfc/reference/cframewnd-class.md).  
  
 Uygulamanız MDI, ise `CMainFrame` sınıfından türetilen [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). Bu durumda `CMainFrame` menü, araç çubuğu ve durum çubuğu tutan ana çerçeve uygular. Uygulama Sihirbazı'nı sizin için yeni bir belge çerçeve penceresi sınıfında türemiyor. Bunun yerine, varsayılan uygulamasında kullanan [Cmdıchildwnd sınıfı](../mfc/reference/cmdichildwnd-class.md). MFC çerçevesi her görünüm içerecek şekilde alt pencere oluşturur (türü olabilir `CScrollView`, `CEditView`, `CTreeView`, `CListView`, vb.), uygulama gerektiriyor. Belge çerçeve penceresi özelleştirmeniz gerekiyorsa, yeni bir belge çerçeve penceresi sınıfında oluşturabilirsiniz (bkz [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)).  
  
 Araç çubuğu desteklemek seçerseniz, sınıfı ayrıca türündeki üye değişkeni yok [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CStatusBar](../mfc/reference/cstatusbar-class.md) ve bir `OnCreate` iki başlatmak için ileti işleyicisi işlevi [ Denetim çubukları](../mfc/control-bars.md).  
  
 Bu çerçeve penceresi sınıfları oluşturuldu olarak çalışır, ancak bunların işlevselliğini geliştirmek için üye değişkenleri ve üye işlevleri eklemeniz gerekir. Diğer Windows iletilerini işleme, pencere sınıfları olmasını isteyebilirsiniz. Daha fazla bilgi için bkz: [miktar MFC tarafından oluşturulan bir pencere stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve penceresi sınıfları](../mfc/frame-window-classes.md)   
 [MFC programı veya Denetim Kaynağı ve başlık dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)

