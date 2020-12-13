---
description: 'Hakkında daha fazla bilgi edinin: &lt; c&gt;'
title: '&lt;c> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 35d06183136a82c602b5e4daa288fb4518962154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182625"
---
# <a name="ltcgt"></a>&lt;,&gt;

\<c>Etiket, bir açıklama içindeki metnin kod olarak işaretlenmesi gerektiğini gösterir. [\<code>](code-visual-cpp.md)Birden çok satırı kod olarak göstermek için kullanın.

## <a name="syntax"></a>Sözdizimi

```
<c>text</c>
```

#### <a name="parameters"></a>Parametreler

*metin*<br/>
Kod olarak göstermek istediğiniz metin.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

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

[XML Belgeleri](xml-documentation-visual-cpp.md)
