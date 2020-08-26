---
title: Case (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: e1d3c113c42be99a8475c5a667b7ea6ed9583d92
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838912"
---
# <a name="case-c"></a>durum (C++)

İçinde [switch_type](switch-type.md) özniteliğiyle kullanılır **`union`** .

## <a name="syntax"></a>Söz dizimi

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parametreler

*deeri*<br/>
İşleme sağlamak istediğiniz olası bir giriş değeri. **Değer** türü aşağıdaki türlerden biri olabilir:

- **`int`**

- **`char`**

- `boolean`

- **`enum`**

ya da böyle bir tür tanımlayıcı.

## <a name="remarks"></a>Açıklamalar

**Case** C++ özniteliği, **Case** MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bu öznitelik yalnızca [switch_type](switch-type.md) özniteliğiyle birlikte kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki kod **Case** özniteliğinin bir kullanımını gösterir:

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`** Veya üyesi**`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
