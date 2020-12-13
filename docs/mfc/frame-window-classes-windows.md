---
description: 'Daha fazla bilgi edinin: çerçeve penceresi sınıfları (Windows)'
title: Çerçeve Penceresi Sınıfları (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: dcd7dea1fd138fbe2ebf3f82013b00cff5ff1f52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339715"
---
# <a name="frame-window-classes-windows"></a>Çerçeve Penceresi Sınıfları (Windows)

Çerçeve pencereleri, bir uygulamanın veya bir uygulamanın bir bölümünün çerçevesini oluşturan Windows. Çerçeve pencereleri genellikle görünümler, araç çubukları ve durum çubukları gibi diğer pencereleri içerir. Bu durumda `CMDIFrameWnd` , `CMDIChildWnd` nesneleri dolaylı olarak içerebilir.

[CFrameWnd](reference/cframewnd-class.md)<br/>
SDI uygulamasının ana çerçeve penceresi için temel sınıf. Ayrıca tüm diğer çerçeve pencere sınıfları için temel sınıf.

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI uygulamasının ana çerçeve penceresi için temel sınıf.

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI uygulamasının belge çerçeve pencereleri için temel sınıf.

[CMiniFrameWnd](reference/cminiframewnd-class.md)<br/>
Genellikle kayan araç çubuklarının etrafında görülen yarı yükseklikli bir çerçeve penceresi.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Bir sunucu belgesi yerinde düzenlenirken bir görünüm için çerçeve penceresi sağlar.

## <a name="related-class"></a>İlgili sınıf

Sınıfı `CMenu` , uygulamanızın menülerine erişmek için bir arabirim sağlar. Çalışma zamanında menüleri dinamik olarak değiştirmek için kullanışlıdır; Örneğin, bağlam uyarınca menü öğelerini ekleme veya silme. Menüler yalnızca çerçeve pencereleri ile kullanıldığından, iletişim kutuları ve alt öğe olmayan diğer pencereler ile de kullanılabilir.

[CMenu](reference/cmenu-class.md)<br/>
`HMENU`Uygulamanın menü çubuğu ve açılır menüleri için bir tutamacı kapsüller.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
