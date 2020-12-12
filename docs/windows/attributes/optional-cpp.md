---
description: 'Daha fazla bilgi edinin: isteğe bağlı (C++)'
title: isteğe bağlı (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: 70ae49854a496aad35edc87bdd1ac5facb899448
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329725"
---
# <a name="optional-c"></a>isteğe bağlı (C++)

Bir üye işlevi için isteğe bağlı bir parametre belirtir.

## <a name="syntax"></a>Syntax

```cpp
[optional]
```

## <a name="remarks"></a>Açıklamalar

**İsteğe bağlı** C++ özniteliği, [isteğe bağlı](/windows/win32/Midl/optional) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **isteğe bağlı** olarak nasıl kullanılabileceğini göstermektedir:

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)
