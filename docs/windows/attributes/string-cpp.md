---
title: dize (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: e1b528fb922a15655de403c6099ee1d36e2fb3de
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023938"
---
# <a name="string-c"></a>string (C++)

Bildiren tek boyutlu **char**, **wchar_t**, `byte` (veya eşdeğer) dizi ya da böyle bir dizinin işaretçisi gerekir kabul bir dize.

## <a name="syntax"></a>Sözdizimi

```cpp
[string]
```

## <a name="remarks"></a>Açıklamalar

**Dize** C++ özniteliği ile aynı işlevlere sahip [dize](/windows/desktop/Midl/string) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **dize** bir arabirimde ve bir tür tanımı:

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
|**Uygulandığı öğe:**|Dizi veya işaretçiyi bir dizi, arabirimi parametreyi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Dizi Öznitelikleri](array-attributes.md)<br/>
[dışarı aktar](export.md)