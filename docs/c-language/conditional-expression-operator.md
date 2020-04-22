---
title: Koşullu İfade İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
ms.openlocfilehash: a64317c75e48111148053cc7efb62fb5a6d79f7f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749186"
---
# <a name="conditional-expression-operator"></a>Koşullu İfade İşleci

C'nin bir üçüncül işleci vardır: koşullu ifade işleci (**? : ).**

## <a name="syntax"></a>Sözdizimi

*koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-OR-ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-OR ifadesi*  **?**  *expression*  **:**  *koşullu ifade*

*Mantıksal-OR-ifadesi* integral, kayan veya işaretçi türüne sahip olmalıdır. Eşdeğerliği 0 olarak değerlendirilir. Bir sıra noktası *mantıksal-OR-ifade*izler. Operands gelirleri aşağıdaki gibi değerlendirilmesi:

- *Mantıksal-OR-ifade* 0'a eşit değilse, *ifade* değerlendirilir. İfadeyi değerlendirme sonucu nonterminal *ifadesi*ile verilir. (Bu, *ifadenin* yalnızca *mantıksal-OR-ifadesi* doğruysa değerlendirildiği anlamına gelir.)

- *Mantıksal-OR-ifade* 0'a eşitse *koşullu ifade* değerlendirilir. İfadenin sonucu *koşullu ifadenin*değeridir. *(Bu, koşullu ifadenin* yalnızca *mantıksal-OR-ifadesi* yanlışsa değerlendirildiği anlamına gelir.)

*İfade* veya *koşullu ifadenin* değerlendirildiğini, ancak her ikisinin de değerlendirilmediğini unutmayın.

Koşullu bir işlemin sonucunun türü, aşağıdaki gibi *ifade* veya *koşullu ifade* operand türüne bağlıdır:

- *İfade* veya *koşullu ifadenin* integral veya kayan türü varsa (türleri farklı olabilir), işleç olağan aritmetik dönüşümleri gerçekleştirir. Sonucun türü, dönüşümden sonraki operandların türüdür.

- Hem *ifade* hem de *koşullu ifade* aynı yapıya, birliğe veya işaretçi türüne sahipse, sonuç türü aynı yapı, birleşim veya işaretçi türüdür.

- Her iki operands `void`türü varsa, `void`sonuç türü vardır.

- Herhangi bir türdeki bir nesneye işaretçi veya diğer operand bir `void`işaretçi ise, nesnenin işaretçisi `void` bir işaretçiye `void`dönüştürülür ve sonuç bir işaretçiye .

- *İfade* veya *koşullu ifade* bir işaretçi yse ve diğer operand 0 değeri olan sabit bir ifadeyse, sonucun türü işaretçi türüdür.

İşaretçiler için tür karşılaştırmasında, işaretçi noktalarının `volatile`önemsiz olduğu türdeki herhangi bir tür niteleyicisi **(const** veya ) önemsizdir, ancak sonuç türü, koşullu maddenin her iki bileşeninden de varsamaları devralır.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler koşullu işleç kullanımlarını gösterir:

```
j = ( i < 0 ) ? ( -i ) : ( i );
```

Bu örnek, `i` `j`'nin mutlak değerini . `i` 0'dan küçükse, `-i` `j`'ye atanır. 0'dan `i` büyük veya `i` eşitse, `j`.'a atanır.

```cpp
void f1( void );
void f2( void );
int x;
int y;
    .
    .
    .
( x == y ) ? ( f1() ) : ( f2() );
```

Bu örnekte, iki `f1` `f2`işlev ve , `x` ve `y`iki değişken ve , bildirilir. Programın ilerleyen saatlerinde, iki değişken aynı değere sahipse, işlev `f1` çağrılır. Aksi `f2` takdirde, denir.

## <a name="see-also"></a>Ayrıca bkz.

[Koşullu İşleç: ? :](../cpp/conditional-operator-q.md)
