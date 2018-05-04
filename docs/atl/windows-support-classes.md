---
title: Windows Destek sınıfları (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.windows
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2095e5141dfdd320bae0e7aa69ffd4b3c9fe9a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-support-classes"></a>Windows Destek sınıfları
Aşağıdaki sınıflar windows için destek sağlar:  
  
-   [_U_MENUorID](../atl/reference/u-menuorid-class.md) için sarmalayıcıları sağlar **CreateWindow'u** ve **CreateWindowEx**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) bir pencere işlemek için kullanılan yöntemler içerir. `CWindow` temel sınıfı olan `CWindowImpl`, `CDialogImpl`, ve `CContainedWindow`.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) yeni bir pencere sınıfına dayalı bir pencere uygular. Ayrıca bir alt veya üst sınıf pencere sağlar.  
  
-   [Cdialogımpl](../atl/reference/cdialogimpl-class.md) bir iletişim kutusu uygular.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX denetimlerini sunan bir iletişim kutusu (kalıcı veya geçici) uygular.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) temel işlevselliğe sahip bir iletişim kutusu (kalıcı veya geçici) uygular.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) bir ActiveX denetimini barındıran bir pencere yönetir.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) bir ActiveX denetimini barındırır ve ayrıca Lisanslı ActiveX denetimlerini barındırma desteği olan bir pencere düzenleme için yöntemler sağlar.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) başka bir nesne içinde bulunan bir pencere uygular.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) yeni bir pencere sınıfı bilgilerini yönetir.  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md) dinamik ileti haritaları zincirleme destekler.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) kendi ileti kullanıma sunmak için bir nesne eşlemeleri diğer nesnelere sağlar.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) ATL pencere nesnesi nitelikler Standartlaştırma, basit bir yöntem sağlar.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) pencere stilleri ve bir pencere oluşturmak için kullanılan genişletilmiş stilleri varsayılan değerleri sağlar. Bir pencere oluşturma sırasında sağlanan değerler için mantıksal veya işlecini kullanarak bu değerleri eklenir.  
  
## <a name="related-articles"></a>İlgili Makaleler  
 [ATL Pencere Sınıfları](../atl/atl-window-classes.md)  
  
 [ATL öğretici](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../atl/atl-class-overview.md)   
 [İleti eşleme makroları](../atl/reference/message-map-macros-atl.md)   
 [Pencere Sınıfı Makroları](../atl/reference/window-class-macros.md)

