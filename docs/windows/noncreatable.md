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
ms.openlocfilehash: b31ede898e2b1976bc16be7cf89c0223c3709193
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221549"
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

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
