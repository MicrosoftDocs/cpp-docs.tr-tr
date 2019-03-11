---
title: '&lt;örnek&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: b1511bb77b35b054d83a64c1a832843e62a8daa9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744015"
---
# <a name="ltexamplegt-visual-c"></a>&lt;örnek&gt; (Visual C++)

\<Örnek > etiketi bir yöntem veya diğer kitaplık üyesini kullanmaya ilişkin bir örnek belirtmenize olanak sağlar. Yaygın olarak, bu da kullanımını kapsayacaktır [ \<kod >](../ide/code-visual-cpp.md) etiketi.

## <a name="syntax"></a>Sözdizimi

```
<example>description</example>
```

#### <a name="parameters"></a>Parametreler

*Açıklaması*<br/>
Kod örneği açıklaması.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```
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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
