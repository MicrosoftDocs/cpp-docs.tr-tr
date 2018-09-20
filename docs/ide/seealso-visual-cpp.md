---
title: '&lt;SeeAlso&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <seealso>
- seealso
dev_langs:
- C++
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69cbf45ee37ff10f5b367bc3915647815b2ccd09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376479"
---
# <a name="ltseealsogt-visual-c"></a>&lt;SeeAlso&gt; (Visual C++)

\<Seealso > etiketi, bir Ayrıca bkz. bölümünde görüntülenmesini isteyebilirsiniz metin belirtmenize olanak sağlar. Kullanım [ \<bakın >](../ide/see-visual-cpp.md) bağlantı metninde belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak içine alın.

Derleyici belirli kod öğesi var. çözümler olup olmadığını denetler ve `member` çıktı XML öğesi adı.  Değil bulamazsa, derleyici bir uyarı verir `member`.

Genel tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bakın >](../ide/see-visual-cpp.md).

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

Bkz: [ \<Özet >](../ide/summary-visual-cpp.md) kullanma örneği için \<seealso >.

Visual C++ derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş.

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

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)