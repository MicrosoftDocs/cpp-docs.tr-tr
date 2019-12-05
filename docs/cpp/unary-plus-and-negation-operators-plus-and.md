---
title: 'Birli Artı ve Değilleme işleçleri: + ve -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
ms.openlocfilehash: 83fedd9d3cc6cd7c08ba79d2ed83e9f62d919e29
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857248"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Birli Artı ve Değilleme işleçleri: + ve -

## <a name="syntax"></a>Sözdizimi

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ işleci

Birli artı işlecinin sonucu ( **+** ), işleneninin değeridir. Tek işlenenli artı işleminin işleneni, aritmetik bir türden olmalıdır.

İntegral işlenenlerde integral yükseltme gerçekleştirilir. Sonuç türü, işlenin yükseltildiği türdür. Bu nedenle, `ch` **char**türünde olduğu `+ch`ifade, **int**türünde sonuçlar; değer değiştirilmemiş. Yükseltmenin nasıl yapıldığı hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

## <a name="--operator"></a>- işleci

Birli olumsuzlama işleci ( **-** ) işleneninin negatifini üretir. Birli olumsuzlama işlecinin işleneni bir aritmetik tür olmalıdır.

İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Yükseltmenin nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

**Microsoft 'a özgü**

İşaretsiz miktarların birli Olumsuzlaştırma değeri 2 ^ n ' den işlenenin değerinin çıkarılmasıyla gerçekleştirilir; burada n, verili işaretsiz türdeki bir nesnedeki bitlerin sayısıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)