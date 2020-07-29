---
title: dize (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 68708cce2e167c6f40b461d52861fe4ed82be867
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213820"
---
# <a name="string-c"></a>string (C++)

Tek boyutlu **`char`** , **`wchar_t`** , `byte` (veya eşdeğer) dizinin ya da bu tür bir dizi işaretçisinin bir dize olarak değerlendirilmesinin gerektiği anlamına gelir.

## <a name="syntax"></a>Sözdizimi

```cpp
[string]
```

## <a name="remarks"></a>Açıklamalar

**String** C++ özniteliği [, MIDL](/windows/win32/Midl/string) özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir arabirimde ve bir typedef üzerinde nasıl **dize** kullanacağınızı gösterir:

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|Array, Interface parametresi, Interface yöntemi için dizi veya işaretçi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Dizi öznitelikleri](array-attributes.md)<br/>
[işlemi](export.md)
