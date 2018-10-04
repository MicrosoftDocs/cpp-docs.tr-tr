---
title: satype (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 255517789a5854ee6f76c4982bb75825905df546
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790022"
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
|**İçin geçerlidir**|Arabirimi parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[id](id.md)  