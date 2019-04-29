---
title: '&lt;param > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: d8ea4feddbe1ec2d5898f8ef698cc2d69d255933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320012"
---
# <a name="ltparamgt"></a>&lt;param&gt;

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

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

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
