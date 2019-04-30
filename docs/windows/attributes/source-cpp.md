---
title: Kaynak (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: 699ea64de49a4383bc8fb62b2f3b2133d7c496c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407191"
---
# <a name="source-c"></a>kaynak (C++)

Sınıfta, COM nesnesinin kaynak arabirimleri için bağlantı noktalarını belirtir. Özellik veya yöntem üyesi bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Parametreler

*Arabirimleri*<br/>
Kaynak uyguladığınızda belirttiğiniz bir veya daha fazla arabirim bir sınıfa öznitelik. Kaynak bir özellik veya yöntem uygulandığında, bu parametre kullanılmaz.

## <a name="remarks"></a>Açıklamalar

**Kaynak** C++ özniteliği ile aynı işlevlere sahip [kaynak](/windows/desktop/Midl/source) MIDL özniteliği.

Kullanabileceğiniz [varsayılan](default-cpp.md) nesnenin varsayılan kaynak arabirimi belirtmek için özniteliği.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapı**, **arabirimi**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|`coclass` (sınıf veya yapı için uygulandığında)|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[coclass](coclass.md)