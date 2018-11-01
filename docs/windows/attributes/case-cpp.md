---
title: Durum (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: 1ed107b78ea5638d93a773e19de13b4c1fe1036c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648415"
---
# <a name="case-c"></a>durum (C++)

İle kullanılan [switch_type](switch-type.md) özniteliğini bir **birleşim**.

## <a name="syntax"></a>Sözdizimi

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parametreler

*value*<br/>
Olası bir işleme sağlamak istediğiniz değeri girin. Türünü **değer** şu türlerden biri olabilir:

- `int`

- `char`

- `boolean`

- `enum`

veya böyle bir türü bir tanımlayıcı.

## <a name="remarks"></a>Açıklamalar

**Çalışması** C++ özniteliği ile aynı işlevlere sahip **çalışması** MIDL özniteliği. Bu öznitelik yalnızca birlikte kullanılan [switch_type](switch-type.md) özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir kullanımını göstermektedir. **çalışması** özniteliği:

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
|**İçin geçerlidir**|Üye bir **sınıfı** veya **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)