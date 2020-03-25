---
title: Satype (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 4619deec6d5e4e9083fbc7bcab53caee0101285c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166282"
---
# <a name="satype"></a>satype

`SAFEARRAY` yapısının veri türünü belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Parametreler

*data_type*<br/>
Bir arabirim yöntemine parametre olarak geçirilmekte olan `SAFEARRAY` veri yapısına yönelik veri türü.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim parametresi, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

## <a name="remarks"></a>Açıklamalar

**Satype** C++ özniteliği `SAFEARRAY`veri türünü belirtir.

> [!NOTE]
> Bir yöneltme düzeyi, oluşturulan. IDL dosyasındaki `SAFEARRAY` işaretçisinden. cpp dosyasında bildirildiği şekilde bırakılır.

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
[id](id.md)
