---
description: 'Şu konuda daha fazla bilgi edinin: defaultvtable'
title: defaultvtable (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 9cabb2e3487788b56a37e7380ef9a9e08cf2bc67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122154"
---
# <a name="defaultvtable"></a>defaultvtable

Bir COM nesnesi için varsayılan vtable arabirimi olarak bir arabirimi tanımlar.

## <a name="syntax"></a>Sözdizimi

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
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
