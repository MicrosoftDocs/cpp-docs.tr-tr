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
ms.openlocfilehash: c17ba2b6dd79e8e62baa29bba403c136d16a0d95
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077529"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>Uygulama Sihirbazı Tarafından Oluşturulan Çerçeve Pencere Sınıfları

**Yeni proje** iletişim kutusundan yenı bir MFC projesi oluşturduğunuzda, uygulama, belge ve görünüm sınıflarına ek olarak, uygulama Sihirbazı uygulamanızın ana çerçeve penceresi için türetilmiş bir çerçeve pencere sınıfı oluşturur. Sınıfı varsayılan olarak `CMainFrame` çağrılır ve içeren dosyalar MAINFRM olarak adlandırılır. H ve MAINFRM. CPP.

Uygulamanız SDI ise, `CMainFrame` sınıfınız [CFrameWnd](../mfc/reference/cframewnd-class.md)sınıfından türetilir.

Uygulamanız MDI ise, `CMainFrame` [Cmdiframewnd](../mfc/reference/cmdiframewnd-class.md)sınıfından türetilir. Bu durumda `CMainFrame` menü, araç çubuğu ve durum çubuklarını tutan ana kareyi uygular. Uygulama Sihirbazı sizin için yeni bir belge çerçeve pencere sınıfı türemez. Bunun yerine, [Cmdictepdwnd sınıfında](../mfc/reference/cmdichildwnd-class.md)varsayılan uygulamayı kullanır. MFC çerçevesi, her bir görünümü (`CScrollView`, `CEditView`, `CTreeView`, `CListView`, vb.) içerecek şekilde, uygulamanın gerektirdiği bir alt pencere oluşturur. Belge çerçevesi pencerenizi özelleştirmeniz gerekiyorsa, yeni bir belge çerçeve pencere sınıfı (bkz. [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)) oluşturabilirsiniz.

Bir araç çubuğunu desteklemeyi seçerseniz, sınıf Ayrıca, [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CStatusBar](../mfc/reference/cstatusbar-class.md) türünde üye değişkenlerine ve iki [Denetim çubuğunu](../mfc/control-bars.md)başlatacak bir `OnCreate` Message-Handler işlevine sahiptir.

Bu çerçeve pencere sınıfları oluşturulan olarak çalışır, ancak işlevlerini geliştirmek için üye değişkenleri ve üye işlevleri eklemeniz gerekir. Ayrıca pencere sınıflarınızın diğer Windows iletilerini işlemesini de isteyebilirsiniz. Daha fazla bilgi için bkz. [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Penceresi Sınıfları](../mfc/frame-window-classes.md)<br/>
[MFC Programı veya Denetim Kaynağı ve Başlık Dosyaları](../build/reference/mfc-program-or-control-source-and-header-files.md)
