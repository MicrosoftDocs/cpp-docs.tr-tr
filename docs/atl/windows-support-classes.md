---
description: 'Hakkında daha fazla bilgi edinin: Windows destek sınıfları'
title: Windows destek sınıfları (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: c88a6ef878a428581ca090e78b2fac3b5e02131d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138078"
---
# <a name="windows-support-classes"></a>Windows destek sınıfları

Aşağıdaki sınıflar Windows için destek sağlar:

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) Ve için sarmalayıcılar sağlar `CreateWindow` `CreateWindowEx` .

- [CWindow](../atl/reference/cwindow-class.md) Pencereyi düzenleme yöntemlerini içerir. `CWindow` ,, ve için temel `CWindowImpl` sınıftır `CDialogImpl` `CContainedWindow` .

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) Yeni bir pencere sınıfını temel alan bir pencere uygular. Ayrıca, pencereyi alt sınıflara veya süper sınıfa eklemenizi sağlar.

- [Cdialogimpl](../atl/reference/cdialogimpl-class.md) Bir iletişim kutusu uygular.

- [Caxdialogimpl](../atl/reference/caxdialogimpl-class.md) ActiveX denetimlerini barındıran bir iletişim kutusu (kalıcı veya kalıcı) uygular.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) Temel işlevlerle bir iletişim kutusu (kalıcı veya kalıcı) uygular.

- [CAxWindow](../atl/reference/caxwindow-class.md) Bir ActiveX denetimi barındıran pencereyi yönetir.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) , ActiveX denetimi barındıran bir pencereyi düzenlemek için yöntemler sağlar ve lisanslı ActiveX denetimlerini barındırmak için de destek içerir.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) Başka bir nesne içinde yer alan bir pencere uygular.

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) Yeni bir pencere sınıfının bilgilerini yönetir.

- [Cdynamiczinciri](../atl/reference/cdynamicchain-class.md) , İleti eşlemelerinin dinamik zincirlemesini destekler.

- [CMessageMap](../atl/reference/cmessagemap-class.md) Bir nesnenin ileti eşlemelerini diğer nesnelerle kullanıma almasına izin verir.

- [CWinTraits](../atl/reference/cwintraits-class.md) Bir ATL pencere nesnesinin nitelikleri standartlaştırarak basit bir yöntem sağlar.

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) Pencere oluşturmak için kullanılan pencere stilleri ve genişletilmiş stiller için varsayılan değerleri sağlar. Bu değerler, bir pencerenin oluşturulması sırasında belirtilen değerlere mantıksal OR işleci kullanılarak eklenir.

## <a name="related-articles"></a>İlgili Makaleler

[ATL pencere sınıfları](../atl/atl-window-classes.md)

[ATL öğreticisi](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../atl/atl-class-overview.md)<br/>
[İleti eşleme makroları](../atl/reference/message-map-macros-atl.md)<br/>
[Pencere sınıfı makroları](../atl/reference/window-class-macros.md)
