---
title: Olağan Aritmetik Dönüştürmeler
ms.date: 11/04/2016
helpviewer_keywords:
- arithmetic conversions [C++]
- type conversion [C++], arithmetic
- operators [C], arithmetic conversions
- data type conversion [C++], arithmetic
- conversions [C++], arithmetic
- arithmetic operators [C++], type conversions
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
ms.openlocfilehash: 7e28c8a234ff840a16228416720ac48763fccc76
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231422"
---
# <a name="usual-arithmetic-conversions"></a>Olağan Aritmetik Dönüştürmeler

Çoğu C işleci, bir ifadenin işlenenlerini ortak bir türe getirmek veya kısa değerleri makine işlemlerinde kullanılan tamsayı boyutuna genişletmek için tür dönüştürmeleri gerçekleştirir. C işleçleri tarafından gerçekleştirilen dönüşümler, belirli işlece ve işlenenin veya işlenenleri türüne bağlıdır. Ancak, birçok işleç integral ve kayan türlerin işlenenleri üzerinde benzer dönüşümler gerçekleştirir. Bu dönüşümler "aritmetik dönüştürmeler" olarak bilinir. Bir işlenen değerinin uyumlu bir türe dönüştürülmesi, değerinde değişikliğe neden olmaz.

Aşağıda özetlenen aritmetik dönüştürmeler "Olağan aritmetik dönüştürmeler" olarak adlandırılır. Bu adımlar yalnızca aritmetik tür bekleyen ikili işleçler için geçerlidir. Amaç, aynı zamanda sonucun türü olan ortak bir tür getirsağlamaktır. Hangi dönüşümlerin gerçekten gerçekleşmekte olduğunu anlamak için, derleyici ifadedeki ikili işlemlere aşağıdaki algoritmayı uygular. Aşağıdaki adımlar öncelik sıralaması değildir.

1. Her iki işlenen de tür ise **`long double`** , diğer işlenen türüne dönüştürülür **`long double`** .

1. Yukarıdaki koşul karşılanmazsa ve her iki işlenen de tür ise **`double`** , diğer işlenen türüne dönüştürülür **`double`** .

1. Yukarıdaki iki koşul karşılanmazsa ve her iki işlenen de tür ise **`float`** , diğer işlenen türüne dönüştürülür **`float`** .

1. Yukarıdaki üç koşul karşılanmazsa (işlenenlerin hiçbiri kayan türlerdeyse), tam sayı dönüştürmeleri işlenenler üzerinde aşağıdaki gibi gerçekleştirilir:

   - Her iki işlenen de tür ise **`unsigned long`** , diğer işlenen türüne dönüştürülür **`unsigned long`** .

   - Yukarıdaki koşul karşılanmazsa ve işlenenin türü **`long`** ve diğeri türü ise **`unsigned int`** , her iki işlenen de türüne dönüştürülür **`unsigned long`** .

   - Yukarıdaki iki koşul karşılanmazsa ve her iki işlenen de tür ise **`long`** , diğer işlenen türüne dönüştürülür **`long`** .

   - Yukarıdaki üç koşul karşılanmazsa ve her iki işlenen de tür ise **`unsigned int`** , diğer işlenen türüne dönüştürülür **`unsigned int`** .

   - Yukarıdaki koşulların hiçbiri karşılanmazsa her iki işlenen de türüne dönüştürülür **`int`** .

Aşağıdaki kod bu dönüştürme kurallarını göstermektedir:

```
float   fVal;
double  dVal;
int   iVal;
unsigned long ulVal;

dVal = iVal * ulVal; /* iVal converted to unsigned long
                      * Uses step 4.
                      * Result of multiplication converted to double
                      */
dVal = ulVal + fVal; /* ulVal converted to float
                      * Uses step 3.
                      * Result of addition converted to double
                      */
```

## <a name="see-also"></a>Ayrıca bkz.

[C Işleçleri](../c-language/c-operators.md)
