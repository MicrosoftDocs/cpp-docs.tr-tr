---
title: helpstringcontext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 49fada071661bd647e012bfdfac2aeedabba68fa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206608"
---
# <a name="helpstringcontext"></a>helpstringcontext

Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstringcontext(
   contextID
) ]
```

### <a name="parameters"></a>Parametreler

*Contextıd*  
Bir 32-bit Yardım bağlamı tanımlayıcıda **yardımcı** dosya.

## <a name="remarks"></a>Açıklamalar

**Helpstringcontext** C++ özniteliği ile aynı işlevlere sahip [helpstringcontext](/windows/desktop/Midl/helpstringcontext) ODL özniteliği.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object,
   helpstring("help string"),
   helpstringcontext(1),
   uuid="11111111-1111-1111-1111-111111111111"
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

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Arabirim Öznitelikleri](../windows/interface-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  
[Modülü](../windows/module-cpp.md)  