---
title: '&lt;dahil&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs: C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e3f6207afe58a9490e854eb5f7dbeb5a7489abb8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltincludegt-visual-c"></a>&lt;dahil&gt; (Visual C++)
\<Dahil > etiketi, başka bir dosya türlerini tanımlamak açıklamaları ve kaynak kodunuzu üyelerinde bakın sağlar. Bu belge açıklamaları doğrudan, kaynak kodu dosyasına yerleştirerek alternatiftir.  Örneğin, kullanabileceğiniz \<dahil > takım veya şirket içinde kullanılan standart "ortak" açıklamaları eklemek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Belgeleri içeren dosyanın adı. Dosya adı nitelenmiş bir yol olmalıdır.  Ad, tek veya çift tırnak işaretleri içine alın.  Derleyici bulamadı, bir uyarı verir `filename`.  
  
 `tagpath`  
 Dosyadaki istenen düğüm kümesi seçer geçerli bir XPath ifadesi.  
  
 `name`  
 Ad belirticisi açıklamaları önündeki etiketinde; `name` sahip bir `id`.  
  
 `id`  
 Açıklamaları önündeki etiket kimliği.  Ad, tek veya çift tırnak işaretleri içine alın.  
  
## <a name="remarks"></a>Açıklamalar  
 \<Dahil > etiketi XML XPath sözdizimini kullanır. Kullanarak'nı özelleştirme yolları XPath belgelerine bakın \<dahil >.  
  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
## <a name="example"></a>Örnek  
 Bu birden çok dosya bir örnektir. Kullanan ilk dosya \<dahil >, aşağıdaki belge açıklamaları içerir:  
  
```  
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
  
 İkinci dosya, xml_include_tag.doc, aşağıdaki belge açıklamaları içerir:  
  
```  
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
  
```  
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
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)