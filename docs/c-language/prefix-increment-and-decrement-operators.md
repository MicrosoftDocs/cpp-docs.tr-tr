---
title: Önek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
ms.openlocfilehash: 041c44829b8a267ca053dc85da0333e86db6b7b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325500"
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

## <a name="see-also"></a>Ayrıca bkz.

[C Birli İşleçler](../c-language/c-unary-operators.md)
