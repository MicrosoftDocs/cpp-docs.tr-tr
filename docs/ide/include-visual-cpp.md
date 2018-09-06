---
title: '&lt;dahil&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3cb07824ad5212f4174a6f19e3efa4549432455
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894462"
---
# <a name="ltincludegt-visual-c"></a>&lt;dahil&gt; (Visual C++)

\<Dahil > etiket türleri açıklayan yorumlar başka bir dosyaya ve üyeleri, kaynak kodunuzdaki bakın olanak tanır. Bu belge açıklamaları doğrudan, kaynak kodu dosyasında yerleştirme için bir alternatifidir.  Örneğin, kullanabileceğiniz \<dahil > ekibiniz veya şirketiniz içinde kullanılan standart "standart" açıklama eklemek için.

## <a name="syntax"></a>Sözdizimi

```  
<include file='filename' path='tagpath' />
```  

#### <a name="parameters"></a>Parametreler

`filename`  
Belgeleri içeren dosyanın adı. Dosya adını içeren bir yol nitelenmiş olmalıdır.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `filename`.

`tagpath`  
İstenen düğüm dosyasında yer alan kümesi seçer geçerli bir XPath ifadesi.

`name`  
Yorumları önündeki etiketinde ad tanımlayıcısı; `name` sahip bir `id`.

`id`  
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