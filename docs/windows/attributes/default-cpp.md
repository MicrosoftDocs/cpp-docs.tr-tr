---
title: Varsayılan (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: c6448b00fef50a7654816a2c39af2943db12d314
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024588"
---
# <a name="default-c"></a>default (C++)

Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>Parametreler

*arabirimi1*<br/>
Bir nesne oluşturmak, komut dosyası ortamlar için kullanılabilir hale getirilir varsayılan arabirimi ile tanımlanan sınıfın temel **varsayılan** özniteliği.

Herhangi bir varsayılan arabirim belirtilirse, bir kaynak arabirimi ilk geçtiği varsayılan olarak kullanılır.

*interface2*<br/>
(İsteğe bağlı) Varsayılan kaynak arabirimi. Bu arabirim ile de belirtmeniz gerekir [kaynak](source-cpp.md) özniteliği.

İlk kaynak arabirimi, hiçbir varsayılan kaynak arabirimi belirtilmezse, varsayılan olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

**Varsayılan** C++ özniteliği ile aynı işlevlere sahip [varsayılan](/windows/desktop/Midl/default) MIDL özniteliği. **Varsayılan** özniteliği ile kullanılan ayrıca [çalışması](case-cpp.md) özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kodda gösterildiği nasıl **varsayılan** coclass'ı tanımını belirtmek için kullanılan `ICustomDispatch` varsayılan programlama arabirimi olarak:

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

[Kaynak](source-cpp.md) ayrıca özniteliğinin nasıl kullanılacağına ilişkin bir örnek **varsayılan**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapı**, veri üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass'ı** (uygulandığında **sınıfı** veya **yapı**)|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[coclass](coclass.md)