---
title: "&lt;özel durum&gt; (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- exception
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c07dde806938b38dd55a3258b3724b0937d5601d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltexceptiongt-visual-c"></a>&lt;özel durum&gt; (Visual C++)
\<Özel durum > etiketi hangi özel durum belirtmenize olanak sağlar. Bu etiket için bir yöntem tanımını uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `member`  
 Geçerli derleme ortamından kullanılabilir bir özel durum referansı. Ad arama kuralları kullanarak derleyici belirtilen özel durum var ve çevirir denetler `member` XML çıktısında kurallı öğesi adı.  Derleyici bulamadı, bir uyarı verir `member`.  
  
 Ad, tek veya çift tırnak işaretleri içine alın.  
  
 Genel bir tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bkz >](../ide/see-visual-cpp.md).  
  
 `description`  
 Bir açıklama.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
 Visual C++ derleyicisi belge açıklamaları bir geçiş cref başvurularında çözümlemeye çalışır.  Bu nedenle, C++ arama kurallarını kullanarak, bir simge başvuru işaretlenir derleyici tarafından bulunmaması halinde olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.  
  
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