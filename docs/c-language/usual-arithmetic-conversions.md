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
ms.openlocfilehash: 729e173c695db3b4970490e84bedfd441e6ff6d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344843"
---
# <a name="usual-arithmetic-conversions"></a>Olağan Aritmetik Dönüştürmeler

Çoğu C işleci, bir ifadenin işlenenlerini ortak bir türe getirmek veya kısa değerleri makine işlemlerinde kullanılan tamsayı boyutuna genişletmek için tür dönüştürmeleri gerçekleştirir. C işleçleri tarafından gerçekleştirilen dönüşümler, belirli işlece ve işlenenin veya işlenenleri türüne bağlıdır. Ancak, birçok işleç integral ve kayan türlerin işlenenleri üzerinde benzer dönüşümler gerçekleştirir. Bu dönüşümler "aritmetik dönüştürmeler" olarak bilinir. Bir işlenen değerinin uyumlu bir türe dönüştürülmesi, değerinde değişikliğe neden olmaz.

Aşağıda özetlenen aritmetik dönüştürmeler "Olağan aritmetik dönüştürmeler" olarak adlandırılır. Bu adımlar yalnızca aritmetik tür bekleyen ikili işleçler için geçerlidir. Amaç, aynı zamanda sonucun türü olan ortak bir tür getirsağlamaktır. Hangi dönüşümlerin gerçekten gerçekleşmekte olduğunu anlamak için, derleyici ifadedeki ikili işlemlere aşağıdaki algoritmayı uygular. Aşağıdaki adımlar öncelik sıralaması değildir.

1. Her iki işlenen de tür `long double`ise, diğer işlenen türüne `long double`dönüştürülür.

1. Yukarıdaki koşul karşılanmazsa ve her iki işlenen de **Double**türünde ise, diğer işlenen **Double**türüne dönüştürülür.

1. Yukarıdaki iki koşul karşılanmazsa ve her iki işlenen de **float**türünde ise, diğer işlenen **float**türüne dönüştürülür.

1. Yukarıdaki üç koşul karşılanmazsa (işlenenlerin hiçbiri kayan türlerdeyse), tam sayı dönüştürmeleri işlenenler üzerinde aşağıdaki gibi gerçekleştirilir:

   - Her iki işlenen de tür `unsigned long`ise, diğer işlenen türüne `unsigned long`dönüştürülür.

   - Yukarıdaki koşul karşılanmazsa ve her iki işlenen de **Long** ve türün `unsigned int`diğer türü ise, her iki işlenen de türüne `unsigned long`dönüştürülür.

   - Yukarıdaki iki koşul karşılanmazsa ve her iki işlenen de **Long**türünde ise, diğer işlenen de **Long**türüne dönüştürülür.

   - Yukarıdaki üç koşul karşılanmazsa ve her iki işlenen de tür `unsigned int`ise, diğer işlenen türüne `unsigned int`dönüştürülür.

   - Yukarıdaki koşulların hiçbiri karşılanmazsa her iki işlenen de türüne `int`dönüştürülür.

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
