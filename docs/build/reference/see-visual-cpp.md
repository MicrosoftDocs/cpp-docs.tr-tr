---
description: Hakkında daha fazla bilgi &lt; edinin:&gt;
title: '&lt;bkz.> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: b4f8f9a2312a3db1ce2840209668b7b23837ab31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224744"
---
# <a name="ltseegt"></a>&lt;bakýn&gt;

\<see>Etiketi, metnin içinden bir bağlantı belirtmenize olanak tanır. [\<seealso>](seealso-visual-cpp.md)Ayrıca bkz. bölümünde görünmesini isteyebileceğiniz metni göstermek için kullanın.

## <a name="syntax"></a>Sözdizimi

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru.  Adı tek veya çift tırnak içine alın.

Derleyici, verilen kod öğesinin var olduğunu ve `member` çıkış XML dosyasında öğe adına çözümlendiğini denetler.  Derleyici bulamazsa bir uyarı verir `member` .

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

[\<summary>](summary-visual-cpp.md)Hakkında bir örnek için bkz \<see> ..

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. [\<seealso>](seealso-visual-cpp.md)Daha fazla bilgi için bkz..

## <a name="example"></a>Örnek

Aşağıdaki örnek, derleyicinin başvuruyu çözümleyecek şekilde genel bir türe nasıl cref başvurusu yapabileceğiniz gösterilmektedir.

```cpp
// xml_see_cref_example.cpp
// compile with: /LD /clr /doc
// the following cref shows how to specify the reference, such that,
// the compiler will resolve the reference
/// <see cref="C{T}">
/// </see>
ref class A {};

// the following cref shows another way to specify the reference,
// such that, the compiler will resolve the reference
/// <see cref="C < T >"/>

// the following cref shows how to hard-code the reference
/// <see cref="T:C`1">
/// </see>
ref class B {};

/// <see cref="A">
/// </see>
/// <typeparam name="T"></typeparam>
generic<class T>
ref class C {};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
