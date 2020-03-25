---
title: kısıtlanmış (C++ com özniteliği)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: a47c56673e19f891b24ff433b9c614804f0bd51c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166373"
---
# <a name="restricted"></a>kısıtlı

Bir Module, Interface veya dispınterface üyesinin rastgele çağrılamıyor olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Parametreler

*arabirimlerdeki*<br/>
Bir COM nesnesi üzerinde rastgele çağrılmayan bir veya daha fazla arabirim. Bu parametre yalnızca bir sınıfa uygulandığında geçerlidir.

## <a name="remarks"></a>Açıklamalar

**Restricted** C++ özniteliği, [kısıtlı](/windows/win32/Midl/restricted) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **Kısıtlanmış** özniteliği nasıl kullanacağınızı gösterir:

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim yöntemi, **arabirim**, **sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass** ( **sınıfa** veya **yapıya**uygulandığında)|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)
