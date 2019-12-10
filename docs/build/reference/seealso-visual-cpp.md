---
title: '&lt;seede > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: 698db2df462f561acd897d0d0e56b3106a915466
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988610"
---
# <a name="ltseealsogt"></a>&lt;seede&gt;

\<seede > etiketi, Ayrıca bkz. bölümünde görünmesini isteyebileceğiniz metni belirtmenize olanak tanır. Metin içinden bir bağlantı belirtmek için [\<> bakın](see-visual-cpp.md) .

## <a name="syntax"></a>Sözdizimi

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru.  Adı tek veya çift tırnak içine alın.

Derleyici verilen kod öğesinin var olduğunu denetler ve çıkış XML dosyasında öğe adına `member` çözümler.  Derleyici `member`bulamazsa bir uyarı verir.

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz. [\<](see-visual-cpp.md).

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

Bkz. \<SeeAlso > kullanımı örneği için [\<özet >](summary-visual-cpp.md) .

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bir cref 'de çözümlenmemiş bir sembole başvurulur. Cref-B:: test için XML yorumu `<seealso cref="!:B::Test" />`olacaktır, ancak:: test başvurusu doğru biçimlendirilmiş `<seealso cref="M:A.Test" />`.

```cpp
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
