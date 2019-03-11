---
title: '&lt;param&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: 33288b170dc89ad9fd7bbf33fece11c396f45295
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743231"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)

\<Param > Etiket kullanılmalıdır yöntemi bildirimi için açıklama parametrelerden biri yöntemi tanımlamak için.

## <a name="syntax"></a>Sözdizimi

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>Parametreler

*Adı*<br/>
Bir yöntem parametresi adı.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `name`.

*Açıklaması*<br/>
Parametre için bir açıklama.

## <a name="remarks"></a>Açıklamalar

Metni \<param > etiketi IntelliSense içinde gösterilecek [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code)ve kod açıklaması Web raporu.

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
