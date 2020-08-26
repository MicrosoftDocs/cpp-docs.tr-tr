---
title: dize (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 119e0aa60d123324c60825a9418e0b8c93696c5f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845386"
---
# <a name="string-c"></a>string (C++)

Tek boyutlu **`char`** , **`wchar_t`** , `byte` (veya eşdeğer) dizinin ya da bu tür bir dizi işaretçisinin bir dize olarak değerlendirilmesinin gerektiği anlamına gelir.

## <a name="syntax"></a>Syntax

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Array, Interface parametresi, Interface yöntemi için dizi veya işaretçi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Dizi öznitelikleri](array-attributes.md)<br/>
[işlemi](export.md)
