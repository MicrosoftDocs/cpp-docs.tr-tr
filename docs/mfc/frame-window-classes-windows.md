---
title: Çerçeve Penceresi Sınıfları (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 3e56bd0f449992118db75a44c39b6e0e15cb0d86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392799"
---
# <a name="frame-window-classes-windows"></a>Çerçeve Penceresi Sınıfları (Windows)

Çerçeve pencereleri uygulama veya bir uygulamanın parçası çerçeve windows ' dir. Çerçeve pencereleri genellikle görünümleri, araç çubuklarını ve durum çubukları gibi diğer windows içerir. Durumunda, `CMDIFrameWnd`, bunlar içerebilir `CMDIChildWnd` dolaylı olarak nesneleri.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Bir SDI uygulamanın ana çerçeve penceresi için taban sınıf. Ayrıca temel sınıf için tüm diğer çerçeve penceresi sınıfları.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Bir MDI uygulamanın ana çerçeve penceresi için taban sınıf.

[Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Bir MDI uygulamanın belge çerçeve pencereleri için temel sınıf.

[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)<br/>
Genelde kayan araç çubukları görülen yarım yükseklikte bir pencere.

[Coleıpframewnd](../mfc/reference/coleipframewnd-class.md)<br/>
Sunucu belgesinin yerinde düzenlenirken çerçeve penceresi için bir görünüm sağlar.

## <a name="related-class"></a>İlgili sınıfı

Sınıf `CMenu` , uygulamanızın menüleri erişmek bir arabirim sağlar. Menüleri dinamik olarak çalışma zamanında düzenleme için kullanışlıdır. Örneğin, eklerken veya menü öğeleri bağlam göre siliniyor. Çerçeve pencereleri ile menüleri en sık kullanılan olsa da, bunlar da iletişim kutuları ve diğer nonchild windows ile kullanılabilir.

[CMenu](../mfc/reference/cmenu-class.md)<br/>
Kapsülleyen bir `HMENU` uygulamanın menü çubuğu ve açılır menüler tanıtıcısı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
