---
title: Aralık (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 8ed0ba2c53992dd19d1c4491f8085e955146224c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839484"
---
# <a name="range-c"></a>aralık (C++)

Değerleri çalışma zamanında ayarlanmış olan bağımsız değişkenler veya alanlar için izin verilen değerler aralığını belirtir.

## <a name="syntax"></a>Söz dizimi

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
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)<br/>
[Veri üyesi öznitelikleri](data-member-attributes.md)
