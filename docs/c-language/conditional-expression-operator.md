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

C 'nin bir Üçlü işleci vardır: koşullu ifade işleci (**?:**).

## <a name="syntax"></a>Sözdizimi

*koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal OR ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MANTıKSAL or ifadesi*  **?**  *ifade*  **:**  *koşullu ifade*

*MANTıKSAL or-ifadesi* integral, kayan veya işaretçi türüne sahip olmalıdır. Denklik değerini 0 olarak değerlendirilir. Bir sıra noktası, *MANTıKSAL or ifadesi*izler. İşlenenleri değerlendirmesi şu şekilde devam eder:

- *MANTıKSAL or-ifadesi* 0 ' a eşit değilse, *ifade* değerlendirilir. İfadenin değerlendirilme sonucu, terminal dışı *ifadesi*tarafından verilir. (Bu, *ifadenin* yalnızca *mantıksal or-ifadesi* true ise değerlendirildiği anlamına gelir.)

- *Mantıksal-veya-ifadesi* 0 eşitse *koşullu ifade* değerlendirilir. İfadenin sonucu, *koşullu ifadenin*değeridir. (Bu, *koşullu ifadenin* yalnızca *mantıksal or-ifadesi* false olduğunda değerlendirileceği anlamına gelir.)

Her iki *ifade* veya *koşullu ifade* değerlendirilir, ancak her ikisi birden değildir.

Koşullu bir işlemin sonucunun türü, *ifadenin* veya *koşullu ifade* işleneninin türüne göre aşağıdaki gibi değişir:

- *İfade* veya *koşullu ifadede* integral veya kayan tür varsa (türleri farklı olabilir), operatör her zamanki aritmetik dönüştürmeleri gerçekleştirir. Sonucun türü, dönüştürmeden sonra işlenen türüdür.

- Her iki *ifade* ve *koşullu ifade* aynı yapıya, birleşime veya işaretçi türüne sahip ise, sonucun türü aynı yapı, birleşim veya işaretçi türüdür.

- Her iki işlenen de türüne `void`sahipse, sonucun türü `void`vardır.

- Her iki işlenen de herhangi bir türde nesnenin işaretçisiyse ve diğer işlenen için `void`bir işaretçisiyse, nesne işaretçisi işaretçisine dönüştürülür `void` ve sonuç bir işaretçisidir. `void`

- Herhangi bir *ifade* veya *koşullu ifade* bir işaretçisiyse ve diğer işlenen değeri 0 olan sabit bir ifadesiyse, sonucun türü işaretçi türüdür.

İşaretçiler için tür karşılaştırmasına, işaretçi noktalarının önemli olduğu türdeki**const** tür niteleyicileri `volatile`(const veya), ancak sonuç türü, her iki bileşenden de niteleyicileri devralır.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde koşullu işlecin kullanımları gösterilmektedir:

```
j = ( i < 0 ) ? ( -i ) : ( i );
```

Bu örnek öğesinin `i` mutlak değerini olarak `j`atar. `i` 0 ' dan küçükse, `-i` öğesine `j`atanır. `i` 0 ' dan büyük veya buna eşitse, `i` öğesine `j`atanır.

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

Bu örnekte, ve ' iki işlev `f1` `f2`ve ve iki değişken, `x` ve `y`' i bildirilmiştir. Programın ilerleyen kısımlarında, iki değişken aynı değere sahip ise, işlev `f1` çağrılır. Aksi takdirde `f2` , çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Koşullu İşleç: ? :](../cpp/conditional-operator-q.md)
