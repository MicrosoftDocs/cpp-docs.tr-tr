---
description: 'Hakkında daha fazla bilgi edinin: call_as'
title: call_as (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: de407da1401479327185c6133c625d61e1e221cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247455"
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

**Call_as** C++ özniteliği, [call_as](/windows/win32/Midl/call-as) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, Uzaktan erişilebilir olmayan bir işlevi () uzaktan erişilebilen bir işleve () eşlemek için **call_as** nasıl kullanabileceğinizi gösterir `f1` `Remf1` :

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Interface yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Yerel](local-cpp.md)
