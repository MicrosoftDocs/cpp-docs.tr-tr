---
title: '&lt;paramref > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: 1f4e9cb0e6b39e4da78e78048342dac2ecc9deea
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988683"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<paramref > etiketi, bir sözcüğün bir parametre olduğunu göstermek için bir yol sağlar. Bu parametreyi farklı bir şekilde biçimlendirmek için. xml dosyası işlenebilir.

## <a name="syntax"></a>Sözdizimi

```
<paramref name="name"/>
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
Başvurabileceğiniz parametrenin adı.  Adı tek veya çift tırnak içine alın.  Derleyici `name`bulamazsa bir uyarı verir.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
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

[XML Belgeleri](xml-documentation-visual-cpp.md)
