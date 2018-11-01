---
title: Önek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
ms.openlocfilehash: 9460d3fda9bca74cd9c95ffa7748a5ddc91e3f78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606940"
---
# <a name="prefix-increment-and-decrement-operators"></a>Önek Arttırma ve Azaltma İşleçleri

Birli işleçler (`++` ve **--**) artırma veya azaltma işleçleri önce işlenen göründüğünde azaltma işleçleri veya "ön eki" artış olarak adlandırılır. Sonek artırma ve azaltma önek artırma ve azaltma daha yüksek önceliğe sahiptir. İşlenen, integral, kayan veya işaretçi türünde olmalıdır ve değiştirilebilir bir l-değeri bir ifade olması gerekir (bir ifade olmadan **const** özniteliği). Sonuç bir l-değerdir.

İşleci, işleneni önce görünür işlenen artırılması veya azaltılması ve kendi yeni değer ifadesi sonucu.

Tamsayı veya kayan türünde bir işlenen, tamsayı değeri 1 artırılması veya azaltılması. Sonuç türü, işlenenin türü ile aynıdır. İşaretçi türünde bir işlenen sıra nesnesi tarafından artırılması veya azaltılması boyutudur. Artan bir işaretçi sonraki nesneye işaret eder; indirildiği işaretçi önceki nesneye işaret eder.

## <a name="example"></a>Örnek

Bu örnekte, birli önek azaltma işleci gösterilmektedir:

```
if( line[--i] != '\n' )
    return;
```

Bu örnekte, değişken `i` için bir alt simge olarak kullanılmadan önce azaltılır `line`.

## <a name="see-also"></a>Ayrıca Bkz.

[C Birli İşleçler](../c-language/c-unary-operators.md)