---
title: Aralık (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.range
dev_langs:
- C++
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a4f84684c5d8f8feb8595da628976c90a2593c96
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201357"
---
# <a name="range-c"></a>aralık (C++)

Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ range(
   low,
   high
) ]
```

### <a name="parameters"></a>Parametreler

*Düşük*  
Düşük aralık değeri.

*Yüksek*  
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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Yöntem Öznitelikleri](../windows/method-attributes.md)  
[Parametre Öznitelikleri](../windows/parameter-attributes.md)  
[Veri Üyesi Öznitelikleri](../windows/data-member-attributes.md)  