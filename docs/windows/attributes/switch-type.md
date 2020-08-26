---
title: switch_type (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: 0c39aa442c9d4eaf3a482e411cda762fe0cc34b3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838535"
---
# <a name="switch_type"></a>switch_type

UNION ayrımınant olarak kullanılan değişkenin türünü tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Anahtar türü, bir tamsayı, karakter, Boole veya numaralandırma türü olabilir.

## <a name="remarks"></a>Açıklamalar

**Switch_type** C++ özniteliği, [switch_type](/windows/win32/Midl/switch-type) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

C++ öznitelikleri, [kapsüllenmiş birleşimleri](/windows/win32/Midl/encapsulated-unions)desteklemez. [Kapsüllenmiş olmayan birleşimler](/windows/win32/Midl/nonencapsulated-unions) yalnızca aşağıdaki biçimde desteklenir:

```cpp
// cpp_attr_ref_switch_type.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];
[ export ]
struct SizedValue2 {
   [switch_type("char"), switch_is(kind)] union {
      [case(1), string]
         wchar_t* wval;
      [default, string]
         char* val;
   };
   char kind;
};
```

## <a name="example"></a>Örnek

**Switch_type**örnek bir kullanımı için bkz. [durum](case-cpp.md) örneği.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`typedef`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[işlemi](export.md)
