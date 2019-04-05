---
title: pragma (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 159e1570c2bde07bb4df8fa904a519e8e0018a6a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041195"
---
# <a name="pragma"></a>pragması

Belirtilen dizeyi tırnak işaretleri kullanmanıza gerek kalmadan oluşturulan .idl dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Parametreler

*pragma_statement*<br/>
Oluşturulan .idl dosyasına gitmek istiyorsanız pragması.

## <a name="remarks"></a>Açıklamalar

**Pragma** C++ özniteliği ile aynı işlevlere sahip [pragma](/windows/desktop/Midl/pragma) MIDL özniteliği.

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
|**Uygulandığı öğe:**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)