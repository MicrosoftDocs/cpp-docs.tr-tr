---
title: Koşullu İfade İşleci
ms.date: 11/04/2016
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
ms.openlocfilehash: 9dc93a47d36af92fe370e3f56f504682d49bd1dd
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150629"
---
# <a name="conditional-expression-operator"></a>Koşullu İfade İşleci

C sahip bir Üçlü işleç: koşullu ifade işleci (**?:**).

## <a name="syntax"></a>Sözdizimi

*Koşullu ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mantıksal-veya-ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Mantıksal OR ifadesi***?**  *ifade***:***koşullu ifade*

*Mantıksal-veya-expression* integral, kayan veya işaretçi türünde olmalıdır. 0, denklik açısından değerlendirilir. Bir dizi noktası izleyen *mantıksal-veya-expression*. İşlenenlerin gibi çalışır:

- Varsa *mantıksal-veya-expression* 0'a eşit değil *ifade* değerlendirilir. İfade değerlendirmesinin sonucu bildirimlere verilen *ifade*. (Yani *ifade* yalnızca değerlendirilir *mantıksal-veya-expression* geçerlidir.)

- Varsa *mantıksal-veya-expression* eşittir 0, *koşullu ifade* değerlendirilir. İfadenin sonucu değeri *koşullu ifade*. (Yani *koşullu ifade* yalnızca değerlendirilir *mantıksal-veya-expression* false'tur.)

Ya da unutmayın *ifade* veya *koşullu ifade* değerlendirilir, ancak ikisi birden değil.

Koşullu bir işlemin sonucunu türünü türüne bağlıdır *ifade* veya *koşullu ifade* işleneni aşağıdadır:

- Varsa *ifade* veya *koşullu ifade* integral sahip veya bu (türleri farklı) kayan türü işleç olağan aritmetik dönüştürmeler gerçekleştirir. Sonuç türü dönüştürme işleminden sonra işlenenler türüdür.

- Her iki *ifade* ve *koşullu ifade* aynı yapı, birleşim veya işaretçi türü sonuç türü, aynı yapıya, birleşim veya işaretçi türüne sahip.

- Her iki işlenen türü varsa `void`, sonuç türünde `void`.

- İki işlenenden herhangi türde bir nesne işaretçisidir ve diğer işlenenin işaretçisidir `void`, işaretçiyi nesneye bir işaretçiye dönüştürülür `void` ve sonucu bir işaretçiye `void`.

- Ya da *ifade* veya *koşullu ifade* bir işaretçi ise diğer işlenen değeri 0 ' sonuç türü olan bir sabit ifade ise işaretçi türü.

İşaretçileri tür Karşılaştırmada niteleyicileri yazın (**const** veya `volatile`) türünde hangi ukazatel ukazuje Önemsiz, ancak sonuç türü niteleyicileri her iki koşul bileşenlerini devralır.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, koşullu işleç kullanımlarını gösterir:

```
j = ( i < 0 ) ? ( -i ) : ( i );
```

Bu örnekte mutlak değerini atar `i` için `j`. Varsa `i` 0'dan küçük `-i` atandığı `j`. Varsa `i` değerinden büyükse veya eşitse 0 `i` atandığı `j`.

```
void f1( void );
void f2( void );
int x;
int y;
    .
    .
    .
( x == y ) ? ( f1() ) : ( f2() );
```

Bu örnekte, iki işlev `f1` ve `f2`ve iki değişken `x` ve `y`, bildirilir. Programda daha sonra iki değişken aynı değeri, işlev varsa `f1` çağrılır. Aksi takdirde, `f2` çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Koşullu İşleç: ? :](../cpp/conditional-operator-q.md)
