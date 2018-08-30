---
title: call_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a5e5d5ddb831c5d4025e729cb27dd3a9e11b3688
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194759"
---
# <a name="callas"></a>call_as

Sağlayan bir [yerel](../windows/local-cpp.md) uzak işlev çağrıldığında, yerel işlevin çağrılması, uzak bir işleve eşleştirilecek işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
[ call_as(
   function
) ]
```

### <a name="parameters"></a>Parametreler

*İşlevi*  
Uzak bir işlev çağrıldığında çağrılacak istediğiniz yerel işlev.

## <a name="remarks"></a>Açıklamalar

**Call_as** C++ özniteliği ile aynı işlevlere sahip [call_as](/windows/desktop/Midl/call-as) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir **call_as** nonremotable işlevi eşleştirmek için (`f1`) Uzaktan erişilebilir işlevi (`Remf1`):

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
|**İçin geçerlidir**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  
[Yerel](../windows/local-cpp.md)  