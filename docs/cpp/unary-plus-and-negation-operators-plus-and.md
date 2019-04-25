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
ms.openlocfilehash: c1d5fc926b396f1ec44b9e44e79721e2ca4a0908
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244174"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Birli Artı ve Değilleme işleçleri: + ve -

## <a name="syntax"></a>Sözdizimi

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ işleci

Tek işlenenli artı sonucunu (**+**), işleneninin değeridir. Tek işlenenli artı işleminin işleneni, aritmetik bir türden olmalıdır.

İntegral işlenenlerde integral yükseltme gerçekleştirilir. Sonuç türü, işlenin yükseltildiği türdür. Bu nedenle, ifade `+ch`burada `ch` türünde **char**, türüyle sonuçlanır **int**; değer değiştirilmez. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl yapılacağı hakkında daha fazla bilgi.

## <a name="--operator"></a>- işleci

Tekli değilleme işleci (**-**), işleneninin negatifini üretir. Tekli değilleme işleci için işlenen, aritmetik bir türü olmalıdır.

İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl gerçekleştirildiğini hakkında daha fazla bilgi.

## <a name="microsoft-specific"></a>Microsoft'a özgü

Tekli olumsuzlama işaretsiz miktarlar, işlenenin 2'den çıkarılmasıyla gerçekleştirilir ^ n, n, bit işaretsiz belirtilen türde bir nesne sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)