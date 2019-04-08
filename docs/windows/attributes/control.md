---
title: Denetim (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.control
helpviewer_keywords:
- Control attribute
ms.assetid: 3d046bb2-4afe-4cb8-a762-233b296e1975
ms.openlocfilehash: 223acf774d1cc90d84aed2d0d0c8cb59fc778fa1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034718"
---
# <a name="control"></a> denetimi

Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[control]
```

## <a name="remarks"></a>Açıklamalar

**Denetimi** özniteliği gelir [coclass'ı](coclass.md) özniteliği. **Denetimi** C++ özniteliği ile aynı işlevlere sahip [denetimi](/windows/desktop/Midl/control) MIDL özniteliği.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_control.cpp
// compile with: /LD
#include <windows.h>
[module(name="Test", control=true)];

[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[coclass, control, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CTest : public ICustom {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)