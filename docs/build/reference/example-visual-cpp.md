---
title: '&lt;örnek > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 384e9b9808a49770887eeda69b1d24fdd3f06027
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988319"
---
# <a name="ltexamplegt"></a>&lt;örnek&gt;

\<örnek > etiketi, bir yöntemin veya diğer kitaplık üyesinin nasıl kullanılacağına ilişkin bir örnek belirtmenize olanak tanır. Bu, genellikle [\<code >](code-visual-cpp.md) etiketinin kullanımını da içerir.

## <a name="syntax"></a>Sözdizimi

```
<example>description</example>
```

#### <a name="parameters"></a>Parametreler

*description*<br/>
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
