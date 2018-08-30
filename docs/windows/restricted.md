---
title: kısıtlı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e8d226f508f5f5e8c717bd671413f21377c0ae01
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202296"
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

*Arabirimleri*  
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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Arabirim Öznitelikleri](../windows/interface-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  