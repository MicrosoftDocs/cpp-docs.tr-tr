---
title: switch_type (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: c3a4187c629238fa464a607c0b653f857fa44b6a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513956"
---
# <a name="switch_type"></a>switch_type

UNION ayrımınant olarak kullanılan değişkenin türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Parametreler

*type*<br/>
Anahtar türü, bir tamsayı, karakter, Boole veya numaralandırma türü olabilir.

## <a name="remarks"></a>Açıklamalar

**Switch_type** C++ özniteliği, [switch_type](/windows/win32/Midl/switch-type) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

C++Öznitelikler, [kapsüllenmiş birleşimleri](/windows/win32/Midl/encapsulated-unions)desteklemez. [Kapsüllenmiş olmayan birleşimler](/windows/win32/Midl/nonencapsulated-unions) yalnızca aşağıdaki biçimde desteklenir:

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

Örnek switch_type [](case-cpp.md) örnek kullanımı için bkz. örnek örneği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**genişletiyor**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)