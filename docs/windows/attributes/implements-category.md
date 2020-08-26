---
title: implements_category (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: cd9a4de8834bc22368393e9ea4639884785af0f2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846127"
---
# <a name="implements_category"></a>implements_category

Hedef sınıf tarafından uygulanan bileşen kategorilerini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Parametreler

*implements_category*<br/>
Uygulanan kategorinin KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**İmplements_category** C++ özniteliği, hedef sınıf tarafından uygulanan bileşen kategorilerini belirtir. Bu, bir KATEGORI Haritası oluşturup **implements_category** özniteliği tarafından belirtilen ayrı girdileri ekleyerek yapılır. Daha fazla bilgi için bkz. [Bileşen kategorileri ve bunların nasıl çalıştıkları](/windows/win32/com/component-categories-and-how-they-work).

Bu öznitelik, [coclass](coclass.md), [ProgID](progid.md)veya [vi_progid](vi-progid.md) özniteliğinin (ya da bunlardan birini belirten başka bir özniteliğin) aynı öğeye uygulanmasını gerektirir. Tek bir öznitelik kullanılırsa, diğer ikisi otomatik olarak uygulanır. Örneğin, `progid` uygulanmışsa `vi_progid` ve `coclass` de uygulanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, aşağıdaki nesnenin kategoriyi uyguladığını belirtir `Control` .

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|Aşağıdakilerden biri: `coclass` , `progid` veya `vi_progid`|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM öznitelikleri](com-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)
