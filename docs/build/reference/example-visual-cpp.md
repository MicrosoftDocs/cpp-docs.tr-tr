---
title: '&lt;Örnek > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 69e4ad8315948c9c77e99f6ebece4debbe3831b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272539"
---
# <a name="ltexamplegt"></a>&lt;Örnek&gt;

\<Örnek > etiketi bir yöntem veya diğer kitaplık üyesini kullanmaya ilişkin bir örnek belirtmenize olanak sağlar. Yaygın olarak, bu da kullanımını kapsayacaktır [ \<kod >](code-visual-cpp.md) etiketi.

## <a name="syntax"></a>Sözdizimi

```
<example>description</example>
```

#### <a name="parameters"></a>Parametreler

*Açıklaması*<br/>
Kod örneği açıklaması.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

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

[XML Belgeleri](xml-documentation-visual-cpp.md)
