---
description: 'Hakkında daha fazla bilgi edinin: ATL projesi için derleyici Iyileştirmesi belirtme'
title: ATL Projesinde Derleyici İyileştirmesi Belirtme
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: d0650cfebdeb74caeb78a0ab4f138f4896865fc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138807"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>ATL Projesinde Derleyici İyileştirmesi Belirtme

Varsayılan olarak, [atl denetim sihirbazı](../../atl/reference/atl-control-wizard.md) ATL_NO_VTABLE makrosu ile yeni sınıflar oluşturur ve aşağıdaki gibi:

```
class ATL_NO_VTABLE CProjName
{
...
};
```

ATL daha sonra _ATL_NO_VTABLE aşağıdaki gibi tanımlar:

```
#ifdef _ATL_DISABLE_NO_VTABLE
#define ATL_NO_VTABLE
#else
#define ATL_NO_VTABLE __declspec(novtable)
#endif
```

_ATL_DISABLE_NO_VTABLE tanımlamadıysanız, ATL_NO_VTABLE makrosu olarak genişletilir `declspec(novtable)` . `declspec(novtable)`Bir sınıf bildiriminde kullanılması, vtable işaretçisinin sınıf oluşturucusunda ve yıkıcısında başlatılmasını önler. Projenizi oluşturduğunuzda bağlayıcı, vtable ' ı ve vtable 'ın işaret ettiği tüm işlevleri ortadan kaldırır.

ATL_NO_VTABLE ve sonuç `declspec(novtable)` olarak, yalnızca doğrudan creatable olmayan temel sınıflar ile birlikte kullanmanız gerekir. `declspec(novtable)`Bu sınıf (genellikle [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md)veya [CComPolyObject](../../atl/reference/ccompolyobject-class.md)), projeniz için vtable işaretçisini başlattığında, projenizde en fazla türetilmiş sınıfla kullanmanız gerekir.

Tarafından kullanılan herhangi bir nesnenin oluşturucusundan sanal işlevleri çağırmamalıdır `declspec(novtable)` . Bu çağrıları [Finalyapýsý](ccomobjectrootex-class.md#finalconstruct) yöntemine taşımalısınız.

Değiştiricisini kullanmanız gerekip gerekmediğini bilmiyorsanız `declspec(novtable)` , herhangi bir sınıf tanımından ATL_NO_VTABLE makrosunu kaldırabilir veya şunu belirterek genel olarak devre dışı bırakabilirsiniz

```
#define _ATL_DISABLE_NO_VTABLE
```

diğer tüm ATL üstbilgi dosyaları dahil etmeden önce, *pch. h* (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) içinde.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C Run-Time kodla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
