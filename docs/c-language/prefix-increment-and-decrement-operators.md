---
title: "Önek arttırma ve azaltma işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84d8c3f5a1b43fdec5554003e32db4f23b4f0406
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="prefix-increment-and-decrement-operators"></a>Önek Arttırma ve Azaltma İşleçleri
Birli işleçleri (`++` ve  **--** ) "öneki" artışı adlı veya artırma veya azaltma işleçleri önce işlenen görüntülendiğinde işleçleri azaltma. Sonek arttırma ve azaltma önek artırma ve azaltma daha yüksek önceliğe sahiptir. İşlenen integral, kayan veya işaretçi türü olması gerekir ve değiştirilebilir l-değeri ifadesi olmalıdır (olmayan bir ifade **const** özniteliği). L-değeri sonucudur.  
  
 İşleç önce kendi işleneni göründüğünde, işlenen artırılır veya indirildiği ve yeni değeri ifade sonucudur.  
  
 Tam sayı veya kayan tür işleneni tamsayı değeri 1 artırılır veya indirildiği. Sonuç türü işlenen türü ile aynıdır. İşaretçi türünün işleneni bu adresleri nesnesi tarafından artırılır veya indirildiği boyutudur. Bir artımlı işaretçinin sonraki nesneye işaret; Azaltılan işaretçi önceki nesneye işaret etmiyor.  
  
## <a name="example"></a>Örnek  
 Bu örnekte birli önek azaltma işleci gösterilmektedir:  
  
```  
if( line[--i] != '\n' )  
    return;  
```  
  
 Bu örnekte, değişken `i` bir alt simge olarak kullanılabilmesi düşülür `line`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Birli İşleçler](../c-language/c-unary-operators.md)