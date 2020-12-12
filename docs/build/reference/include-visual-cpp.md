---
description: 'Şunlar hakkında daha fazla bilgi edinin: &lt;&gt;'
title: '&lt;> dahil et (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: 577281b293fcca9b9b0b9491dd239240d435f32c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199785"
---
# <a name="ltincludegt"></a>&lt;include&gt;

\<include>Etiketi, kaynak kodunuzda türleri ve üyeleri tanımlayan başka bir dosyadaki açıklamalara başvurmanıza olanak sağlar. Bu, belge açıklamalarını doğrudan kaynak kodu dosyanıza yerleştirmeye alternatiftir.  Örneğin, \<include> takımınızın veya şirketinizin tamamında kullanılan standart "demirbaş" açıklamalarını eklemek için kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Parametreler

*filename*<br/>
Belgeleri içeren dosyanın adı. Dosya adı bir yol ile nitelenebilir.  Adı tek veya çift tırnak içine alın.  Derleyici bulamazsa bir uyarı verir `filename` .

*tagpath*<br/>
Dosyada bulunan istenen düğüm kümesini seçen geçerli bir XPath ifadesi.

*ada*<br/>
Yorumlarla önce gelen etiketteki ad Belirleyicisi; `name` , olur `id` .

*id*<br/>
Açıklamaların önündeki etiketin KIMLIĞI.  Adı tek veya çift tırnak içine alın.

## <a name="remarks"></a>Açıklamalar

\<include>Etiketi, XML XPath söz dizimini kullanır. Kullanarak özelleştirme yolları için XPath belgelerine bakın \<include> .

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

Bu çok dosyalı bir örnektir. Tarafından kullanılan ilk dosya \<include> aşağıdaki belge açıklamalarını içerir:

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

İkinci dosya xml_include_tag.doc, aşağıdaki belge açıklamalarını içerir:

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

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
