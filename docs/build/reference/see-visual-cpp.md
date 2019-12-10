---
title: '&lt;bkz. >C++ (belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: 8693646fa37648d1b20c791d99d159f2c81b8ec1
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988622"
---
# <a name="ltseegt"></a>&lt;bkz.&gt;

\<bkz. > etiketi, metnin içinden bir bağlantı belirtmenize olanak tanır. Ayrıca bkz. Ayrıca, Ayrıca bkz. bölümünde görünmesini isteyebileceğiniz metni göstermek için [\<](seealso-visual-cpp.md) kullanın.

## <a name="syntax"></a>Sözdizimi

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru.  Adı tek veya çift tırnak içine alın.

Derleyici verilen kod öğesinin var olduğunu denetler ve çıkış XML dosyasında öğe adına `member` çözümler.  Derleyici `member`bulamazsa bir uyarı verir.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

[\<özet >](summary-visual-cpp.md) bkz. > \<kullanma örneği.

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. Daha fazla bilgi için bkz. [\<SeeAlso >](seealso-visual-cpp.md) .

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
