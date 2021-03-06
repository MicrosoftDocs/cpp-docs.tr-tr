---
description: 'Hakkında daha fazla bilgi edinin: &lt; param&gt;'
title: '&lt;param> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: 1de18bd050cfd6986f1fba7f1ae7acc289a41e14
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126214"
---
# <a name="ltparamgt"></a>&lt;larına&gt;

\<param>Yöntemi, yöntemin parametrelerinden birini açıklayacak bir yöntem bildirimine ilişkin açıklamada kullanılmalıdır.

## <a name="syntax"></a>Sözdizimi

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>Parametreler

*ada*<br/>
Bir yöntem parametresinin adı.  Adı tek veya çift tırnak içine alın.  Derleyici bulamazsa bir uyarı verir `name` .

*açıklaması*<br/>
Parametresi için bir açıklama.

## <a name="remarks"></a>Açıklamalar

\<param>Etiketin metni IntelliSense, [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code)ve kod yorumu Web raporunda görüntülenir.

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
