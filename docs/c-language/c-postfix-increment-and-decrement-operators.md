---
title: "C sonek arttırma ve azaltma işleçleri | Microsoft Docs"
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
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9fd1efe80cf5227c682a3bac47299a0daea49e1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C Sonek Arttırma ve Azaltma İşleçleri
Sonek işlenenleri artırmak ve azaltma işleçleri değiştirilebilir l değerleri olan skaler türleridir.  
  
## <a name="syntax"></a>Sözdizimi  
 *sonek ifade*:  
 *sonek ifade*  **++**  
  
 *sonek ifade*  **--**  
  
 Sonuç sonek artırma veya azaltma işlemi işleneni değeri. Sonuç alındıktan sonra işlenen artırılır (veya indirildiği) değeri. Aşağıdaki kod sonek artırma işlecinin gösterir.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 Bu örnekte, değişken `var` 0'a kıyasla sonra artar. Varsa `var` artar önce pozitif, next deyimi yürütülür. İlk olarak, nesnenin değerini işaret için tarafından `q` gösterdiği nesne atandığı `p`. Ardından, `q` ve `p` artırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Son Ek Arttırma ve Azaltma İşleçleri: ++ ve --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)