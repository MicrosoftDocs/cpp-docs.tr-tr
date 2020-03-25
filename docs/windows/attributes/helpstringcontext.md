---
title: helpstringcontext (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: 339d65070efe8bf2dafae2cf76e92c75a1bebc18
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168155"
---
# <a name="helpstringcontext"></a>helpstringcontext

Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞINI belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Parametreler

*ContextId*<br/>
**Yardım** dosyasında 32 bitlik bir yardım bağlamı tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

**Helpstringcontext** C++ özniteliği, [helpstringcontext](/windows/win32/Midl/helpstringcontext) ODL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**Class**, **Interface**, Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[module](module-cpp.md)
