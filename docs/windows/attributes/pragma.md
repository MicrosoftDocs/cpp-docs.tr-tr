---
title: pragma (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 56b1aa4bf445095b86a1ea6792bfc78f45266e9a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166490"
---
# <a name="pragma"></a>pragması

Belirtilen dizeyi, tırnak işaretlerinin kullanımı olmadan oluşturulan. IDL dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)
