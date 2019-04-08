---
title: call_as (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: a0051cdca6673800b37d5733c0b849da24010fcb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023925"
---
# <a name="callas"></a>call_as

Sağlayan bir [yerel](local-cpp.md) uzak işlev çağrıldığında, yerel işlevin çağrılması, uzak bir işleve eşleştirilecek işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Parametreler

* işlevi*<br/>
Uzak bir işlev çağrıldığında çağrılacak istediğiniz yerel işlev.

## <a name="remarks"></a>Açıklamalar

**Call_as** C++ özniteliği ile aynı işlevlere sahip [call_as](/windows/desktop/Midl/call-as) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir **call_as** nonremotable işlevi eşleştirmek için (`f1`) Uzaktan erişilebilir işlevi (`Remf1`):

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[yerel](local-cpp.md)