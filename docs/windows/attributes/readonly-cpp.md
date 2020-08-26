---
title: ReadOnly (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: ea2b0a46d34fc415a3b9eca97b92cda764fc7d42
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839809"
---
# <a name="readonly-c"></a>readonly (C++)

Bir veri üyesine atamayı yasaklar.

## <a name="syntax"></a>Syntax

```cpp
[readonly]
```

## <a name="remarks"></a>Açıklamalar

**ReadOnly** C++ özniteliği, [salt okunur](/windows/win32/Midl/readonly) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

Bir yöntem parametresinin değiştirilmesini yasaklamak istiyorsanız [ın](in-cpp.md) özniteliğini kullanın.

## <a name="example"></a>Örnek

Aşağıdaki kod **ReadOnly** özniteliğinin kullanımını gösterir:

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Veri üyesi öznitelikleri](data-member-attributes.md)
