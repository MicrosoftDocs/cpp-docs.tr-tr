---
title: defaultvtable (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 40f901345601193db9752ea6c6dca980ded0625d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579939"
---
# <a name="defaultvtable"></a>defaultvtable

Varsayılan vtable arabirim bir COM nesnesi için bir arabirim tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>Parametreler

*interface*<br/>
COM nesnesi için varsayılan vtable olmasını istediğiniz belirtilen arabirim.

## <a name="remarks"></a>Açıklamalar

**Defaultvtable** C++ özniteliği ile aynı işlevlere sahip [defaultvtable](/windows/desktop/Midl/defaultvtable) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod öznitelikleri kullanan bir sınıf üzerinde gösterir. **defaultvtable** bir varsayılan arabirim belirtmek için:

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)