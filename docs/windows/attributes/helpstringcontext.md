---
title: helpstringcontext (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: a6df5b63291fbc54d6c12a116fccd8372e8ced9a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026116"
---
# <a name="helpstringcontext"></a>helpstringcontext

Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Parametreler

*Contextıd*<br/>
Bir 32-bit Yardım bağlamı tanımlayıcıda **yardımcı** dosya.

## <a name="remarks"></a>Açıklamalar

**Helpstringcontext** C++ özniteliği ile aynı işlevlere sahip [helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL özniteliği.

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
|**Uygulandığı öğe:**|**sınıf**, **arabirimi**, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[modül](module-cpp.md)