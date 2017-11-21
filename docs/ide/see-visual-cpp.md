---
title: '&lt;bkz:&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs: C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25dc28c993289942d0eafd2f20fb5c849f1658c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltseegt-visual-c"></a>&lt;bkz:&gt; (Visual C++)
\<Bkz > etiketi metin içindeki bir bağlantıdan belirtmenize olanak sağlar. Kullanım [ \<seealso >](../ide/seealso-visual-cpp.md) bir Ayrıca bkz. bölümünde görünen isteyebilirsiniz metin belirtmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `member`  
 Bir üye ya da geçerli derleme ortamından çağrılacak kullanılabilir alan başvuru.  Ad, tek veya çift tırnak işaretleri içine alın.  
  
 Verilen code öğesi var ve çözümler derleyici denetler `member` çıktı XML öğesi adı.  Derleyici bulamadı, bir uyarı verir `member`.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
 Bkz: [ \<Özet >](../ide/summary-visual-cpp.md) kullanma örneği için \<bakın >.  
  
 Visual C++ derleyicisi belge açıklamaları bir geçiş cref başvurularında çözümlemeye çalışır.  Bu nedenle, C++ arama kurallarını kullanarak, bir simge başvuru işaretlenir derleyici tarafından bulunmaması halinde olarak çözümlenmemiş. Bkz: [ \<seealso >](../ide/seealso-visual-cpp.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Derleyici başvurusu çözümleyecek şekilde aşağıdaki örnek, genel bir tür cref referansı nasıl yapabileceğiniz gösterir.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)