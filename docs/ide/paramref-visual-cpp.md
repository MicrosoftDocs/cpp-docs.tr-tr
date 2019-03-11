---
title: '&lt;paramref&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: 7c1b8a79761e10209e26e1dee8a8751746c2f38c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744659"
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

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
