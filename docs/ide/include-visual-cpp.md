---
title: '&lt;dahil&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- include
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: 0d03ee6e327eb95e63cec16f3886d616c909c3df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451980"
---
# <a name="ltincludegt-visual-c"></a>&lt;dahil&gt; (Visual C++)

\<Dahil > etiket türleri açıklayan yorumlar başka bir dosyaya ve üyeleri, kaynak kodunuzdaki bakın olanak tanır. Bu belge açıklamaları doğrudan, kaynak kodu dosyasında yerleştirme için bir alternatifidir.  Örneğin, kullanabileceğiniz \<dahil > ekibiniz veya şirketiniz içinde kullanılan standart "standart" açıklama eklemek için.

## <a name="syntax"></a>Sözdizimi

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Belgeleri içeren dosyanın adı. Dosya adını içeren bir yol nitelenmiş olmalıdır.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `filename`.

*tagpath*<br/>
İstenen düğüm dosyasında yer alan kümesi seçer geçerli bir XPath ifadesi.

*Adı*<br/>
Yorumları önündeki etiketinde ad tanımlayıcısı; `name` sahip bir `id`.

*id*<br/>
Yorumları önünde etiket kimliği.  Ad, tek veya çift tırnak içine alın.

## <a name="remarks"></a>Açıklamalar

\<Dahil > etiketini XML XPath sözdizimi kullanır. XPath kullanarak özelleştirme yolları belgelerine başvurun \<dahil >.

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

Bu çok dosyalı bir örnektir. Kullanan ilk dosya \<dahil >, aşağıdaki belgeleri açıklamaları içerir:

```cpp
// xml_include_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_include_tag.dll

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />
public ref class Test {
   void TestMethod() {
   }
};

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />
public ref class Test2 {
   void Test() {
   }
};
```

İkinci bir dosya, xml_include_tag.doc, aşağıdaki belgeleri açıklamaları içerir:

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Program çıktısı

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>t2</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)