---
title: Aralık (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 9ce941fe95f2bbef3895c039984db1e1d2985ae1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029544"
---
# <a name="range-c"></a>aralık (C++)

Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ range(low, high) ]
```

### <a name="parameters"></a>Parametreler

*Düşük*<br/>
Düşük aralık değeri.

*Yüksek*<br/>
Yüksek bir aralık değeri.

## <a name="remarks"></a>Açıklamalar

**Aralığı** C++ özniteliği ile aynı işlevlere sahip [aralığı](/windows/desktop/Midl/range) MIDL özniteliği.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirim yöntemini, arabirim parametresi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)