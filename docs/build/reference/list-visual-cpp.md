---
title: '&lt;liste> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- list
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
ms.openlocfilehash: 24f9b17c67b8f951743fd51c04266b05dad235c7
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041971"
---
# <a name="ltlistgt-and-ltlistheadergt"></a>&lt;liste &gt; ve &lt; listheader&gt;

\<listheader>Blok, bir tablo ya da tanım listesinin başlık satırını tanımlamak için kullanılır. Bir tablo tanımlarken, yalnızca başlıktaki terim için bir giriş sağlamanız gerekir.

## <a name="syntax"></a>Söz dizimi

```xml
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

*terimli*<br/>
' De tanımlanacak bir terim `description` .

*açıklaması*<br/>
Bir madde işareti veya numaralandırılmış listedeki bir öğe ya da bir tanımı `term` .

## <a name="remarks"></a>Açıklamalar

Listedeki her öğe bir \<item> blokla belirtilir. Bir tanım listesi oluştururken, hem hem de belirtmeniz gerekecektir `term` `description` . Ancak, bir tablo, madde işaretli liste veya numaralandırılmış liste için yalnızca bir giriş sağlamanız gerekir `description` .

Bir liste veya tablo gerektiği kadar çok \<item> blok içerebilir.

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

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

[XML belgeleri](xml-documentation-visual-cpp.md)
