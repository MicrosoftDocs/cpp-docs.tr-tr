---
title: '&lt;izin&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- permission
- <permission>
dev_langs:
- C++
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 416467782be92760ac999301f9899be1260905aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltpermissiongt-visual-c"></a>&lt;izin&gt; (Visual C++)
\<İzni > etiketi üyesi erişim belge olanak sağlar. <xref:System.Security.PermissionSet>üye erişimi belirtmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `member`  
 Bir üye ya da geçerli derleme ortamından çağrılacak kullanılabilir alan başvuru. Verilen code öğesi var ve çevirir derleyici denetler `member` XML çıktısında kurallı öğesi adı.  Ad, tek veya çift tırnak işaretleri içine alın.  
  
 Derleyici bulamadı, bir uyarı verir `member`.  
  
 Genel bir tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bkz >](../ide/see-visual-cpp.md).  
  
 `description`  
 Üye erişimi açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
 Visual C++ derleyicisi belge açıklamaları bir geçiş cref başvurularında çözümlemeye çalışır.  Bu nedenle, C++ arama kurallarını kullanarak, bir simge başvuru işaretlenir derleyici tarafından bulunmaması halinde olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.  
  
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