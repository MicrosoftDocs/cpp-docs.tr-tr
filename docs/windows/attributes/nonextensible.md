---
title: nonextensible (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 332f61148ccf8cb5816e8bd347181ac9d130a730
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512456"
---
# <a name="nonextensible"></a>nonextensible

Belirten `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenir ve çalışma zamanında ek üyeleriyle genişletilemez.

## <a name="syntax"></a>Sözdizimi

```cpp
[nonextensible]
```

## <a name="remarks"></a>Açıklamalar

**Nonextensible** C++ özniteliği ile aynı işlevlere sahip [nonextensible](/windows/desktop/Midl/nonextensible) MIDL özniteliği.

Kullanım **nonextensible** ayrıca gerektirir [oleautomation](oleautomation.md) özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod bir kullanımını göstermektedir **nonextensible** özniteliği:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|`dual` ve `oleautomation`, veya `dispinterface`|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)