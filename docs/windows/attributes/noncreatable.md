---
title: noncreatable (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: a10d93650c0ae564019a09b34c3a604d12327998
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305326"
---
# <a name="noncreatable"></a>noncreatable

Tek başına oluşturulamaz bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[noncreatable]
```

## <a name="remarks"></a>Açıklamalar

**Noncreatable** C++ özniteliği ile aynı işlevlere sahip [noncreatable](/windows/desktop/Midl/noncreatable) MIDL özniteliği ve otomatik olarak aracılığıyla oluşturulan geçirilir. IDL dosyası derleyici tarafından.

Bu öznitelik ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, öznitelik de eklediği [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu. Bu makro, nesne harici olarak oluşturulamıyor ATL için gösterir.

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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
