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

Çoğu C işleçleri, bir ifadenin işlenenleri için ortak tür getirin veya makine işlemlerde tamsayı boyuta kısa değerler genişletmek için tür dönüştürmeleri gerçekleştirir. C işleçleri tarafından gerçekleştirilen dönüştürmeler belirli işleci ve işlenenleri ve işlenen türü bağlıdır. Ancak, işleçlerinin çoğu, integral ve kayan türler işlenenlerde benzer dönüşümleri gerçekleştirir. Bu dönüştürmeleri "aritmetik dönüştürmeler" denir. Uyumlu bir türe dönüştürme bir işlenen değerinin değerine değişikliğe neden olmaz.

Aşağıda özetlenen aritmetik dönüştürmeler "olağan aritmetik dönüştürmeler." olarak adlandırılır Bu adımlar, aritmetik türde beklediğiniz ikili işleçler için uygulanır. Amacı, aynı zamanda sonuç türü olan genel bir türü sonucu veren sağlamaktır. Hangi dönüştürmeler gerçekten gerçekleşmesi belirlemek için derleyici aşağıdaki algoritmadan ifadesinde ikili işlemler uygulanır. Aşağıdaki adımlar bir öncelik sırası değildir.

1. İki işlenenden türü ise `long double`, diğer işlenen türüne dönüştürülür `long double`.

1. Yukarıdaki koşul karşılanmamıştır ve işlenenlerden türünde **çift**, diğer işlenen türüne dönüştürülür **çift**.

1. Yukarıdaki koşullar karşılanmadı ve iki işlenenden türünde **float**, diğer işlenen türüne dönüştürülür **float**.

1. Yukarıdaki üç koşul karşılanmazsa (işlenenlerden hiçbiri olan kayan türlerden) tamsayı dönüştürmeleri işlenenler üzerinde aşağıdaki gibi gerçekleştirilir:

   - İki işlenenden türü ise `unsigned long`, diğer işlenen türüne dönüştürülür `unsigned long`.

   - Yukarıdaki koşul karşılanmamıştır ve işlenenlerden türünde **uzun** ve diğer tür `unsigned int`, her iki işlenen de türüne dönüştürülür `unsigned long`.

   - Yukarıdaki koşullar karşılanmadı ve iki işlenenden türünde **uzun**, diğer işlenen türüne dönüştürülür **uzun**.

   - Yukarıdaki üç koşulları karşılanmadı ve iki işlenenden türünde `unsigned int`, diğer işlenen türüne dönüştürülür `unsigned int`.

   - Yukarıdaki koşulların hiçbiri karşılanırsa, her iki işlenen de türüne dönüştürülür `int`.

Aşağıdaki kod bu dönüştürme kuralları gösterilmektedir:

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

[C İşleçleri](../c-language/c-operators.md)
