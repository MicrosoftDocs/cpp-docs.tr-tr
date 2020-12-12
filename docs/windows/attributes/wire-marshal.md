---
description: 'Hakkında daha fazla bilgi edinin: wire_marshal'
title: wire_marshal (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.wire_marshal
helpviewer_keywords:
- wire_marshal attribute
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
ms.openlocfilehash: 69e3b85137d656e40cb77f9f75c361495c88f4a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118296"
---
# <a name="wire_marshal"></a>wire_marshal

Uygulamaya özgü veri türü yerine iletim için kullanılacak bir veri türü belirtir.

## <a name="syntax"></a>Syntax

```cpp
[wire_marshal]
```

## <a name="remarks"></a>Açıklamalar

**Wire_marshal** C++ özniteliği, [wire_marshal](/windows/win32/Midl/wire-marshal) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod **wire_marshal** kullanımını gösterir:

```cpp
// cpp_attr_ref_wire_marshal.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export, public] typedef unsigned long _FOUR_BYTE_DATA;

[export] typedef struct _TWO_X_TWO_BYTE_DATA {
   unsigned short low;
   unsigned short high;
} TWO_X_TWO_BYTE_DATA ;

[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`typedef`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)
