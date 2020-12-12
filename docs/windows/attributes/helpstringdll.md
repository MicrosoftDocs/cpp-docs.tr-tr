---
description: 'Daha fazla bilgi edinin: helpstringdll'
title: helpstringdll (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 13a64f7f98a9d63e6a176911caad1246ad64af75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148804"
---
# <a name="helpstringdll"></a>helpstringdll

Belge dizesi aramasını (Yerelleştirme) gerçekleştirmek için kullanılacak DLL 'in adını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Parametreler

*string*<br/>
Belge dizesi aramasını gerçekleştirmek için kullanılacak DLL.

## <a name="remarks"></a>Açıklamalar

**Helpstringdll** C++ özniteliği, [helpstringdll](/windows/win32/Midl/helpstringdll) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **interface**, Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)
