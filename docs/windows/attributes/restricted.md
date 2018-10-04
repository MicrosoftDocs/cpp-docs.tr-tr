---
title: kısıtlı (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1dfaed296242d2a0fc341c2ff5f137a08d753e71
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789847"
---
# <a name="restricted"></a>kısıtlı

Bir modül, arabirim veya dispinterface üyesi rasgele çağrılamaz belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Parametreler

*Arabirimleri*<br/>
Rasgele bir COM nesnesi üzerinde çağrılamaz bir veya daha fazla arabirim. Bu parametre, yalnızca bir sınıfa uygulandığında geçerlidir.

## <a name="remarks"></a>Açıklamalar

**Kısıtlı** C++ özniteliği ile aynı işlevlere sahip [kısıtlı](/windows/desktop/Midl/restricted) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **kısıtlı** özniteliği:

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirim yöntemini **arabirimi**, **sınıfı**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass'ı** (uygulandığında **sınıfı** veya **yapı**)|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)  