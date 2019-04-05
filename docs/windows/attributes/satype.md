---
title: satype (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 7588e8d855d648309c46d981898cfbbf7888f4c9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025730"
---
# <a name="satype"></a>satype

Veri türü belirtir `SAFEARRAY` yapısı.

## <a name="syntax"></a>Sözdizimi

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Parametreler

*data_type*<br/>
Veri türü için `SAFEARRAY` arabirim yöntemi için parametre olarak geçirilen veri yapısı.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Arabirimi parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|None|

## <a name="remarks"></a>Açıklamalar

**Satype** C++ öznitelik veri türü belirtir `SAFEARRAY`.

> [!NOTE]
> Yöneltme düzeyi düşürülmüştür `SAFEARRAY` nasıl .cpp dosyasında bildirilen öğesinden oluşturulan .idl dosyasındaki bir işaretçi.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[kimlik](id.md)