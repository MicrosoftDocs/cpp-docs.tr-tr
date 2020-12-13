---
description: 'Daha fazla bilgi edinin: ATL pencere sınıflarına giriş'
title: ATL pencere sınıflarına giriş
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 54a9d9764450025e51f9fac368a3434ca786fe09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152730"
---
# <a name="introduction-to-atl-window-classes"></a>ATL pencere sınıflarına giriş

Aşağıdaki ATL sınıfları Windows uygulamak ve işlemek için tasarlanmıştır:

- [CWindow](../atl/reference/cwindow-class.md) , nesnesine bir pencere tutamacı eklemenize olanak tanır `CWindow` . Ardından `CWindow` pencereyi yönetmek için yöntemleri çağırın.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) , yeni bir pencere uygulamanıza ve iletileri ileti eşlemesiyle işlem yapmanıza olanak sağlar. Yeni bir Windows sınıfına dayalı bir pencere oluşturabilir, var olan bir sınıfı süper sınıfa veya varolan bir pencerenin alt sınıfına sahip olabilirsiniz.

- [Cdialogimpl](../atl/reference/cdialogimpl-class.md) , kalıcı veya kalıcı olmayan bir iletişim kutusu uygulamanıza ve iletileri ileti eşlemesiyle işlem yapmanıza olanak sağlar.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) , ileti eşlemesi başka bir sınıfta bulunan bir pencere uygulayan önceden oluşturulmuş bir sınıftır. Kullanımı `CContainedWindowT` , tek bir sınıfta ileti işlemeyi merkezileştirmenizi sağlar.

- [Caxdialogimpl](../atl/reference/caxdialogimpl-class.md) , ActiveX denetimlerini barındıran bir iletişim kutusu (kalıcı veya kalıcı) uygulamanıza olanak sağlar.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) , temel işlevsellikle kalıcı iletişim kutusu uygulamanıza olanak tanır.

- [CAxWindow](../atl/reference/caxwindow-class.md) , ActiveX denetimi barındıran bir pencere uygulamanıza olanak tanır.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) , lisanslı bir ActiveX denetimi barındıran bir pencere uygulamanıza olanak tanır.

Belirli pencere sınıflarının yanı sıra, ATL, ATL pencere nesnesi uygulamasını kolaylaştırmak için tasarlanan çeşitli sınıflar sağlar. Bunlar şu şekildedir:

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) , yeni bir pencere sınıfının bilgilerini yönetir.

- [CWinTraits](../atl/reference/cwintraits-class.md) ve [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) , atl pencere nesnesinin nitelikleri standartlaştırarak basit bir yöntem sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
