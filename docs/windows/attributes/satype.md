---
title: Satype (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 16da256f491dbb0002d92cadaceda14a49eb2192
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842786"
---
# <a name="satype"></a>satype

Yapının veri türünü belirtir `SAFEARRAY` .

## <a name="syntax"></a>Söz dizimi

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Parametreler

*data_type*<br/>
Bir `SAFEARRAY` arabirim yöntemine parametre olarak geçirilmekte olan veri yapısına yönelik veri türü.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

## <a name="remarks"></a>Açıklamalar

**Satype** C++ özniteliği, öğesinin veri türünü belirtir `SAFEARRAY` .

> [!NOTE]
> Bir yöneltme düzeyi, `SAFEARRAY` oluşturulan. IDL dosyasındaki işaretçiden. cpp dosyasında bildirildiği şekilde bırakılır.

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

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[id](id.md)
