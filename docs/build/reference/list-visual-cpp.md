---
title: '&lt;listesi > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- list
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
ms.openlocfilehash: 102cf9f7b1b867a012f662ce786d97012826abd1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439307"
---
# <a name="ltlistgt"></a>&lt;list&gt;

\<listheader > bloğu, bir tablo ya da tanım listesinin başlık satırını tanımlamak için kullanılır. Bir tablo tanımlarken, yalnızca başlıktaki terim için bir giriş sağlamanız gerekir.

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

*terimli*<br/>
`description`tanımlanacak bir terim.

*açıklaması*<br/>
Bir madde işareti veya numaralandırılmış listedeki bir öğe ya da bir `term`tanımı.

## <a name="remarks"></a>Açıklamalar

Listedeki her öğe, bir \<öğesi > bloğu ile belirtilir. Tanım listesi oluştururken hem `term` hem de `description`belirtmeniz gerekir. Ancak, bir tablo, madde işaretli liste veya numaralandırılmış liste için yalnızca `description`için bir giriş sağlamanız gerekir.

Bir liste veya tablo, gereken sayıda \<öğe > bloğunu içerebilir.

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

[XML Belgeleri](xml-documentation-visual-cpp.md)
