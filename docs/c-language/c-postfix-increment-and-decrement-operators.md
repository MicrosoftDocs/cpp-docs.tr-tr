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
ms.openlocfilehash: 7dc0b4c71aafe3435def0b96ae621c60ff640dc0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751217"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C Sonek Arttırma ve Azaltma İşleçleri
Sonek işleneni artırın ve azaltma işleçleri, değiştirilebilir bir l-değerler skaler türlerdir.  
  
## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Sonuç sonek artırma veya azaltma işlemi işlenenin değeridir. Sonuç alındıktan sonra işlenenin artırılması (veya azaltılması). Aşağıdaki kod sonek artırma işlecini gösterir.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
Bu örnekte, değişken `var` 0 olarak karşılaştırıldığında sonra artar. Varsa `var` pozitif artan önce sonraki deyimi yürütülür. İlk olarak, nesnenin değeri tarafından işaret edilen `q` tarafından işaret edilen nesnenin atandığı `p`. Ardından, `q` ve `p` artırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.

[Son Ek Arttırma ve Azaltma İşleçleri: ++ ve --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)