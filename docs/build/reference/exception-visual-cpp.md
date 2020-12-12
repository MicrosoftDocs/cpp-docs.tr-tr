---
description: 'Daha fazla bilgi edinin: &lt; özel durum &gt; etiketi'
title: '&lt;özel durum> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
ms.openlocfilehash: c75f2a4a10386664e23b5ba730e1827c6d74af71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192427"
---
# <a name="ltexceptiongt-tag"></a>&lt;özel durum &gt; etiketi

\<exception>Etiketi hangi özel durumların atılamayacağını belirtmenizi sağlar. Bu etiket bir yöntem tanımına uygulanır.

## <a name="syntax"></a>Sözdizimi

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamında kullanılabilir bir özel duruma başvuru. Ad arama kurallarını kullanarak, derleyici verilen özel durumun var olduğunu denetler ve `member` çıkış XML dosyasında kurallı öğe adına çevirir.  Derleyici bulamazsa bir uyarı verir `member` .

Adı tek veya çift tırnak içine alın.

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz [\<see>](see-visual-cpp.md) ..

*açıklaması*<br/>
Bir açıklama.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. [\<seealso>](seealso-visual-cpp.md)Daha fazla bilgi için bkz..

## <a name="example"></a>Örnek

```cpp
// xml_exception_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_exception_tag.dll
using namespace System;

/// Text for class EClass.
public ref class EClass : public Exception {
   // class definition ...
};

/// <exception cref="System.Exception">Thrown when... .</exception>
public ref class TestClass {
   void Test() {
      try {
      }
      catch(EClass^) {
      }
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
