---
title: "Önek arttırma ve azaltma işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f5a6c98d53c73a6913c9ed8e63b2a1fce43b97d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [C birli işleçler](../c-language/c-unary-operators.md)