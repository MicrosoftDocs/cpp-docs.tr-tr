---
title: ATL pencere sınıflarına giriş
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 987e2eab5fe4eec32d88b7c1528f1e3189fc925a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459806"
---
# <a name="introduction-to-atl-window-classes"></a>ATL pencere sınıflarına giriş

Aşağıdaki ATL sınıfları, uygulamak ve windows işlemek için tasarlanmıştır:

- [CWindow](../atl/reference/cwindow-class.md) eklemek için bir pencere tutucu sağlar `CWindow` nesne. Ardından çağırın `CWindow` pencereyi denetlemek için yöntemleri.

- [Cwindowımpl](../atl/reference/cwindowimpl-class.md) yeni bir pencere uygular ve ileti eşlemesi iletilerle işlemenize olanak sağlar. Oluşturabileceğiniz bir pencere bir yeni Windows sınıf, sınıfın var olan bir sınıfı veya alt varolan pencereye göre.

- [Cdialogımpl](../atl/reference/cdialogimpl-class.md) kalıcı bir ya da ileti eşlemesi ile modsuz iletişim kutusu ve işlem iletileri olanak tanır.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) bir penceresi olan ileti eşlemesi yer alan başka bir sınıf uygulayan önceden oluşturulmuş bir sınıftır. Kullanarak `CContainedWindowT` merkezileştirin ileti işlemede edıfact'i bir sınıf sağlar.

- [Caxdialogımpl](../atl/reference/caxdialogimpl-class.md) ActiveX denetimleri sunan bir iletişim kutusu (kalıcı veya kısıtlayıcı olmayan) olanak tanır.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) temel işlevsellikle kalıcı bir iletişim kutusu olanak tanır.

- [CAxWindow](../atl/reference/caxwindow-class.md) , bir ActiveX denetimi barındıran bir pencere olanak tanır.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) lisanslı bir ActiveX denetimi barındıran bir pencere olanak tanır.

Belirli bir pencere sınıflarının yanı sıra, ATL bir ATL pencere nesnesi uygulamasını daha kolay hale getirmek için tasarlanan çok sınıf sağlar. Bunlar şu şekildedir:

- [Cwndclassınfo](../atl/reference/cwndclassinfo-class.md) yeni bir pencere sınıf bilgilerini yönetir.

- [CWinTraits](../atl/reference/cwintraits-class.md) ve [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ATL pencere nesnenin nitelikler Standartlaştırma basit bir yöntem sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)

