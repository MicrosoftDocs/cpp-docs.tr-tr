---
title: '&lt;SeeAlso&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <seealso>
- seealso
dev_langs: C++
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2e1d50162989e5148cd0755afb48f4413ce51269
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltseealsogt-visual-c"></a>&lt;SeeAlso&gt; (Visual C++)
\<Seealso > etiketi bir Ayrıca bkz. bölümünde görünen isteyebilirsiniz metin belirtmenize olanak sağlar. Kullanım [ \<bkz >](../ide/see-visual-cpp.md) metin içindeki bir bağlantıdan belirtmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `member`  
 Bir üye ya da geçerli derleme ortamından çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak işaretleri içine alın.  
  
 Verilen code öğesi var ve çözümler derleyici denetler `member` çıktı XML öğesi adı.  Derleyici bulamadı, bir uyarı verir `member`.  
  
 Genel bir tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bkz >](../ide/see-visual-cpp.md).  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
 Bkz: [ \<Özet >](../ide/summary-visual-cpp.md) kullanma örneği için \<seealso >.  
  
 Visual C++ derleyicisi belge açıklamaları bir geçiş cref başvurularında çözümlemeye çalışır.  Bu nedenle, C++ arama kurallarını kullanarak, bir simge başvuru işaretlenir derleyici tarafından bulunmaması halinde olarak çözümlenmemiş.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, bir cref çözülmemiş bir simge başvuruluyor. Cref B::Test için XML açıklama olacaktır `<seealso cref="!:B::Test" />`, A::Test referansı doğru biçimlendirilmiş iken `<seealso cref="M:A.Test" />`.  
  
```  
// xml_seealso_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_seealso_tag.dll  
  
/// Text for class A.  
public ref struct A {  
   /// <summary><seealso cref="A::Test"/>  
   /// <seealso cref="B::Test"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void Test() {}  
};  
  
/// Text for class B.  
public ref struct B {  
   void Test() {}  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)