---
title: Aralık (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.range
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
ms.openlocfilehash: 380f7c9e15a3682b486217c842f00c944251e631
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214623"
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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim yöntemi, arabirim parametresi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)
