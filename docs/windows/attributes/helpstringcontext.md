---
title: helpstringcontext (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: 9e089c210ad52d8ee07291c174a151f5077ae074
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830988"
---
# <a name="helpstringcontext"></a>helpstringcontext

Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞINI belirtir.

## <a name="syntax"></a>Söz dizimi

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **interface**, Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[birimi](module-cpp.md)
