---
description: 'Daha fazla bilgi edinin: Range (C++)'
title: Aralık (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 0c1a45ac1f4e968de52c9ed2bffb89ac2cf5fd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327359"
---
# <a name="range-c"></a>aralık (C++)

Değerleri çalışma zamanında ayarlanmış olan bağımsız değişkenler veya alanlar için izin verilen değerler aralığını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>Parametreler

*zayıf*<br/>
Düşük Aralık değeri.

*geniş*<br/>
Yüksek Aralık değeri.

## <a name="remarks"></a>Açıklamalar

**Range** C++ özniteliği [, MIDL](/windows/win32/Midl/range) özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_range.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim yöntemi, arabirim parametresi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Veri üyesi öznitelikleri](data-member-attributes.md)
