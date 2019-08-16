---
title: dize (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 978f1f546c0df8de4ff167ddf5ddf724feb31b6e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514012"
---
# <a name="string-c"></a>string (C++)

Tek boyutlu bir **char**, **wchar_t**, `byte` (veya eşdeğeri) dizisinin veya bu dizi işaretçisinin bir dize olarak değerlendirilmesinin gerektiği anlamına gelir.

## <a name="syntax"></a>Sözdizimi

```cpp
[string]
```

## <a name="remarks"></a>Açıklamalar

**String** C++ özniteliği, MIDL özniteliğiyle aynı işlevselliğe sahiptir [](/windows/win32/Midl/string) .

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
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Dizi Öznitelikleri](array-attributes.md)<br/>
[export](export.md)