---
title: ATL projesi için derleyici Iyileştirmesi belirtme
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: c3b00823cb33be952451c3cc9e370c99140acc3c
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630609"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL projesi için derleyici Iyileştirmesi belirtme

Varsayılan olarak, [atl Denetim SIHIRBAZı](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE makrosu ile yeni sınıflar oluşturur ve aşağıdaki gibi:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL daha sonra _ATL_NO_VTABLE öğesini şu şekilde tanımlar:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

_ATL_DISABLE_NO_VTABLE tanımlayamazsınız, ATL_NO_VTABLE makrosu olarak `declspec(novtable)`genişletilir. Bir `declspec(novtable)`sınıf bildiriminde kullanılması, vtable işaretçisinin sınıf oluşturucusunda ve yıkıcısında başlatılmasını önler. Projenizi oluşturduğunuzda bağlayıcı, vtable ' ı ve vtable 'ın işaret ettiği tüm işlevleri ortadan kaldırır.

ATL_NO_VTABLE ve sonuç `declspec(novtable)`olarak, yalnızca doğrudan creatable olmayan temel sınıflar ile birlikte kullanmanız gerekir. Bu sınıf (genellikle `declspec(novtable)` [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md)veya [CComPolyObject](../../atl/reference/ccompolyobject-class.md)), projeniz için vtable işaretçisini başlattığında, projenizde en fazla türetilmiş sınıfla kullanmanız gerekir.

Tarafından kullanılan `declspec(novtable)`herhangi bir nesnenin oluşturucusundan sanal işlevleri çağırmamalıdır. Bu çağrıları [Finalyapýsý](ccomobjectrootex-class.md#finalconstruct) yöntemine taşımalısınız.

`declspec(novtable)` Değiştiricisini kullanmanız gerekip gerekmediğini bilmiyorsanız, herhangi bir sınıf tanımından ATL_NO_VTABLE makrosunu kaldırabilir veya şunu belirterek genel olarak devre dışı bırakabilirsiniz

```
#define _ATL_DISABLE_NO_VTABLE
```

diğer tüm ATL üstbilgi dosyaları dahil etmeden önce, *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) içinde.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[C++Visual Studio 'da proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
