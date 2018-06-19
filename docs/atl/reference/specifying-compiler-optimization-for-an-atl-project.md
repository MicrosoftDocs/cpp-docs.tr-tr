---
title: ATL projeleri için derleyici iyileştirmesi belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0060437613bcdd6281ce5cceb112f5fd7f470bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361976"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL projeleri için derleyici iyileştirmesi belirtme
Varsayılan olarak, [ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE makrosu ile yeni sınıflar gibi oluşturur:  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 ATL sonra _ATL_NO_VTABLE şu şekilde tanımlar:  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 ATL_NO_VTABLE makrosu _ATL_DISABLE_NO_VTABLE tanımlamıyorsa genişleyen `declspec(novtable)`. Kullanarak `declspec(novtable)`vtable işaretçi bildirimi sınıf oluşturucu ve yıkıcı başlatılmış bir sınıfta engeller. Projenizi yapılandırdığınızda, bağlayıcı vtable ve tüm işlevler vtable işaret ettiği ortadan kaldırır.  
  
 ATL_NO_VTABLE, kullanmanız gerekir ve bu nedenle `declspec(novtable)`, doğrudan creatable olmayan taban sınıfına sahip. Değil kullanmalısınız `declspec(novtable)` projenizdeki en çok türetilen sınıfı ile çünkü bu sınıfı (genellikle [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), veya [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) projeniz için vtable işaretçi başlatır.  
  
 Sanal işlevler kullanan herhangi bir nesnenin oluşturucudan çağırmamalıdır `declspec(novtable)`. Bu çağrı taşımalısınız [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) yöntemi.  

  
 Kullanıp emin değilseniz `declspec(novtable)` değiştiricisi, ATL_NO_VTABLE makrosu herhangi sınıfı tanımından kaldırın ya da, genel olarak, belirterek devre dışı bırakabilirsiniz  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 Stdafx.h'de önce diğer tüm ATL üstbilgi dosyaları dahil edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)   
 [Visual C++ proje türleri](../../ide/visual-cpp-project-types.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM nesneleri temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

