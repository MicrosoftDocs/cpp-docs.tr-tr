---
title: Genişletilebilir olmayan (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: 01f89c4a06a8e90fd6a539fa5a5a85ebb8067d40
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833042"
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
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`dual` ve `oleautomation` veya `dispinterface`|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
