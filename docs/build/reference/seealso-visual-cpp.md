---
description: 'Daha fazla bilgi edinin: &lt; SeeAlso&gt;'
title: '&lt;SeeAlso> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: 70f5f0147ff56dd6327e99f073f80c28a7cce539
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224731"
---
# <a name="ltseealsogt"></a>&lt;SeeAlso&gt;

\<seealso>Etiketi, Ayrıca bkz. bölümünde görünmesini isteyebileceğiniz metni belirtmenize imkan sağlar. [\<see>](see-visual-cpp.md)Metnin içinden bir bağlantı belirtmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru.  Adı tek veya çift tırnak içine alın.

Derleyici, verilen kod öğesinin var olduğunu ve `member` çıkış XML dosyasında öğe adına çözümlendiğini denetler.  Derleyici bulamazsa bir uyarı verir `member` .

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz [\<see>](see-visual-cpp.md) ..

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

[\<summary>](summary-visual-cpp.md)Hakkında bir örnek için bkz \<seealso> ..

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bir cref 'de çözümlenmemiş bir sembole başvurulur. Cref to B:: test için XML yorumu olacaktır `<seealso cref="!:B::Test" />` , ancak:: test başvurusu doğru biçimlendirilmiş `<seealso cref="M:A.Test" />` .

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
