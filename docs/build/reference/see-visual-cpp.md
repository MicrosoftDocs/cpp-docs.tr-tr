---
title: '&lt;bkz: > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: be99d3ac156c587888a7c56997d82531cf86ccec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318907"
---
# <a name="ltseegt"></a>&lt;Bkz:&gt;

\<Bakın > etiketi bağlantı metninde belirtmenize olanak sağlar. Kullanım [ \<seealso >](seealso-visual-cpp.md) ayrıca bölümü görünmesini istediğiniz metni belirtmek için.

## <a name="syntax"></a>Sözdizimi

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak içine alın.

Derleyici belirli kod öğesi var. çözümler olup olmadığını denetler ve `member` çıktı XML öğesi adı.  Değil bulamazsa, derleyici bir uyarı verir `member`.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

Bkz: [ \<Özet >](summary-visual-cpp.md) kullanma örneği için \<bakın >.

MSVC derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş. Bkz: [ \<seealso >](seealso-visual-cpp.md) daha fazla bilgi için.

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

[XML Belgeleri](xml-documentation-visual-cpp.md)
