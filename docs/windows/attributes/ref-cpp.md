---
title: başvuru (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ref
helpviewer_keywords:
- ref attribute
ms.assetid: 67e82d3e-07d9-4ef8-bf2b-0a4491d12557
ms.openlocfilehash: c22d04f7a799ea720fb7d69ffc1aa21ddf9db55c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468438"
---
# <a name="ref-c"></a>ref (C++)

Bir başvuru işaretçi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ref]
```

## <a name="remarks"></a>Açıklamalar

**Ref** C++ özniteliği ile aynı işlevlere sahip [ref](/windows/desktop/Midl/ref) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **ref** özniteliği:

```cpp
// cpp_attr_ref_ref.cpp
// compile with: /LD
#include <windows.h>
[module(name="ATLFIRELib")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1), unique] char * GetFirstName([in, ref] char * pszFullName );
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**TypeDef**, parametre arabirim, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)