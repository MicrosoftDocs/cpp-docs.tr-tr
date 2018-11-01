---
title: C Sonek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: 8d45ce34457779e668124d9f48b82a5b74da1c56
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506862"
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