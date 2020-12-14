---
description: 'Daha fazla bilgi edinin: &lt; izin&gt;'
title: '&lt;izin> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: cd815b5df831632afd399e752e4525082f20b063
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226031"
---
# <a name="ltpermissiongt"></a>&lt;yetkisi&gt;

\<permission>Etiketi bir üyenin erişimini belgelemenizi sağlar. <xref:System.Security.PermissionSet> bir üyeye erişim belirtmenize izin verir.

## <a name="syntax"></a>Sözdizimi

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru. Derleyici verilen kod öğesinin var olduğunu denetler ve `member` çıkış XML dosyasında kurallı öğe adına çevirir.  Adı tek veya çift tırnak içine alın.

Derleyici bulamazsa bir uyarı verir `member` .

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz [\<see>](see-visual-cpp.md) ..

*açıklaması*<br/>
Üyeye erişim açıklaması.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. [\<seealso>](seealso-visual-cpp.md)Daha fazla bilgi için bkz..

## <a name="example"></a>Örnek

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
