---
description: 'Daha fazla bilgi edinin: birli artı ve değilleme Işleçleri: + ve-'
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
ms.openlocfilehash: 64478ccfa9191e5704c1e3c896b17bc0986dc0e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145775"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Birli Artı ve Değilleme işleçleri: + ve -

## <a name="syntax"></a>Syntax

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ işleci

Birli artı işlecinin sonucu ( **+** ), işleneninin değeridir. Tek işlenenli artı işleminin işleneni, aritmetik bir türden olmalıdır.

İntegral işlenenlerde integral yükseltme gerçekleştirilir. Sonuç türü, işlenin yükseltildiği türdür. Bu nedenle, öğesinin `+ch` `ch` türü olan ifadesi, **`char`** türü ile sonuçlanır **`int`** ; değer değiştirilmemiş olur. Yükseltmenin nasıl yapıldığı hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

## <a name="--operator"></a>- işleci

Birli olumsuzlama işleci ( **-** ) işleneninin negatifini üretir. Birli olumsuzlama işlecinin işleneni bir aritmetik tür olmalıdır.

İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Yükseltmenin nasıl gerçekleştirildiği hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

**Microsoft'a Özgü**

İşaretsiz miktarların birli Olumsuzlaştırma değeri 2 ^ n ' den işlenenin değerinin çıkarılmasıyla gerçekleştirilir; burada n, verili işaretsiz türdeki bir nesnedeki bitlerin sayısıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
