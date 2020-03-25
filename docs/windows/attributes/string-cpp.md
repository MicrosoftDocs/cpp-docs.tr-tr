---
title: dize (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 96d5e609130b34a4a5f35109ce691c2de470e537
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166172"
---
# <a name="string-c"></a>string (C++)

Tek boyutlu bir **char**, **wchar_t**, `byte` (veya eşdeğeri) dizisinin veya bu dizi işaretçisinin bir dize olarak değerlendirilmesinin gerektiğini gösterir.

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
|**Uygulama hedefi**|Array, Interface parametresi, Interface yöntemi için dizi veya işaretçi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Dizi Öznitelikleri](array-attributes.md)<br/>
[export](export.md)
