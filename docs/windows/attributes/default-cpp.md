---
description: 'Daha fazla bilgi edinin: default (C++)'
title: Varsayılan (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: 83c4a17f513db755395ed978d57c9c6f01f84ca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333010"
---
# <a name="default-c"></a>default (C++)

Bir coclass içinde tanımlanan özel veya dispınterface 'in varsayılan programlama arabirimini temsil ettiğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>Parametreler

*arabirimi1*<br/>
Özniteliği ile tanımlanmış sınıfa göre bir nesne oluşturan ortamlar için kullanılabilir hale getirilen varsayılan arabirim **`default`** .

Varsayılan arabirim belirtilmemişse, kaynak olmayan bir arabirimin ilk oluşumu varsayılan olarak kullanılır.

*interface2*<br/>
Seçim Varsayılan kaynak arabirimi. Bu arabirimi [kaynak](source-cpp.md) özniteliğiyle de belirtmeniz gerekir.

Varsayılan kaynak arabirim belirtilmemişse, ilk kaynak arabirim varsayılan olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

**`default`** C++ özniteliği, [varsayılan](/windows/win32/Midl/default) MIDL özniteliğiyle aynı işlevselliğe sahiptir. **`default`** Özniteliği [Case](case-cpp.md) özniteliğiyle de kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki kod, **`default`** `ICustomDispatch` Varsayılan programlama arabirimi olarak belirtmek için bir coclass 'ın tanımında nasıl kullanıldığını gösterir:

```cpp
// cpp_attr_ref_default.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]
__interface IDual {
   HRESULT Dual([in] long l, [out, retval] long *pLong);
};

[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]
__interface ICustomDispatch : public IDispatch {
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);
};

[   coclass, default(ICustomDispatch), source(IDual), uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")
]
class CClass : public ICustom, public IDual, public ICustomDispatch {
   HRESULT Custom(long l, long *pLong) { return(S_OK); }
   HRESULT Dual(long l, long *pLong) { return(S_OK); }
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }
};

int main() {
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch
   CClass *pClass = new CClass;

   long llong;

   pClass->custom(1, &llong);
   pClass->dual(1, &llong);
   pClass->dispinterface(1, &llong);
   pClass->dispatch(1, &llong);

   delete pClass;
#endif
   return(0);
}
```

[Kaynak](source-cpp.md) özniteliği, öğesinin nasıl kullanılacağına ilişkin bir örnek de içerir **`default`** .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , veri üyesi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** (veya öğesine uygulandığında **`class`** **`struct`** )|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[coclass](coclass.md)
