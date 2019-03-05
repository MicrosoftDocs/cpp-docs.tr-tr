---
title: ATL projesinde derleyici iyileştirmesi belirtme
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: 6e6fe09aaa0726a39aae8b85cb6581c5d0cd24e1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280023"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL projesinde derleyici iyileştirmesi belirtme

Varsayılan olarak, [ATL denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE makro yeni sınıflar gibi oluşturur:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL ardından _ATL_NO_VTABLE şu şekilde tanımlar:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

_ATL_DISABLE_NO_VTABLE tanımlamazsanız için ATL_NO_VTABLE makro genişler `declspec(novtable)`. Kullanarak `declspec(novtable)`bir sınıfta sınıf oluşturucusu ve yıkıcısı başlatıldı bildirimi vtable işaretçi engeller. Projenizi yapılandırdığınızda, bağlayıcı vtable ve tüm işlevleri vtable işaret ettiği ortadan kaldırır.

ATL_NO_VTABLE, kullanmanız gerekir ve dolayısıyla `declspec(novtable)`, doğrudan oluşturulabilir olmayan taban sınıfına sahip. Değil kullanmalısınız `declspec(novtable)` projenizde, en çok türetilen sınıf ile çünkü bu sınıf (genellikle [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), veya [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) projeniz için vtable işaretçi başlatır.

Sanal işlevler kullanan herhangi bir nesnenin oluşturucudan çağırmamalıdır `declspec(novtable)`. Bu çağrılar için taşımalısınız [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) yöntemi.

Kullanıp emin değilseniz `declspec(novtable)` değiştiricisi, bir sınıf tanımından ATL_NO_VTABLE makrosu kaldırabilir veya genel olarak belirterek devre dışı

```
#define _ATL_DISABLE_NO_VTABLE
```

Stdafx.h öğesinde önce diğer tüm ATL üstbilgi dosyalarını dahil edilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ Proje Türleri](../../ide/visual-cpp-project-types.md)<br/>
[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
