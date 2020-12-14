---
description: 'Daha fazla bilgi edinin: Case (C++)'
title: Case (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: d851e662387425ca94cc6a03877babf011c7028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247442"
---
# <a name="case-c"></a>durum (C++)

İçinde [switch_type](switch-type.md) özniteliğiyle kullanılır **`union`** .

## <a name="syntax"></a>Sözdizimi

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parametreler

*değer*<br/>
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
|**Şunlara uygulanır**|**`class`** Veya üyesi **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
