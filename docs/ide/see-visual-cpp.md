---
title: '&lt;bkz:&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: c8e797dff1495e9b4573ab4e0820d60b8027a293
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747598"
---
# <a name="ltseegt-visual-c"></a>&lt;bkz:&gt; (Visual C++)

\<Bakın > etiketi bağlantı metninde belirtmenize olanak sağlar. Kullanım [ \<seealso >](../ide/seealso-visual-cpp.md) ayrıca bölümü görünmesini istediğiniz metni belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak içine alın.

Derleyici belirli kod öğesi var. çözümler olup olmadığını denetler ve `member` çıktı XML öğesi adı.  Değil bulamazsa, derleyici bir uyarı verir `member`.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

Bkz: [ \<Özet >](../ide/summary-visual-cpp.md) kullanma örneği için \<bakın >.

Visual C++ derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Derleyicinin başvuru giderecek şekilde, aşağıdaki örnek bir genel tür referansı cref nasıl kullanabileceğinizi gösterir.

```
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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
