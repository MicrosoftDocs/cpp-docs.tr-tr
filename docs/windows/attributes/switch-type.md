---
title: switch_type (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7aa11ada46f74c3e2a7293c65151b1f1ede7255e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080097"
---
# <a name="switchtype"></a>switch_type

Birleşim discriminant kullanılan değişkenin türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Anahtar türü, bir tamsayı, karakter, Boole veya numaralandırma türü olabilir.

## <a name="remarks"></a>Açıklamalar

**Switch_type** C++ özniteliği ile aynı işlevlere sahip [switch_type](/windows/desktop/Midl/switch-type) MIDL özniteliği.

C++ öznitelikleri desteklemiyor [birleşimler kapsüllenmiş](/windows/desktop/Midl/encapsulated-unions). [Nonencapsulated birleşimler](/windows/desktop/Midl/nonencapsulated-unions) yalnızca şu biçimde desteklenir:

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

Bkz: [çalışması](case-cpp.md) örnek kullanımını örneğin **switch_type**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**tür tanımı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)