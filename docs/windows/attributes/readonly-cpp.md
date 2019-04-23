---
title: salt okunur (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 7eea071b62130c65fbb46ebc8827fc2b428c4c0c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036923"
---
# <a name="readonly-c"></a>readonly (C++)

Bir veri üyesine atama yasaklar.

## <a name="syntax"></a>Sözdizimi

```cpp
[readonly]
```

## <a name="remarks"></a>Açıklamalar

**Salt okunur** C++ özniteliği ile aynı işlevlere sahip [salt okunur](/windows/desktop/Midl/readonly) MIDL özniteliği.

Bir yöntem parametresi değiştirilmesini engellemek istiyorsanız, ardından kullanmak [içinde](in-cpp.md) özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir kullanımını göstermektedir. **salt okunur** özniteliği:

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
|**İçin geçerlidir**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)