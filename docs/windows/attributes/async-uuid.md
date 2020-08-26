---
title: async_uuid (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: cb0abdcedc26c5ffe197e52d5da4fbad1ec516d2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836250"
---
# <a name="async_uuid"></a>async_uuid

Bir COM arabiriminin hem zaman uyumlu hem de zaman uyumsuz sürümlerini tanımlamak için MıDL derleyicisini yönlendiren UUID 'yi belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[async_uuid (uuid)]
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
Arabirimin sürümünü tanımlayan bir UUID.

## <a name="remarks"></a>Açıklamalar

**Async_uuid** C++ özniteliği, [async_uuid](/windows/win32/Midl/async-uuid) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_async_uuid.cpp
// compile with: /LD
#include <Windows.h>
[module(name="Test")];
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|`interface`|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|**Dual**, **dispınterface**|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
