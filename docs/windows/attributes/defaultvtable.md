---
title: defaultvtable (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 6b1d6960a065bf2df46852d3df1ca53d4239f1bc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839497"
---
# <a name="defaultvtable"></a>defaultvtable

Bir COM nesnesi için varsayılan vtable arabirimi olarak bir arabirimi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>Parametreler

*arayüz*<br/>
COM nesnesi için varsayılan vtable 'a sahip olmasını istediğiniz belirtilen arabirim.

## <a name="remarks"></a>Açıklamalar

**Defaultvtable** C++ özniteliği, [defaultvtable](/windows/win32/Midl/defaultvtable) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, varsayılan bir arabirim belirtmek için **defaultvtable** kullanan bir sınıftaki öznitelikleri gösterir:

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
