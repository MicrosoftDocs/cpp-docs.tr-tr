---
title: Genişletilebilir olmayan (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: f2947e223d068ea6cc92a41abe19cb7f920112b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514401"
---
# <a name="nonextensible"></a>nonextensible

`IDispatch` Uygulamanın yalnızca arabirim açıklamasında listelenen özellikleri ve yöntemleri içerdiğini belirtir ve çalışma zamanında ek üyelerle birlikte genişletilemez.

## <a name="syntax"></a>Sözdizimi

```cpp
[nonextensible]
```

## <a name="remarks"></a>Açıklamalar

**Genişletilebilir** C++ olmayan öznitelik, [Genişletilebilir](/windows/win32/Midl/nonextensible) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`dual`ve `oleautomation`veya`dispinterface`|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)