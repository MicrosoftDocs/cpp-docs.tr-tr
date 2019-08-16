---
title: Varsayılan (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: 291e16ad0967acd1869874fcc9fa6eb5529e4b44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501689"
---
# <a name="default-c"></a>default (C++)

Bir coclass içinde tanımlanan özel veya dispınterface 'in varsayılan programlama arabirimini temsil ettiğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>Parametreler

*arabirimi1*<br/>
**Varsayılan** öznitelik ile tanımlanmış sınıfa dayalı bir nesne oluşturan ortamlar için kullanılabilir hale getirilen varsayılan arabirim.

Varsayılan arabirim belirtilmemişse, kaynak olmayan bir arabirimin ilk oluşumu varsayılan olarak kullanılır.

*interface2*<br/>
Seçim Varsayılan kaynak arabirimi. Bu arabirimi [kaynak](source-cpp.md) özniteliğiyle de belirtmeniz gerekir.

Varsayılan kaynak arabirim belirtilmemişse, ilk kaynak arabirim varsayılan olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

**Varsayılan** C++ öznitelik [varsayılan](/windows/win32/Midl/default) MIDL özniteliğiyle aynı işlevselliğe sahiptir. **Varsayılan** öznitelik [Case](case-cpp.md) özniteliğiyle de kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki kod, varsayılan programlama arabirimi olarak belirtmek `ICustomDispatch` için bir coclass 'ın tanımında varsayılan olarak nasıl kullanıldığını gösterir:

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

[Kaynak](source-cpp.md) özniteliğinin Ayrıca **varsayılan**olarak nasıl kullanılacağına ilişkin bir örneği de vardır.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**, veri üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** ( **sınıfa** veya **yapıya**uygulandığında)|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[coclass](coclass.md)