---
title: '&lt;özel durum&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- exception
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03724e6f1ad0c85ad70e464786a7393b3f2f61e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094994"
---
# <a name="ltexceptiongt-visual-c"></a>&lt;özel durum&gt; (Visual C++)
\<Özel durum > etiketi hangi özel durumlar atılabilir belirtmenize olanak sağlar. Bu etiket, bir yöntem tanımına uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parametreler  
*Üyesi*<br/>
Geçerli derleme ortamdan kullanılabilir bir özel durum başvuru. Ad arama kurallarını kullanarak, derleyici belirtilen özel var ve çevirir denetler `member` kurallı öğesi adı ' % s'çıkış XML dosyası.  Değil bulamazsa, derleyici bir uyarı verir `member`.  
  
 Ad, tek veya çift tırnak içine alın.  
  
 Genel tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bakın >](../ide/see-visual-cpp.md).  
  
*Açıklaması*<br/>
Bir açıklama.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.  
  
 Visual C++ derleyicisi, belge yorumlarını bir geçiş cref başvuruları çözümlemek dener.  Bu nedenle, C++ arama kurallarını kullanarak, bir sembol başvurusu işaretlenir derleyici tarafından bulunamadı olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)