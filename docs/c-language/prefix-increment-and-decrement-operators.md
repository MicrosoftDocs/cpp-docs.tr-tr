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

Birli İşleçler (`++` ve **--**), artırma veya azaltma işleçleri işlenenden önce görüntülendiğinde "önek" artışı veya azaltma işleçleri olarak adlandırılır. Sonek artışı ve azaltma, ön ek artışı ve azalma kıyasla daha yüksek önceliğe sahiptir. İşlenen integral, kayan veya işaretçi türüne sahip olmalı ve değiştirilebilir bir l-Value ifadesi ( **const** özniteliği olmayan bir ifade) olmalıdır. Sonuç bir l değeridir.

İşleç işlenenden önce göründüğünde, işlenen artırılır veya azaltılır ve yeni değeri ifadenin sonucudur.

İntegral veya kayan türün işleneni, 1 tamsayı değeri tarafından artırılır veya azaltılır. Sonucun türü, işlenen türüyle aynıdır. İşaretçi türündeki bir işlenen, adreslenen nesnenin boyutuyla artırılır veya azaltılır. Artan bir işaretçi sonraki nesneye işaret eder; azaltma işaretçisi önceki nesneye işaret eder.

## <a name="example"></a>Örnek

Bu örnek, birli ön ek azaltma işlecini gösterir:

```
if( line[--i] != '\n' )
    return;
```

Bu örnekte, bir alt simge `i` olarak kullanılmadan önce değişken azaltılır `line`.

## <a name="see-also"></a>Ayrıca bkz.

[C Birli İşleçler](../c-language/c-unary-operators.md)
