---
title: helpstringcontext (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00b0e7824de3c6977bd641e7016e3efc5acdcfa1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067378"
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
|**İçin geçerlidir**|**sınıf**, **arabirimi**, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[module](module-cpp.md)