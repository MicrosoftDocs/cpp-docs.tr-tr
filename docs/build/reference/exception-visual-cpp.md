---
title: '&lt;özel durum >C++ (belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
ms.openlocfilehash: ddfe647fa2db55b3ca606265011896a66398a8a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988298"
---
# <a name="ltexceptiongt"></a>&lt;özel durum&gt;

\<özel durum > etiketi hangi özel durumların atılamayacağını belirlemenizi sağlar. Bu etiket bir yöntem tanımına uygulanır.

## <a name="syntax"></a>Sözdizimi

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamında kullanılabilir bir özel duruma başvuru. Ad arama kurallarını kullanarak, derleyici verilen özel durumun var olduğunu denetler ve `member` çıktı XML dosyasında kurallı öğe adına çevirir.  Derleyici `member`bulamazsa bir uyarı verir.

Adı tek veya çift tırnak içine alın.

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz. [\<](see-visual-cpp.md).

*description*<br/>
Bir açıklama.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. Daha fazla bilgi için bkz. [\<SeeAlso >](seealso-visual-cpp.md) .

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
