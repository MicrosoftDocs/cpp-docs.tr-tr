---
title: '&lt;Liste&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- list
- <list>
dev_langs:
- C++
helpviewer_keywords:
- list C++ XML tag
- <list> C++ XML tag
ms.assetid: c792a10b-0451-422c-9aa0-604116e69d64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bff8e3588e31414f50cb6d150c0e8c9f2603586b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ltlistgt-visual-c"></a>&lt;Liste&gt; (Visual C++)
\<Listheader > bloğu bir tablo veya tanım listesi başlık satırının tanımlamak için kullanılır. Bir tablo tanımlarken, yalnızca bir giriş başlığı'nda terim için sağlamanız gerekir.  
  
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
 `term`  
 İçinde tanımlanan tanımlamak için bir terim `description`.  
  
 `description`  
 Her iki öğeyi madde işareti veya numaralı liste ya da tanımı bir `term`.  
  
## <a name="remarks"></a>Açıklamalar  
 Listedeki her bir öğe ile belirtilen bir \<öğesi > bloğu. Bir tanım listesi oluştururken, her ikisi de belirtmeniz gerekir `term` ve `description`. Ancak, bir tablo, listeyi veya numaralandırılmış listesi için yalnızca bir giriş için sağlamanız gerekir `description`.  
  
 Bir liste veya tablo kadar olabilir \<öğesi > gerektiğinde engeller.  
  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)