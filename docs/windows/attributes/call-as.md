---
title: call_as (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: 755741faec6c0ba702d372ca8dee486edcb72ef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167347"
---
# <a name="call_as"></a>call_as

Uzak işlev çağrıldığında yerel işlev çağrıldığında [Yerel](local-cpp.md) bir işlevin uzak bir işlevle eşleştirilmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Parametreler

*çalışmayacaktır*<br/>
Uzak bir işlev çağrıldığında çağrılmasını istediğiniz yerel işlev.

## <a name="remarks"></a>Açıklamalar

**Call_as** C++ özniteliği [call_as](/windows/win32/Midl/call-as) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, Uzaktan erişilebilir olmayan bir işlevi (`f1`) uzaktan erişilebilen bir işleve (`Remf1`) eşlemek için **call_as** nasıl kullanabileceğinizi gösterir:

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[local](local-cpp.md)
