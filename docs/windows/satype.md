---
title: satype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 6562721cfdf1fb963a6af71e8a8665887fa4d4ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413113"
---
# <a name="satype"></a>satype

Veri türü belirtir `SAFEARRAY` yapısı.

## <a name="syntax"></a>Sözdizimi

```cpp
[ satype(
   data_type
) ]
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

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)<br/>
[Parametre Öznitelikleri](../windows/parameter-attributes.md)<br/>
[Yöntem Öznitelikleri](../windows/method-attributes.md)<br/>
[id](../windows/id.md)  