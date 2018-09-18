---
title: ATL projesinde derleyici iyileştirmesi belirtme | Microsoft Docs
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
ms.openlocfilehash: 622c0720f55e638d6640094f095e59d2d5e5f931
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069345"
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

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ Proje Türleri](../../ide/visual-cpp-project-types.md)<br/>
[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

