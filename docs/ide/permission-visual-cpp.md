---
title: '&lt;izni&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: 5cbcfd6bee97c3ca937ddfac363cd70276ee4d1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529122"
---
# <a name="ltpermissiongt-visual-c"></a>&lt;izni&gt; (Visual C++)

\<İzni > etiketi üyenin erişim belge olanak tanır. <xref:System.Security.PermissionSet> üye erişimi belirtmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Parametreler

*Üyesi*<br/>
Bir üye veya geçerli derleme ortamdan çağrılacak kullanılabilir alan başvuru. Derleyici belirli kod öğesi var. çevirir olup olmadığını denetler ve `member` kurallı öğesi adı ' % s'çıkış XML dosyası.  Ad, tek veya çift tırnak içine alın.

Değil bulamazsa, derleyici bir uyarı verir `member`.

Genel tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bakın >](../ide/see-visual-cpp.md).

*Açıklaması*<br/>
Üye erişimi açıklaması.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

Visual C++ derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

```
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)