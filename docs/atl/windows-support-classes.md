---
title: Windows desteği sınıfları (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.windows
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: e7e9e1f4fb94537cdd131e58ef3fc481ee1c012e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281037"
---
# <a name="windows-support-classes"></a>Windows desteği sınıfları

Aşağıdaki sınıflar, windows için destek sağlar:

- [_U_menuorıd](../atl/reference/u-menuorid-class.md) için sarmalayıcıları sağlar `CreateWindow` ve `CreateWindowEx`.

- [CWindow](../atl/reference/cwindow-class.md) pencere yönlendirmeye yönelik yöntemleri içerir. `CWindow` temel sınıfı olan `CWindowImpl`, `CDialogImpl`, ve `CContainedWindow`.

- [Cwindowımpl](../atl/reference/cwindowimpl-class.md) yeni bir pencere sınıfını esas bir pencere uygular. Ayrıca alt veya üst pencere sağlar.

- [Cdialogımpl](../atl/reference/cdialogimpl-class.md) bir iletişim kutusu uygular.

- [Caxdialogımpl](../atl/reference/caxdialogimpl-class.md) ActiveX denetimleri sunan bir iletişim kutusu (kalıcı veya kısıtlayıcı olmayan) uygular.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) (kalıcı veya kısıtlayıcı olmayan) bir iletişim kutusu ile temel işlevselliğini uygular.

- [CAxWindow](../atl/reference/caxwindow-class.md) , bir ActiveX denetimi barındıran bir pencere yönetir.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) bir ActiveX denetimini barındırır ve ayrıca lisanslı bir ActiveX denetimlerini barındırma desteği olan bir pencere düzenleme yöntemlerini sağlar.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) başka bir nesne içinde yer alan bir pencere uygular.

- [Cwndclassınfo](../atl/reference/cwndclassinfo-class.md) yeni bir pencere sınıf bilgilerini yönetir.

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) dinamik zincirleme ileti haritalarını destekler.

- [CMessageMap](../atl/reference/cmessagemap-class.md) iletisini göstermek için bir nesne eşler diğer nesnelere sağlar.

- [CWinTraits](../atl/reference/cwintraits-class.md) ATL pencere nesnenin nitelikler Standartlaştırma çok basit bir yöntemini sağlar.

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) pencere stilleri ve bir pencere oluşturmak için kullanılan genişletilmiş stiller için varsayılan değerleri sağlar. Bir pencere oluşturma sırasında sağlanan değerler için mantıksal veya işlecini kullanarak bu değerleri eklenir.

## <a name="related-articles"></a>İlgili Makaleler

[ATL Pencere Sınıfları](../atl/atl-window-classes.md)

[ATL öğretici](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../atl/atl-class-overview.md)<br/>
[İleti eşleme makroları](../atl/reference/message-map-macros-atl.md)<br/>
[Pencere Sınıfı Makroları](../atl/reference/window-class-macros.md)
