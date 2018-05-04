---
title: C sonek arttırma ve azaltma işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f96c48a69f692c8646de5dec8ad8e6431fb63c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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