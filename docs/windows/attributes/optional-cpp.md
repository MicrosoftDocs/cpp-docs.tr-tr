---
title: İsteğe bağlı (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: bc6422ff652cfaba5fa71285294b93c1f0e8990e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032946"
---
# <a name="optional-c"></a>isteğe bağlı (C++)

Bir üye işlev için isteğe bağlı bir parametre belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[optional]
```

## <a name="remarks"></a>Açıklamalar

**İsteğe bağlı** C++ özniteliği ile aynı işlevlere sahip [isteğe bağlı](/windows/desktop/Midl/optional) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kodda gösterildiği nasıl **isteğe bağlı** kullanılabilir:

```cpp
// cpp_attr_ref_optional.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Parametre arabirimi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)