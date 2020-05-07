---
title: C Sonek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: 8c2e3ba50ce3e768b377a588cd3e82ad29df79ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325581"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C Sonek Arttırma ve Azaltma İşleçleri

Sonek artırma ve azaltma işleçlerinin işlenenleri, değiştirilebilir l-değerleri olan skaler türlerdir.

## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Sonek artışı veya azaltma işleminin sonucu işlenenin değeridir. Sonuç alındıktan sonra, işlenenin değeri artırılır (veya azaltılır). Aşağıdaki kod, sonek artışı işlecini gösterir.

```
if( var++ > 0 )
    *p++ = *q++;
```

Bu örnekte, değişken `var` 0 ile karşılaştırılır, sonra artırılır. `var` Arttırılmadan önce pozitifse, sonraki ifade yürütülür. İlk olarak, tarafından `q` işaret edilen nesnenin değeri tarafından `p`işaret edilen nesneye atanır. Ardından, `q` ve `p` artırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Son Ek Arttırma ve Azaltma İşleçleri: ++ ve --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
