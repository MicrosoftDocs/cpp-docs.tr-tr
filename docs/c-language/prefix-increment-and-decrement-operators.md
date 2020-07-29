---
title: Önek Arttırma ve Azaltma İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
ms.openlocfilehash: dbbace9780ab96891ceb85f885335e42c577fda1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211729"
---
# <a name="prefix-increment-and-decrement-operators"></a>Önek Arttırma ve Azaltma İşleçleri

Birli İşleçler ( `++` ve **--** ), artırma veya azaltma işleçleri işlenenden önce görüntülendiğinde "önek" artışı veya azaltma işleçleri olarak adlandırılır. Sonek artışı ve azaltma, ön ek artışı ve azalma kıyasla daha yüksek önceliğe sahiptir. İşlenen integral, kayan veya işaretçi türüne sahip olmalı ve değiştirilebilir bir l-Value ifadesi (özniteliği olmayan bir ifade **`const`** ) olmalıdır. Sonuç bir l değeridir.

İşleç işlenenden önce göründüğünde, işlenen artırılır veya azaltılır ve yeni değeri ifadenin sonucudur.

İntegral veya kayan türün işleneni, 1 tamsayı değeri tarafından artırılır veya azaltılır. Sonucun türü, işlenen türüyle aynıdır. İşaretçi türündeki bir işlenen, adreslenen nesnenin boyutuyla artırılır veya azaltılır. Artan bir işaretçi sonraki nesneye işaret eder; azaltma işaretçisi önceki nesneye işaret eder.

## <a name="example"></a>Örnek

Bu örnek, birli ön ek azaltma işlecini gösterir:

```
if( line[--i] != '\n' )
    return;
```

Bu örnekte, `i` bir alt simge olarak kullanılmadan önce değişken azaltılır `line` .

## <a name="see-also"></a>Ayrıca bkz.

[C birli Işleçler](../c-language/c-unary-operators.md)
