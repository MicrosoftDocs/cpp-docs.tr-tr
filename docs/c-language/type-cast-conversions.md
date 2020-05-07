---
title: Tür Atama Dönüştürmeleri
ms.date: 11/04/2016
helpviewer_keywords:
- data type conversion [C++], type-cast conversions
- conversions [C++], type-cast
- type casts
- explicit type conversions
- type casts [C++], about type-cast conversion
- type-cast conversions [C++]
ms.assetid: 57ab5902-f12f-4326-a2f6-6282f1d4025a
ms.openlocfilehash: d54e4c15f84ccecad629d48341e5d3ae26d8cecf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344947"
---
# <a name="type-cast-conversions"></a>Tür Atama Dönüştürmeleri

Türleri açıkça dönüştürmek için tür atamaları kullanabilirsiniz.

**Sözdizimi**

*Cast ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Birli ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(**  *tür adı*  **)**  *Cast ifadesi*

*tür adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*belirtici niteleyicisi-List* *abstract-declarator*<sub>opt</sub>

*Tür-adı* bir tür ve *atama ifadesi* bu türe dönüştürülecek bir değerdir. Tür dönüştürme içeren bir ifade, l değeri değildir. *Cast ifadesi* *tür-adı*türünde bir değişkene atanmış olmasına rağmen dönüştürülür. Atamalar için dönüştürme kuralları ( [atama dönüştürmelerinde](../c-language/assignment-conversions.md)özetlenmiştir) tür yayınlarına de uygulanır. Aşağıdaki tabloda, verilen herhangi bir türe tür atama yapılabilir türler gösterilmektedir.

### <a name="legal-type-casts"></a>Yasal tür yayınları

|Hedef türleri|Olası kaynaklar|
|-----------------------|-----------------------|
|Integral türleri|Herhangi bir tamsayı türü veya kayan nokta türü ya da bir nesne işaretçisi|
|Kayan nokta|Herhangi bir aritmetik tür|
|Bir nesne işaretçisi veya (**void** <strong>\*</strong>)|Herhangi bir tamsayı türü, (**void** <strong>\*</strong>), bir nesne işaretçisi veya işlev işaretçisi|
|İşlev işaretçisi|Herhangi bir integral türü, bir nesnenin işaretçisi veya bir işlev işaretçisi|
|Bir yapı, birleşim veya dizi|Yok|
|Void türü|Herhangi bir tür|

Herhangi bir tanımlayıcı `void` türüne atanabilir. Ancak, bir tür atama ifadesinde belirtilen tür yoksa `void`, bu türe dönüştürmenin tanımlayıcısı bir `void` ifade olamaz. Herhangi bir ifade öğesine `void`dönüşebilir, ancak türündeki `void` bir ifade başka bir türe atanamaz. Örneğin, dönüş türü olan `void` bir işlevin dönüş, başka bir türe dönüşme türüne sahip olamaz.

**Void** <strong>\*</strong> ifadesinin türü işaretçi değil `void`, türüne sahip olduğunu unutmayın. `void` Bir nesne `void` türüne yayınlandıysanız, sonuçta elde edilen ifade herhangi bir öğeye atanamaz. Benzer şekilde, bir tür dönüştürme nesnesi kabul edilebilir bir l değeri değildir, bu nedenle tür atama nesnesine atama yapılamaz.

**Microsoft'a Özgü**

Tanımlayıcı boyutu değişmez olduğu sürece tür dönüştürme bir l-Value ifadesi olabilir. L-Value ifadeleri hakkında daha fazla bilgi için bkz. [l-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md).

**SON Microsoft 'a özgü**

Bir ifadeyi Cast ile türüne `void` dönüştürebilirsiniz, ancak sonuç ifadesi yalnızca bir değer gerekli olmadığı durumlarda kullanılabilir. Bir nesne işaretçisi, **void** <strong>\*</strong> değerine dönüştürüldü ve özgün türe geri döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Dönüştürmeleri](../c-language/type-conversions-c.md)
