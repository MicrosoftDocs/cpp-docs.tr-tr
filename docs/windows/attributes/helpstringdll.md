---
title: helpstringdll (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 72f5926018e3ac7ec4770f83d7a2c3438b67d861
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409544"
---
# <a name="helpstringdll"></a>helpstringdll

Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Parametreler

*string*<br/>
Belge dize arama gerçekleştirmek için kullanılacak DLL.

## <a name="remarks"></a>Açıklamalar

**Helpstringdll** C++ özniteliği ile aynı işlevlere sahip [helpstringdll](/windows/desktop/Midl/helpstringdll) MIDL özniteliği.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **arabirimi**, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)