---
title: noncreatable (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: b645d6d6cbcaeff346437d6457360ecdef8d3190
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840563"
---
# <a name="noncreatable"></a>noncreatable

Kendisi tarafından örneklenemez bir nesne tanımlar.

## <a name="syntax"></a>Syntax

```cpp
[noncreatable]
```

## <a name="remarks"></a>Açıklamalar

**Creatable olmayan** C++ özniteliği, [creatable](/windows/win32/Midl/noncreatable) MIDL özniteliğiyle aynı işlevselliğe sahiptir ve otomatik olarak oluşturulan ' a geçirilir. Derleyiciye göre IDL dosyası.

Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak, öznitelik [object_entry_non_createable_ex_auto](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosunu da çıkartır. Bu makro, ATL 'nin nesnenin dışarıdan oluşturuamayacağını gösterir.

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
