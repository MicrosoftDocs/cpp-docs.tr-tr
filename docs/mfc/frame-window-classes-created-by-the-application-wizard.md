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
ms.openlocfilehash: 46da8fc0cb98406bdf97285d7c6f824afd61c4bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392823"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları

Yeni bir MFC oluşturmak için proje zaman **yeni proje** iletişim kutusunda, uygulama, belge ve görünüm sınıfları ek olarak, uygulamanızın ana çerçeve penceresi için bir türetilen çerçeve-pencere sınıf Uygulama Sihirbazı oluşturur. Sınıf `CMainFrame` varsayılan ve içerdiği dosyalar MAINFRM adlandırılır. H ve MAINFRM. CPP.

Uygulamanız, SDI ise, `CMainFrame` sınıfından türetilmiş sınıf [CFrameWnd](../mfc/reference/cframewnd-class.md).

Uygulamanız, MDI ise `CMainFrame` sınıfından türetilen [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md). Bu durumda `CMainFrame` menüsü araç çubuğu ve durum çubuklarını tutan ana çerçeve uygular. Uygulama Sihirbazı'nı sizin için yeni bir belge çerçeve penceresi sınıfında türemiyor. Bunun yerine, varsayılan uygulamasında kullanır [Cmdıchildwnd sınıfı](../mfc/reference/cmdichildwnd-class.md). MFC çerçevesi her görünümü içerecek bir alt pencere oluşturur (türünde olabilir `CScrollView`, `CEditView`, `CTreeView`, `CListView`, vb.), uygulama gerektiriyor. Belge çerçeve penceresinin özelleştirmek gerekiyorsa, yeni bir belge çerçeve penceresi sınıfında oluşturabilirsiniz (bkz [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)).

Bir araç desteği seçerseniz, sınıf türünün üye değişkenleri de vardır. [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CStatusBar](../mfc/reference/cstatusbar-class.md) ve `OnCreate` iki başlatmak için ileti işleyicisi işlevi [ Denetim çubukları](../mfc/control-bars.md).

Bu çerçeve penceresi sınıfları oluşturulduğu şekilde çalışır ancak bunların işlevselliğini geliştirmek için üye değişkenleri ve üye işlevleri eklemeniz gerekir. Diğer Windows iletilerini işleme pencere sınıflarınızı olmasını isteyebilirsiniz. Daha fazla bilgi için [penceresinde oluşturulan MFC tarafından stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Penceresi Sınıfları](../mfc/frame-window-classes.md)<br/>
[MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../build/reference/mfc-program-or-control-source-and-header-files.md)

