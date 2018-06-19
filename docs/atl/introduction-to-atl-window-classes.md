---
title: ATL pencere sınıfları giriş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea9b275831aee3ea96da1036019db07f9e2dfc93
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356692"
---
# <a name="introduction-to-atl-window-classes"></a>ATL pencere sınıfları giriş
Aşağıdaki ATL sınıfları uygulamak ve windows işlemek için tasarlanmıştır:  
  
-   [CWindow](../atl/reference/cwindow-class.md) bir pencere işleyicisi ekleme sayesinde `CWindow` nesnesi. Ardından çağıran `CWindow` pencereyi denetlemek için yöntemler.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) yeni bir pencere uygulamak ve işlem iletileri ileti eşlemesi ile olanak tanır. Oluşturabileceğiniz bir pencere bir yeni Windows sınıfı, üst sınıf varolan bir sınıfa veya bir alt kümesi varolan pencerede göre.  
  
-   [Cdialogımpl](../atl/reference/cdialogimpl-class.md) , kalıcı bir ya da kalıcı olmayan iletişim kutusu ve işlem iletileri ileti eşlemesi ile uygulamanızı sağlar.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) başka bir sınıf, ileti eşlemesi barındırılan bir pencere uygulayan önceden oluşturulmuş bir sınıftır. Kullanarak `CContainedWindowT` ileti işleme tek bir sınıf merkezileştirmek olanak tanır.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX denetimlerini sunan bir iletişim kutusu (kalıcı veya geçici) uygulamak sağlar.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) modal bir iletişim kutusu ile temel işlevlerini uygulamak sağlar.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) bir ActiveX denetimini barındıran bir pencere uygulamak olanak tanır.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) , lisanslı bir ActiveX denetimi barındıran bir pencere uygulanmasını sağlar.  
  
 Belirli bir pencere sınıfları yanı sıra ATL ATL pencere nesnesi uyarlamasını kolaylaştırmak için tasarlanmış çeşitli sınıflar sağlar. Bunlar şu şekildedir:  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) yeni bir pencere sınıfı bilgilerini yönetir.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) ve [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ATL pencere nesnesi nitelikler Standartlaştırma, basit bir yöntem sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

