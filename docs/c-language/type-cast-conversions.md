---
title: Tür atama dönüştürmeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data type conversion [C++], type-cast conversions
- conversions [C++], type-cast
- type casts
- explicit type conversions
- type casts [C++], about type-cast conversion
- type-cast conversions [C++]
ms.assetid: 57ab5902-f12f-4326-a2f6-6282f1d4025a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a98b49c1533f088ff447f77189a12d2653705420
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751588"
---
# <a name="type-cast-conversions"></a>Tür Atama Dönüştürmeleri

Tür atamaları türleri açıkça dönüştürmek için kullanabilirsiniz.

**Söz dizimi**

*Cast ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birli ifadesi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**(***tür adı***)***atama ifadesi* 

*tür adı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Belirleyicisi niteleyici listesinin* *soyut bildirimci*<sub>iyileştirilmiş</sub>

*Tür adı* bir türdür ve *atama ifadesini* bu türe dönüştürülüp bir değerdir. Bir ifade bir cast türünü içeren bir l değeri değil. *Atama ifadesini* türünde bir değişkene atanmış olsa dönüştürülür *tür adı*. Atamalar için dönüştürme kuralları (özetlenen [atama dönüştürmeleri](../c-language/assignment-conversions.md)) yayınları de yazmak için geçerlidir. Aşağıdaki tablo için belirtilen her türlü atanabilir türleri gösterir.

### <a name="legal-type-casts"></a>Yasal tür atamaları

|Hedef türü|Olası kaynakları|
|-----------------------|-----------------------|
|Tam sayı türleri|Herhangi bir tamsayı türü veya kayan nokta türü veya bir nesne işaretçisi|
|Kayan nokta|Herhangi bir aritmetik tür|
|Bir nesneye bir işaretçi veya (**void** <strong>\*</strong>)|Herhangi bir tamsayı türü (**void** <strong>\*</strong>), bir nesneye bir işaretçi ya da işlev işaretçisi|
|İşlev işaretçisi|Herhangi bir tamsayı türü, bir nesne işaretçisi veya işlev işaretçisi|
|Bir yapı, birlik veya dizi|Yok.|
|Void türü|Herhangi bir türü|

Herhangi bir tanımlayıcı atanabilecek `void` türü. Türü belirtilen ancak, bir tür atama ifadesidir değilse `void`, sonra da tanımlayıcısı olan tür olamaz başvurusuna bir `void` ifade. Herhangi bir ifade atanabilecek `void`, ancak türdeki bir ifade `void` başka bir türüne yayınlanamıyor. Örneğin, bir işlev ile `void` dönüş türünü dönüş başka bir türe sahip olamaz.

Unutmayın bir **void** <strong>\*</strong> ifadesi bir işaretçi türüne sahip `void`, değil yazın `void`. Bir nesne türüne dönüştürülür, `void` türü, sonuçta elde edilen ifade hiçbir öğesine atanamaz. Bu nedenle hiçbir ataması için bir tür atama nesnesi sağlanabilir benzer şekilde, bir tür atama nesnesi bir kabul edilebilir l-değeri değil.

**Microsoft'a özgü**

Tanımlayıcının boyutunu değişmez sürece bir cast türünü bir l-değeri ifade olabilir. L-değeri ifadeleri hakkında daha fazla bilgi için bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md).

**END Microsoft özgü**

Bir ifade türüne dönüştürebilirsiniz `void` bir atama ile ancak sonuçta elde edilen ifade yalnızca bir değer gerekli olduğu kullanılabilir. Bir nesne işaretçisi türüne dönüştürülmüş **void** <strong>\*</strong> ve orijinal türe geri özgün değerine döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Dönüştürmeleri](../c-language/type-conversions-c.md)