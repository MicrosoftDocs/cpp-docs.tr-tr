---
title: '&lt;Özel Durum > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
ms.openlocfilehash: 327c1bc27f4ae71aa214e09f375f963dad5b33d7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823553"
---
# <a name="ltexceptiongt"></a>&lt;özel durum&gt;

\<Özel durum > etiketi hangi özel durumlar atılabilir belirtmenize olanak sağlar. Bu etiket, bir yöntem tanımına uygulanır.

## <a name="syntax"></a>Sözdizimi

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Geçerli derleme ortamdan kullanılabilir bir özel durum başvuru. Ad arama kurallarını kullanarak, derleyici belirtilen özel var ve çevirir denetler `member` kurallı öğesi adı ' % s'çıkış XML dosyası.  Değil bulamazsa, derleyici bir uyarı verir `member`.

Ad, tek veya çift tırnak içine alın.

Genel tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bakın >](see-visual-cpp.md).

*Açıklaması*<br/>
Bir açıklama.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

MSVC derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş. Bkz: [ \<seealso >](seealso-visual-cpp.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

```
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
