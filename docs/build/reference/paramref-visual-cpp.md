---
title: '&lt;paramref> (C++ belgeleri açıklamaları)'
description: Paramref C++ XML belge etiketi hakkında daha fazla bilgi edinin.
ms.date: 11/04/2016
f1_keywords:
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: 393703e7816368fb80f71d962dc190a0db1cea03
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126162"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

Etiketi, bir \<paramref> sözcüğün bir parametre olduğunu göstermek için bir yol sağlar. Bu parametreyi farklı bir şekilde biçimlendirmek için. xml dosyası işlenebilir.

## <a name="syntax"></a>Sözdizimi

```
<paramref name="name"/>
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
Başvurabileceğiniz parametrenin adı.  Adı tek veya çift tırnak içine alın.  Derleyici bulamazsa bir uyarı verir `name` .

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
