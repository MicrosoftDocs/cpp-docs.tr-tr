---
title: noncreatable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 559d461a996789986dcc445d6ef510c7b179542c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381302"
---
# <a name="noncreatable"></a>noncreatable

Tek başına oluşturulamaz bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[noncreatable]
```

## <a name="remarks"></a>Açıklamalar

**Noncreatable** C++ özniteliği ile aynı işlevlere sahip [noncreatable](/windows/desktop/Midl/noncreatable) MIDL özniteliği ve otomatik olarak aracılığıyla oluşturulan geçirilir. IDL dosyası derleyici tarafından.

Bu öznitelik ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, öznitelik de eklediği [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu. Bu makro, nesne harici olarak oluşturulamıyor ATL için gösterir.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_noncreatable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("11111111-1111-1111-1111-111111111111")]
__interface A
{
};

[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]
class CMyClass : public A
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass**|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
