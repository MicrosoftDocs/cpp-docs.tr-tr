---
title: pragma (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: e5683a6f52eccf9eae7c29010849a148e506b286
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836175"
---
# <a name="pragma"></a>pragma

Belirtilen dizeyi, tırnak işaretlerinin kullanımı olmadan oluşturulan. IDL dosyasına yayar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Parametreler

*pragma_statement*<br/>
Oluşturulan. IDL dosyasına gitmek istediğiniz pragma.

## <a name="remarks"></a>Açıklamalar

**Pragma** C++ özniteliği, [pragma](/windows/win32/Midl/pragma) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)
