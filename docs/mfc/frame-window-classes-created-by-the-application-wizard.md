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
ms.openlocfilehash: 00254bdf49015f26ac257789a15afd1e7f5cc31f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621703"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları

**Yeni proje** iletişim kutusundan yenı bir MFC projesi oluşturduğunuzda, uygulama, belge ve görünüm sınıflarına ek olarak, uygulama Sihirbazı uygulamanızın ana çerçeve penceresi için türetilmiş bir çerçeve pencere sınıfı oluşturur. Sınıfı varsayılan olarak çağrılır `CMainFrame` ve içeren dosyalar MAINFRM olarak adlandırılır. H ve MAINFRM. CPP.

Uygulamanız SDI ise, `CMainFrame` sınıfınız [CFrameWnd](reference/cframewnd-class.md)sınıfından türetilir.

Uygulamanız MDI ise `CMainFrame` [Cmdiframewnd](reference/cmdiframewnd-class.md)sınıfından türetilir. Bu durumda `CMainFrame` , menü, araç çubuğu ve durum çubuklarını tutan ana çerçeveyi uygular. Uygulama Sihirbazı sizin için yeni bir belge çerçeve pencere sınıfı türemez. Bunun yerine, [Cmdictepdwnd sınıfında](reference/cmdichildwnd-class.md)varsayılan uygulamayı kullanır. MFC çerçevesi, `CScrollView` `CEditView` `CTreeView` uygulamanın gerektirdiği her bir görünümü (,,, vb `CListView` . olabilir) içeren bir alt pencere oluşturur. Belge çerçevesi pencerenizi özelleştirmeniz gerekiyorsa, yeni bir belge çerçeve pencere sınıfı (bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)) oluşturabilirsiniz.

Bir araç çubuğunu desteklemeyi seçerseniz, sınıf Ayrıca, [CToolBar](reference/ctoolbar-class.md) ve [CStatusBar](reference/cstatusbar-class.md) türünde üye değişkenlerine ve `OnCreate` iki [Denetim çubuğunu](control-bars.md)başlatacak bir ileti işleyicisi işlevine sahiptir.

Bu çerçeve pencere sınıfları oluşturulan olarak çalışır, ancak işlevlerini geliştirmek için üye değişkenleri ve üye işlevleri eklemeniz gerekir. Ayrıca pencere sınıflarınızın diğer Windows iletilerini işlemesini de isteyebilirsiniz. Daha fazla bilgi için bkz. [MFC tarafından oluşturulan pencerenin stillerini değiştirme](changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Penceresi Sınıfları](frame-window-classes.md)<br/>
[MFC programı veya denetim kaynağı ve üstbilgi dosyaları](../build/reference/mfc-program-or-control-source-and-header-files.md)
