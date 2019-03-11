---
title: '&lt;c&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: a5eb88be4cb5be8c4e970c285bad712093fdbb51
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742597"
---
# <a name="ltcgt-visual-c"></a>&lt;c&gt; (Visual C++)

\<c > etiketi gösteren metin açıklamasını içinde kod olarak işaretlenmelidir. Kullanım [ \<kod >](../ide/code-visual-cpp.md) çok satırlı kod olarak belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<c>text</c>
```

#### <a name="parameters"></a>Parametreler

*Metin*<br/>
Kod olarak belirtmek istediğiniz metin.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```cpp
// xml_c_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_c_tag.xdc

/// Text for class MyClass.
class MyClass {
public:
   int m_i;
   MyClass() : m_i(0) {}

   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.
   /// </summary>
   int MyMethod(MyClass * a) {
      return a -> m_i;
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
