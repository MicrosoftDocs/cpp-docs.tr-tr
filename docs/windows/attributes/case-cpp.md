---
title: Case (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: da72fff3bb600b5db2fba0ecdfe9c6a768836f3c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167348"
---
# <a name="case-c"></a>durum (C++)

Bir **birleşimdeki** [switch_type](switch-type.md) özniteliğiyle birlikte kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parametreler

*value*<br/>
İşleme sağlamak istediğiniz olası bir giriş değeri. **Değer** türü aşağıdaki türlerden biri olabilir:

- `int`

- `char`

- `boolean`

- `enum`

ya da böyle bir tür tanımlayıcı.

## <a name="remarks"></a>Açıklamalar

**Case** C++ özniteliği **Case** MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bu öznitelik yalnızca [switch_type](switch-type.md) özniteliğiyle birlikte kullanılır.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Bir **sınıfın** veya **yapının** üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
