---
title: ReadOnly (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 415ad5e33de3132e055e53178e6e65d411f169f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214610"
---
# <a name="readonly-c"></a>readonly (C++)

Bir veri üyesine atamayı yasaklar.

## <a name="syntax"></a>Sözdizimi

```cpp
[readonly]
```

## <a name="remarks"></a>Açıklamalar

**ReadOnly** C++ özniteliği, [ReadOnly](/windows/win32/Midl/readonly) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)
