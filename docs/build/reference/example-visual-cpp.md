---
description: 'Daha fazla bilgi edinin: &lt; örnek&gt;'
title: '&lt;örnek> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 8ffa51be888fb631db6ec1ecd145177ea346084f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200838"
---
# <a name="ltexamplegt"></a>&lt;örneğinde&gt;

\<example>Etiketi, bir yöntemi veya diğer kitaplık üyesini nasıl kullanacağınızı gösteren bir örnek belirtmenizi sağlar. Bu, genellikle etiketinin kullanımını da içerir [\<code>](code-visual-cpp.md) .

## <a name="syntax"></a>Sözdizimi

```
<example>description</example>
```

#### <a name="parameters"></a>Parametreler

*açıklaması*<br/>
Kod örneğinin açıklaması.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
// xml_example_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_example_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>
   /// GetZero method
   /// </summary>
   /// <example> This sample shows how to call the GetZero method.
   /// <code>
   /// int main()
   /// {
   ///    return GetZero();
   /// }
   /// </code>
   /// </example>
   static int GetZero() {
      return 0;
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
