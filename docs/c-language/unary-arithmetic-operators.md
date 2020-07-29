---
title: Birli Aritmetik İşleçler
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
ms.openlocfilehash: 0acbd98e25c05fee6fb5217bf00d80287460dbeb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87189928"
---
# <a name="unary-arithmetic-operators"></a>Birli Aritmetik İşleçler

C birli artı, aritmetik olumsuzlama, tamamlayan ve mantıksal olumsuzlama işleçleri aşağıdaki listede açıklanmıştır:

|İşleç|Açıklama|
|--------------|-----------------|
|**+**|Bir ifadenin başında parantez içinde gelen birli artı işleci, parantez içindeki işlemlerin gruplandırmasını zorlar. Birden fazla ilişkilendirilebilir veya değiştirebilir ikili işleç içeren ifadelerle kullanılır. İşlenen, aritmetik türde olmalıdır. Sonuç, işlenenin değeridir. Bir integral işlenen, integral yükseltme uygulanır. Sonucun türü yükseltilen işlenenin türüdür.|
|**-**|Aritmetik olumsuzlama işlevi, işleneninin negatifini (ikinin tamamlayıcısı) üretir. İşlenen, bir tamsayı veya kayan değer olmalıdır. Bu işleç, her zamanki aritmetik dönüştürmeleri gerçekleştirir.|
|`~`|Bitwise-complement (veya bitwise-NOT) işleci, işlenenin bit seviyesinde tamamlayıcısını üretir. İşlenen, tamsayı türünde olmalıdır. Bu işleç, her zamanki aritmetik dönüşümleri gerçekleştirir; sonuç, dönüştürme işleminden sonra işlenenin türündendir.|
|**!**|logical-negation (logical-NOT) işleci, işleneni doğru ise (sıfır dışında bir değer) 0 değerini üretir, işleneni yanlış ise (0) 1 değerini üretir. Sonucun türü vardır **`int`** . İşlenen; bir tamsayı, kayan değer veya işaretçi değer olmalıdır.|

İşaretçilerde birli aritmetik işlemler geçersizdir.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde birli aritmetik işleçler gösterilmektedir:

```
short x = 987;
    x = -x;
```

Yukarıdaki örnekte, yeni değeri `x` 987 veya-987 ' nin negatiftir.

```
unsigned short y = 0xAAAA;
    y = ~y;
```

Bu örnekte, `y` öğesine atanan yeni değer, 0xAAAA veya 0x5555 değerine ilişkin birin tamamlayanıdır.

```
if( !(x < y) )
```

`x`, `y` öğesine eşit veya ondan büyükse, ifadenin sonucu 1'dir (doğru). `x`, `y` öğesinden küçükse, sonuç 0'dır (yanlış).

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)
