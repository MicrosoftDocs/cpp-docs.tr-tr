---
title: '&lt;Liste > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
ms.openlocfilehash: fd5b97ac518bc4075697da7b6ed88ed46bdd8814
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824084"
---
# <a name="ltlistgt"></a>&lt;list&gt;

\<Listheader > blok satırında bir tablo veya tanım listesi tanımlamak için kullanılır. Bir tablo tanımlarken, yalnızca bir giriş başlığı hükmün sağlamanız gerekir.

## <a name="syntax"></a>Sözdizimi

```
<list type="bullet" | "number" | "table">
   <listheader>
      <term>term</term>
      <description>description</description>
   </listheader>
   <item>
      <term>term</term>
      <description>description</description>
   </item>
</list>
```

#### <a name="parameters"></a>Parametreler

*Terim*<br/>
İçinde tanımlanan tanımlamak için bir terim `description`.

*Açıklaması*<br/>
Bir ya da öğe bir madde işareti veya numaralı liste tanımını bir `term`.

## <a name="remarks"></a>Açıklamalar

Listedeki her bir öğe ile belirtilen bir \<öğesi > bloğu. Tanım listesi oluştururken, her ikisi de belirtmeniz gerekir `term` ve `description`. Ancak, bir tablo, madde işaretli liste veya numaralı liste için bir giriş sağlamanız yeterlidir `description`.

Bir listeyi veya tabloyu kadar olabilir \<öğesi > gerektiğinde engeller.

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```cpp
// xml_list_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_list_tag.dll
/// <remarks>Here is an example of a bulleted list:
/// <list type="bullet">
/// <item>
/// <description>Item 1.</description>
/// </item>
/// <item>
/// <description>Item 2.</description>
/// </item>
/// </list>
/// </remarks>
class MyClass {};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
