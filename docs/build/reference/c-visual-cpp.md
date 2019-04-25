---
title: '&lt;c > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 43e1417e5a749f2ea51346bbf6db235ba08a7bcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294778"
---
# <a name="ltcgt"></a>&lt;c&gt;

\<c > etiketi gösteren metin açıklamasını içinde kod olarak işaretlenmelidir. Kullanım [ \<kod >](code-visual-cpp.md) çok satırlı kod olarak belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<c>text</c>
```

#### <a name="parameters"></a>Parametreler

*Metin*<br/>
Kod olarak belirtmek istediğiniz metin.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

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
