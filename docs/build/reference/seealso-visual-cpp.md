---
title: '&lt;SeeAlso > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: ea399e98723a265ef3c17f2282b7c81299b4abc5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823691"
---
# <a name="ltseealsogt"></a>&lt;SeeAlso&gt;

\<Seealso > etiketi, bir Ayrıca bkz. bölümünde görüntülenmesini isteyebilirsiniz metin belirtmenize olanak sağlar. Kullanım [ \<bakın >](see-visual-cpp.md) bağlantı metninde belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak içine alın.

Derleyici belirli kod öğesi var. çözümler olup olmadığını denetler ve `member` çıktı XML öğesi adı.  Değil bulamazsa, derleyici bir uyarı verir `member`.

Genel tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bakın >](see-visual-cpp.md).

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

Bkz: [ \<Özet >](summary-visual-cpp.md) kullanma örneği için \<seealso >.

MSVC derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bir çözümlenmemiş simge bir cref başvuruluyor. XML yorumu cref B::Test için için olacak `<seealso cref="!:B::Test" />`A::Test başvuru biçimlendirildiğini bilgileriyse `<seealso cref="M:A.Test" />`.

```
// xml_seealso_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_seealso_tag.dll

/// Text for class A.
public ref struct A {
   /// <summary><seealso cref="A::Test"/>
   /// <seealso cref="B::Test"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void Test() {}
};

/// Text for class B.
public ref struct B {
   void Test() {}
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
