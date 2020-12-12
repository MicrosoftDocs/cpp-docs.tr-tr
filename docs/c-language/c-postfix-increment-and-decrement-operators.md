---
description: 'Daha fazla bilgi edinin: C Sonek artışı ve azaltma Işleçleri'
title: C Sonek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: e5e230f1e1e51a1f48b29436705f4f645be9ed44
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300222"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C Sonek Arttırma ve Azaltma İşleçleri

Sonek artırma ve azaltma işleçlerinin işlenenleri, değiştirilebilir l-değerleri olan skaler türlerdir.

## <a name="syntax"></a>Syntax

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Sonek artışı veya azaltma işleminin sonucu işlenenin değeridir. Sonuç alındıktan sonra, işlenenin değeri artırılır (veya azaltılır). Aşağıdaki kod, sonek artışı işlecini gösterir.

```
if( var++ > 0 )
    *p++ = *q++;
```

Bu örnekte, değişken `var` 0 ile karşılaştırılır, sonra artırılır. `var`Arttırılmadan önce pozitifse, sonraki ifade yürütülür. İlk olarak, tarafından işaret edilen nesnenin değeri `q` tarafından işaret edilen nesneye atanır `p` . Ardından, `q` ve `p` artırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sonek artırma ve azaltma Işleçleri: + + ve--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
