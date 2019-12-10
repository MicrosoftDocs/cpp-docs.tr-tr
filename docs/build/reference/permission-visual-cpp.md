---
title: '&lt;izin > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: e7f0a59c85e3fa28d24e44953e207151c3afa0f4
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988668"
---
# <a name="ltpermissiongt"></a>&lt;izin&gt;

\<izin > etiketi bir üyenin erişimini belgelemenizi sağlar. <xref:System.Security.PermissionSet> bir üyeye erişim belirlemenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Parametreler

*üyesidir*<br/>
Geçerli derleme ortamından çağrılabilen bir üyeye veya alana başvuru. Derleyici verilen kod öğesinin var olduğunu denetler ve çıkış XML dosyasında kurallı öğe adına `member` çevirir.  Adı tek veya çift tırnak içine alın.

Derleyici `member`bulamazsa bir uyarı verir.

Genel bir türe cref başvurusu oluşturma hakkında daha fazla bilgi için bkz. [\<](see-visual-cpp.md).

*description*<br/>
Üyeye erişim açıklaması.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

MSVC derleyicisi, belge açıklamalarındaki cref başvurularını tek bir geçişte çözümlemeye çalışır.  Bu nedenle, C++ arama kuralları kullanılıyorsa, derleyici tarafından bir sembol bulunamamıştır ve başvuru çözümlenmemiş olarak işaretlenir. Daha fazla bilgi için bkz. [\<SeeAlso >](seealso-visual-cpp.md) .

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
