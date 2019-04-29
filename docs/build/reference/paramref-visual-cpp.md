---
title: '&lt;paramref > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: cee35ddb5fd5cd811e45f0aa49e94dd9c4b8b180
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319999"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<Paramref > etiketi bir sözcüğün bir parametre olduğunu belirtmek için bir yol sağlar. Bu parametreyi belirgin bir şekilde biçimlendirmek için .xml dosyasını işlenebilir.

## <a name="syntax"></a>Sözdizimi

```
<paramref name="name"/>
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
Başvurmak için parametrenin adı.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `name`.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

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

[XML Belgeleri](xml-documentation-visual-cpp.md)
