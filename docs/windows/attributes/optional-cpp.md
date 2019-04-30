---
title: İsteğe bağlı (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: bc6422ff652cfaba5fa71285294b93c1f0e8990e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407594"
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
|**İçin geçerlidir**|Parametre arabirimi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)