---
title: implements_category (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: bbd859018210d3c972ae9d4b0e9f659d96d95aab
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504199"
---
# <a name="implementscategory"></a>implements_category

Hedef sınıf tarafından uygulanan bileşen kategorilerini belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Parametreler

*implements_category*<br/>
Uygulanan kategori kimliği.

## <a name="remarks"></a>Açıklamalar

**İmplements_category** C++ özniteliği hedef sınıf tarafından uygulanan bileşen kategorileri belirtir. Bu kategori harita oluşturma ve tarafından belirlenen ayrı girdileri ekleyerek yapılır **implements_category** özniteliği. Daha fazla bilgi için [bileşeni kategoriler ve nasıl bunlar iş](/windows/desktop/com/component-categories-and-how-they-work).

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye. Herhangi bir tek öznitelik kullandıysanız, diğer iki otomatik olarak uygulanır. Örneğin, varsa `progid` uygulanan `vi_progid` ve `coclass` de uygulanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, aşağıdaki uygulayan nesne belirtir `Control` kategorisi.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|Aşağıdakilerden biri: `coclass`, `progid`, veya `vi_progid`|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)