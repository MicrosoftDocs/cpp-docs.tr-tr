---
title: transmit_as (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.transmit_as
helpviewer_keywords:
- transmit_as attribute
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
ms.openlocfilehash: e432d1a8f39cbc5e12f192ed7b07c29421bc403e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032108"
---
# <a name="transmitas"></a>transmit_as

İstemci ve sunucu uygulamaları işlemek, sunulan bir türü iletilen türüyle ilişkilendirmek için derleyicinin sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ transmit_as(type) ]
```

### <a name="parameters"></a>Parametreler

*type*<br/>
İstemci ve sunucu arasında aktarılan veri türünü belirtir.

## <a name="remarks"></a>Açıklamalar

**Transmit_as** C++ özniteliği ile aynı işlevlere sahip [transmit_as](/windows/desktop/Midl/transmit-as) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir kullanımını göstermektedir. **transmit_as** özniteliği:

```cpp
// cpp_attr_ref_transmit_as.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export] typedef struct _TREE_NODE_TYPE {
unsigned short data;
struct _TREE_NODE_TYPE * left;
struct _TREE_NODE_TYPE * right;
} TREE_NODE_TYPE;

[export] struct PACKED_NODE {
   unsigned short data;   // same as normal node
   int index;   // array index of parent
};

// A left node recursive built array of
// the nodes in the tree.  Can be unpacked with
// that knowledge
[export] typedef struct _TREE_XMIT_TYPE {
   int count;
   [size_is(count)] PACKED_NODE node[];
} TREE_XMIT_TYPE;

[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**tür tanımı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)