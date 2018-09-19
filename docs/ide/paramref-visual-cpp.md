---
title: '&lt;paramref&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- paramref
- <paramref>
dev_langs:
- C++
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a63caea7186114244927b9ede4c63ed97871d6e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111270"
---
# <a name="ltparamrefgt-visual-c"></a>&lt;paramref&gt; (Visual C++)
\<Paramref > etiketi bir sözcüğün bir parametre olduğunu belirtmek için bir yol sağlar. Bu parametreyi belirgin bir şekilde biçimlendirmek için .xml dosyasını işlenebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a>Parametreler  
*Adı*<br/>
Başvurmak için parametrenin adı.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `name`.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_paramref_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_paramref_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// The <paramref name="Int1"/> parameter takes a number.  
   /// </summary>  
   void MyMethod(int Int1) {}  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)