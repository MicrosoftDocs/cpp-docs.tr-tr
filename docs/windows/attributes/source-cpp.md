---
title: Kaynak (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: f9a1f576e26805c5dd84c2d83cdf3615d0661af3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842773"
---
# <a name="source-c"></a>kaynak (C++)

Bir sınıfında, bağlantı noktaları için COM nesnesinin kaynak arabirimlerini belirtir. Bir özellik veya yöntemde, üyenin bir olay kaynağı olan bir nesne veya DEĞIŞKEN döndürdüğünü gösterir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Parametreler

*arabirimlerdeki*<br/>
Bir sınıfa kaynak özniteliği uyguladığınızda belirttiğiniz bir veya daha fazla arabirim. Bu parametre, kaynak bir özelliğe veya yönteme uygulandığında kullanılmaz.

## <a name="remarks"></a>Açıklamalar

**Kaynak** C++ özniteliği, [kaynak](/windows/win32/Midl/source) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

Bir nesnenin varsayılan kaynak arabirimini belirtmek için [varsayılan](default-cpp.md) özniteliğini kullanabilirsiniz.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`** , **arabirim**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`coclass` (sınıfa veya yapıya uygulandığında)|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[coclass](coclass.md)
