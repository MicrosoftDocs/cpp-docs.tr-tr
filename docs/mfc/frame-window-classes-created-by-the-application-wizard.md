---
title: Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
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
ms.openlocfilehash: a0610ae901b817a1c8f7707d9ba87c15d634e134
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298067"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları

Kullanırken [Uygulama Sihirbazı](../ide/creating-desktop-projects-by-using-application-wizards.md) uygulama, belge ve görünüm sınıfları, ek bir çatı uygulaması oluşturmak için bir türetilen çerçeve-pencere sınıf, uygulamanızın ana çerçeve penceresi için Uygulama Sihirbazı oluşturur. Sınıf `CMainFrame` varsayılan ve içerdiği dosyalar MAINFRM adlandırılır. H ve MAINFRM. CPP.

Uygulamanız, SDI ise, `CMainFrame` sınıfından türetilmiş sınıf [CFrameWnd](../mfc/reference/cframewnd-class.md).

Uygulamanız, MDI ise `CMainFrame` sınıfından türetilen [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). Bu durumda `CMainFrame` menüsü araç çubuğu ve durum çubuklarını tutan ana çerçeve uygular. Uygulama Sihirbazı'nı sizin için yeni bir belge çerçeve penceresi sınıfında türemiyor. Bunun yerine, varsayılan uygulamasında kullanır [Cmdıchildwnd sınıfı](../mfc/reference/cmdichildwnd-class.md). MFC çerçevesi her görünümü içerecek bir alt pencere oluşturur (türünde olabilir `CScrollView`, `CEditView`, `CTreeView`, `CListView`, vb.), uygulama gerektiriyor. Belge çerçeve penceresinin özelleştirmek gerekiyorsa, yeni bir belge çerçeve penceresi sınıfında oluşturabilirsiniz (bkz [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)).

Bir araç desteği seçerseniz, sınıf türünün üye değişkenleri de vardır. [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CStatusBar](../mfc/reference/cstatusbar-class.md) ve `OnCreate` iki başlatmak için ileti işleyicisi işlevi [ Denetim çubukları](../mfc/control-bars.md).

Bu çerçeve penceresi sınıfları oluşturulduğu şekilde çalışır ancak bunların işlevselliğini geliştirmek için üye değişkenleri ve üye işlevleri eklemeniz gerekir. Diğer Windows iletilerini işleme pencere sınıflarınızı olmasını isteyebilirsiniz. Daha fazla bilgi için [penceresinde oluşturulan MFC tarafından stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Penceresi Sınıfları](../mfc/frame-window-classes.md)<br/>
[MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)
