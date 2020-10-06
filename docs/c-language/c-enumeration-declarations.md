---
title: C numaralandırma bildirimleri
description: C programlama dilinde numaralandırma bildirimleri.
ms.date: 10/02/2020
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
ms.openlocfilehash: b7df41475a630b9f6e1d735f5454f6d9601cdd16
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765205"
---
# <a name="c-enumeration-declarations"></a>C numaralandırma bildirimleri

Sabit listesi bir adlandırılmış tamsayı sabitleri kümesinden oluşur. Bir numaralandırma türü bildirimi (isteğe bağlı) numaralandırma etiketinin adını verir. Ayrıca, adlandırılmış tamsayı tanımlayıcılarının kümesini tanımlar ( *numaralandırma kümesi*, *Numaralandırıcı sabitleri*, *Numaralandırıcılar*veya *Üyeler*olarak adlandırılır). Sabit listesi türünün bir değişkeni, bu tür tarafından tanımlanan numaralandırma kümesinin değerlerinden birini depolar.

Türündeki değişkenler, **`enum`** Dizin oluşturma ifadelerinde ve tüm aritmetik ve ilişkisel işleçlerin işlenenleri olarak kullanılabilir. Numaralandırmalar, ön işlemci yönergesine bir alternatif sağlar `#define` ve bunlar sizin için değerlerin üretibileceği ve normal kapsam kurallarına Uyama avantajları sağlar.

ANSI C 'de, bir Numaralandırıcı sabitinin değerini tanımlayan ifadeler her zaman **`int`** tür içermelidir. Bu, bir numaralandırma değişkeniyle ilişkilendirilen depolamanın tek bir değer için gereken depolama alanı olduğu anlamına gelir **`int`** . Sabit Listesi sabiti veya numaralandırılmış türdeki bir değer, C dilinin bir tamsayı ifadesine izin verdiği her yerde kullanılabilir.

## <a name="syntax"></a>Sözdizimi

*`enum-specifier`*:\
&emsp;**`enum`***`identifier`* <sub>opt</sub> **`{`** opt *`enumerator-list`***`}`**\
&emsp;**`enum`** *`identifier`*

*`enumerator-list`*:\
&emsp;*`enumerator`*\
&emsp;*`enumerator-list`* **`,`** *`enumerator`*

*`enumerator`*:\
&emsp;*`enumeration-constant`*\
&emsp;*`enumeration-constant`* **`=`** *`constant-expression`*

*`enumeration-constant`*:\
&emsp;*`identifier`*

İsteğe bağlı *`identifier`* ad, tarafından tanımlanan numaralandırma türüdür *`enumerator-list`* . Bu tanımlayıcı genellikle liste tarafından belirtilen numaralandırmanın "Tag" olarak adlandırılır. Bir tür Belirleyicisi, `identifier` *`enumerator-list`* burada görüldüğü gibi, nonterminalle belirtilen numaralandırmanın etiketini bildirir:

```C
enum identifier
{
    // enumerator-list
}
```

, *`enumerator-list`* Numaralandırma kümesinin üyelerini tanımlar.

Bir etiketin bildirimi görünür durumdaysa, daha sonra etiketi kullanan, ancak atlayan daha *`enumerator-list`* önce belirtilen numaralandırılmış türü belirten bildirimler. Etiket tanımlı bir numaralandırma türüne başvurmalıdır ve bu numaralandırma türü geçerli kapsamda olmalıdır. Numaralandırma türü başka bir yerde tanımlandığından, *`enumerator-list`* Bu bildirimde görünmez. Sabit listesi türleri için Numaralandırmalardan ve bildirimlerden türetilen türlerin bildirimleri numaralandırma **`typedef`** türü tanımlanmadan önce numaralandırma etiketini kullanabilir.

Her *`enumeration-constant`* birinde *`enumerator-list`* , numaralandırma kümesinin bir değeri. Varsayılan olarak, ilki *`enumeration-constant`* 0 değeriyle ilişkilendirilir. *`enumeration-constant`* Listede bir sonraki, *`constant-expression`* açıkça başka bir değerle ilişkilendirmediğiniz takdirde, (+ 1) değeri ile ilişkilendirilir. Öğesinin adı *`enumeration-constant`* değerine eşdeğerdir.

*`enumeration-constant`*  =  *`constant-expression`* Varsayılan değer sırasını geçersiz kılmak için kullanabilirsiniz. Diğer bir deyişle, *`enumeration-constant`*  =  *`constant-expression`* öğesinde görüntüleniyorsa, *`enumerator-list`* *`enumeration-constant`* tarafından verilen değeriyle ilişkilendirilir *`constant-expression`* . , *`constant-expression`* Türünde olmalı **`int`** ve negatif olabilir.

Aşağıdaki kurallar, bir numaralandırma kümesinin üyeleri için geçerlidir:

- Sabit Listesi kümesi, yinelenen sabit değerler içerebilir. Örneğin, 0 değerini iki farklı tanımlayıcı ile ilişkilendirebilirsiniz, örneğin, ve adlı Üyeler `null` `zero` aynı küme içinde.

- Numaralandırma listesindeki tanımlayıcıların aynı kapsamda bulunan diğer tanımlayıcılardan farklı olması gerekir. Bu, diğer numaralandırma listelerindeki normal değişken adlarını ve tanımlayıcıları içerir.

- Numaralandırma etiketleri normal kapsam kurallarına uyar. Aynı görünürlüğe sahip diğer numaralandırma, yapı ve birleşim etiketlerinden farklı olmaları gerekir.

## <a name="examples"></a>Örnekler

Bu örnekler, numaralandırma bildirimlerini gösterir:

```C
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

```C
enum DAY today = wednesday;
```

Sabit Listesi sabitinin adı değeri atamak için kullanılır. `DAY`Numaralandırma türü daha önce bildirildiği için yalnızca numaralandırma etiketi `DAY` gereklidir.

Numaralandırılmış veri türü değişkenine açıkça bir tam sayı değeri atamak için tür dönüştürme kullanın:

```C
workday = ( enum DAY ) ( day_value - 1 );
```

Bu atama C 'de önerilir, ancak gerekli değildir.

```C
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */
{
    false,     /* false = 0, true = 1 */
    true
};

enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */
```

Bu bildirim aynı zamanda şu şekilde belirtilebilir

```C
enum BOOLEAN { false, true } end_flag, match_flag;\
```

veya as

```C
enum BOOLEAN { false, true } end_flag;
enum BOOLEAN match_flag;
```

Bu değişkenleri kullanan bir örnek şöyle görünebilir:

```C
if ( match_flag == false )
    {
     .
     .   /* statement */
     .
    }
    end_flag = true;
```

Adlandırılmamış Numaralandırıcı veri türleri de bildirilebilecek. Veri türünün adı atlanmış, ancak değişkenler bildirilebilecek. Değişken, `response` tanımlı tür değişkenidir:

```C
enum { yes, no } response;
```

## <a name="see-also"></a>Ayrıca bkz.

[Listelemeler](../cpp/enumerations-cpp.md)
