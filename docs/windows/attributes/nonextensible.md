---
description: 'Daha fazla bilgi edinin: Genişletilebilir olmayan'
title: Genişletilebilir olmayan (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: dfb0eda0fc8c6de367ee29ec3786750ba40395ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327442"
---
# <a name="nonextensible"></a>nonextensible

`IDispatch`Uygulamanın yalnızca arabirim açıklamasında listelenen özellikleri ve yöntemleri içerdiğini belirtir ve çalışma zamanında ek üyelerle birlikte genişletilemez.

## <a name="syntax"></a>Syntax

```cpp
[nonextensible]
```

## <a name="remarks"></a>Açıklamalar

**Genişletilebilir olmayan** C++ özniteliği, [Genişletilebilir](/windows/win32/Midl/nonextensible) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

**Genişletilebilir olmayan** kullanımı, [oleautomation](oleautomation.md) özniteliğini de gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **genişletilebilen olmayan** özniteliğin bir kullanımını gösterir:

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arayüz**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|`dual` ve `oleautomation` veya `dispinterface`|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
