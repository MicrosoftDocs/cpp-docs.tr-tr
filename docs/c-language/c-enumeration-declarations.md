---
title: C Numaralandırma Bildirimleri
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
ms.openlocfilehash: d917c93ab8ef2e896f3ef09c9d9191dae49116c3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213729"
---
# <a name="c-enumeration-declarations"></a>C Numaralandırma Bildirimleri

Sabit listesi bir adlandırılmış tamsayı sabitleri kümesinden oluşur. Sabit listesi türü bildirimi, (isteğe bağlı) numaralandırma etiketinin adını verir ve adlandırılmış tamsayı tanımlayıcılarının kümesini tanımlar ("numaralandırma kümesi," "Numaralandırıcı sabitleri," "Numaralandırıcılar" veya "Üyeler" olarak adlandırılır). Numaralandırma türüne sahip bir değişken, bu tür tarafından tanımlanan numaralandırma kümesinin değerlerinden birini depolar.

Türündeki değişkenler, **`enum`** Dizin oluşturma ifadelerinde ve tüm aritmetik ve ilişkisel işleçlerin işlenenleri olarak kullanılabilir. Numaralandırmalar, ön işlemci yönergesine bir alternatif sağlar `#define` ve bunlar sizin için değerlerin üretibileceği ve normal kapsam kurallarına Uyama avantajları sağlar.

ANSI C 'de, bir Numaralandırıcı sabitinin değerini tanımlayan ifadeler her zaman türünde olur; bu **`int`** nedenle, bir numaralandırma değişkeniyle ilişkili depolama alanı tek bir değer için gereken depolama alanı olur **`int`** . Sabit Listesi sabiti veya numaralandırılmış türdeki bir değer, C dilinin bir tamsayı ifadesine izin verdiği her yerde kullanılabilir.

## <a name="syntax"></a>Syntax

*sabit listesi belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`enum`***tanımlayıcı*<sub>opt</sub> **{** *Numaralandırıcı-listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`enum`***tanımlayıcı*

İsteğe bağlı *tanımlayıcı* , *Numaralandırıcı listesi*tarafından tanımlanan numaralandırma türünü adlandırır. Bu tanımlayıcı genellikle liste tarafından belirtilen numaralandırmanın "Tag" olarak adlandırılır. Formun tür Belirleyicisi

```
enum identifier
{
    enumerator-list
}
```

*tanımlayıcıyı* , *Numaralandırıcı listesi* olmayan Terminal tarafından belirtilen numaralandırmanın etiketi olacak şekilde bildirir. *Numaralandırıcı-listesi* , "Numaralandırıcı içeriği" tanımlar. *Numaralandırıcı listesi* aşağıda ayrıntılı olarak açıklanmıştır.

Bir etiketin bildirimi görünür durumdaysa etiketi kullanan, ancak *Numaralandırıcı olmayan* sonraki bildirimler, önceden tanımlanmış numaralandırılmış türü belirtir. Etiket tanımlı bir numaralandırma türüne başvurmalıdır ve bu numaralandırma türü geçerli kapsamda olmalıdır. Numaralandırma türü başka bir yerde tanımlandığından, *Numaralandırıcı listesi* Bu bildirimde görünmüyor. Sabit listesi türleri için Numaralandırmalardan ve bildirimlerden türetilen türlerin bildirimleri numaralandırma **`typedef`** türü tanımlanmadan önce numaralandırma etiketini kullanabilir.

## <a name="syntax"></a>Syntax

*Numaralandırıcı-liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sının*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı-liste* **,** *Numaralandırıcı*

*Numaralandırıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi-sabit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sabit listesi-sabit* **=** *sabit ifadesi*

sabit *listesi-sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Tanımlayıcısını*

*Sabit listesi listesindeki* her *numaralandırma sabiti* , numaralandırma kümesinin bir değerini adlandırır. Varsayılan olarak, ilk *sabit listesi-sabit* değeri 0 ile ilişkilendirilir. Listedeki bir sonraki *sabit* listesi, açıkça başka bir değerle ilişkilendirmediğiniz takdirde ( *sabit ifade* + 1) değeri ile ilişkilendirilir. Sabit *listesinin* adı, değerine eşdeğerdir.

Varsayılan değer sırasını geçersiz kılmak için sabit *listesi-sabit = sabit ifadesi* kullanabilirsiniz. Bu nedenle, *numaralandırma-sabit = sabit ifadesi* *Numaralandırıcı-listesinde*görünürse, sabit *ifade*tarafından verilen değer *numaralandırma sabiti* ile ilişkilendirilir. *Sabit ifadesinin* **`int`** türü olmalıdır ve negatif olabilir.

Aşağıdaki kurallar, bir numaralandırma kümesinin üyeleri için geçerlidir:

- Sabit Listesi kümesi, yinelenen sabit değerler içerebilir. Örneğin, 0 değerini `null` aynı küme içinde ve adında iki farklı tanımlayıcı ile ilişkilendirebilirsiniz `zero` .

- Numaralandırma listesindeki tanımlayıcılar, diğer numaralandırma listelerindeki sıradan değişken adları ve tanımlayıcılar dahil olmak üzere aynı kapsamda bulunan diğer tanımlayıcılardan farklı olmalıdır.

- Numaralandırma etiketleri normal kapsam kurallarına uyar. Aynı görünürlüğe sahip diğer numaralandırma, yapı ve birleşim etiketlerinden farklı olmaları gerekir.

## <a name="examples"></a>Örnekler

Bu örnekler, numaralandırma bildirimlerini gösterir:

```
enum DAY            /* Defines an enumeration type    */
{
    saturday,       /* Names day and declares a       */
    sunday = 0,     /* variable named workday with    */
    monday,         /* that type                      */
    tuesday,
    wednesday,      /* wednesday is associated with 3 */
    thursday,
    friday
} workday;
```

0 değeri, `saturday` Varsayılan olarak ile ilişkilendirilir. Tanımlayıcı `sunday` açıkça 0 olarak ayarlanır. Kalan tanımlayıcılara varsayılan olarak 1 ila 5 değeri verilir.

Bu örnekte, bir kümeden bir değer `DAY` değişkenine atanır `today` .

```
enum DAY today = wednesday;
```

Sabit Listesi sabiti adının değeri atamak için kullanıldığını unutmayın. `DAY`Numaralandırma türü daha önce bildirildiği için yalnızca numaralandırma etiketi `DAY` gereklidir.

Numaralandırılmış veri türü değişkenine açıkça bir tam sayı değeri atamak için tür dönüştürme kullanın:

```
workday = ( enum DAY ) ( day_value - 1 );
```

Bu atama C 'de önerilir, ancak gerekli değildir.

```
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */
{
    false,     /* false = 0, true = 1 */
    true
};

enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */
```

Bu bildirim aynı zamanda şu şekilde belirtilebilir

```
enum BOOLEAN { false, true } end_flag, match_flag;\
```

veya as

```
enum BOOLEAN { false, true } end_flag;
enum BOOLEAN match_flag;
```

Bu değişkenleri kullanan bir örnek şöyle görünebilir:

```
if ( match_flag == false )
    {
     .
     .   /* statement */
     .
    }
    end_flag = true;
```

Adlandırılmamış Numaralandırıcı veri türleri de bildirilebilecek. Veri türünün adı atlanmış, ancak değişkenler bildirilebilecek. Değişken, `response` tanımlı tür değişkenidir:

```
enum { yes, no } response;
```

## <a name="see-also"></a>Ayrıca bkz.

[Numaralandırmalar](../cpp/enumerations-cpp.md)
