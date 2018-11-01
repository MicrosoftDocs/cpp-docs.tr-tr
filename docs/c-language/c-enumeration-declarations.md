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
ms.openlocfilehash: a1c584b324aced32fea6b1b87b9744dedeaa4e5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474262"
---
# <a name="c-enumeration-declarations"></a>C Numaralandırma Bildirimleri

Bir numaralandırma, adlandırılmış tamsayı sabitleri kümesinden oluşur. Bir numaralandırma türü bildirimi numaralandırması (isteğe bağlı) etiketin adını verir ve adlandırılmış tamsayı tanımlayıcıları kümesini tanımlar ("sabit listesi,"Numaralandırıcı sabitler,"Ayarla" adlı "numaralandırıcılar" veya "üyeleri"). Numaralandırma türüne sahip bir değişken türü tarafından tanımlanan numaralandırma kümesinin değerlerinden depolar.

Değişkenler `enum` tür ifadeleri dizin oluşturma ve tüm aritmetik ve ilişkisel işleçler işleneni olarak kullanılabilir. Numaralandırmalar bir alternatif sağlayan `#define` değerleri sizin için oluşturulan ve normal kapsam kurallara uyan avantajları önişlemci yönergesi.

ANSI C, numaralandırıcı sabitinin değeri her zaman tanımlamak ifadeler sahip `int` yazın; bu nedenle, bir numaralandırma değişkeni ile ilişkili depolama için tek gereken depolama alanı `int` değeri. Bir numaralandırma sabiti veya numaralandırılmış türde bir değer kullanılabilir herhangi bir tamsayı ifadesi C dili izin verir.

## <a name="syntax"></a>Sözdizimi

*sabit listesi belirticisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Enum** *tanımlayıcı*<sub>iyileştirilmiş</sub> **{** *numaralandırıcı-listesi* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Enum** *tanımlayıcısı*

İsteğe bağlı *tanımlayıcı* tarafından tanımlanan numaralandırma türü adları *numaralandırıcı-listesi*. Bu tanımlayıcı genellikle listesi tarafından belirtilen numaralandırma "etiket" olarak adlandırılır. Formun bir tür tanımlayıcısı

```
enum identifier
{
    enumerator-list
}
```

bildirir *tanımlayıcı* tarafından belirtilen numaralandırma etiketleri olması *numaralandırıcı-listesi* bildirimlere. *Numaralandırıcı-listesi* tanımlar "Numaralandırıcı içeriği." *Numaralandırıcı-listesi* aşağıda ayrıntılı olarak açıklanmıştır.

Bir etiketi bildirimi etiketi kullanan ancak atlamak görünür, sonraki bildirimleri ise *numaralandırıcı-listesi* daha önce bildirilen bir listeden seçimli türü belirtin. Etiket, tanımlanan numaralandırma türüne başvurmalıdır ve bu numaralandırma türü, geçerli kapsamda olmalıdır. Numaralandırma türü başka bir yerde tanımlamış *numaralandırıcı-listesi* bu bildirimi görünmez. Tür bildirimleri numaralandırmalar türetilmiş ve `typedef` numaralandırma türü tanımlanmadan önce Numaralandırma türleri için bildirimleri numaralandırma etiketi kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

*Numaralandırıcı-listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırıcı-listesi* **,** *numaralandırıcısı*

*Numaralandırıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırma sabiti*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Numaralandırma sabiti* **=** *sabit-ifade*

*Numaralandırma sabiti*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı*

Her *numaralandırma sabiti* içinde bir *numaralandırma listesini* numaralandırma kümesi değerini adlandırır. Varsayılan olarak, ilk *numaralandırma sabiti* değeri 0 ile ilişkilidir. Sonraki *numaralandırma sabiti* listede değeri ile ilişkilendirilir ( *sabit-ifade* + 1) sürece açıkça başka bir değer ile ilişkilendirin. Adı bir *numaralandırma sabiti* değerine eşdeğerdir.

Kullanabileceğiniz *numaralandırma sabiti sabit-ifade =* varsayılan değerler dizisi geçersiz kılmak için. Bu nedenle, varsa *numaralandırma sabiti sabit-ifade =* görünür *numaralandırıcı-listesi*, *numaralandırma sabiti* tarafındanverilendeğerileilişkilendirilir*sabit-ifade*. *Sabit-ifade* olmalıdır `int` yazın ve negatif olabilir.

Bir numaralandırma kümesi üyeleri için aşağıdaki kurallar geçerlidir:

- Bir numaralandırma kümesi yinelenen sabit değerleri içerebilir. Örneğin, belki de adlı değeri 0 ile iki farklı tanımlayıcılar ilişkilendirebiliyordunuz `null` ve `zero`, aynı kümedeki.

- Numaralandırma listesi tanımlayıcılarında sıradan değişken adları ve tanımlayıcıları, diğer sabit listelerinde dahil olmak üzere aynı görünürlük ile aynı kapsamda diğer tanımlayıcılarla farklı olmalıdır.

- Numaralandırma etiketleri normal kapsam kuralları uyulmadığı. Bunlar, diğer sabit listesi, yapı ve birleşim etiketleri aynı görünürlük ile farklı olmalıdır.

## <a name="examples"></a>Örnekler

Bu örneklerde, numaralandırma bildirimleri gösterilmektedir:

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

' % S'değeri 0 ile ilişkili `saturday` varsayılan olarak. Tanımlayıcı `sunday` açıkça 0 olarak ayarlanır. Kalan tanımlayıcıları 1 ile 5 arasındaki değerleri varsayılan olarak verilir.

Bu örnekte, bir değer kümesindeki `DAY` değişkenine atanan `today`.

```
enum DAY today = wednesday;
```

Sabit listesi sabitinin adı değer atamak için kullanıldığını unutmayın. Bu yana `DAY` numaralandırma türü önceden bildirildi, yalnızca sabit listesi etiketi `DAY` gereklidir.

Açıkça bir numaralandırılmış veri türünde bir değişkene bir tamsayı değeri atamak için bir cast türünü kullanın:

```
workday = ( enum DAY ) ( day_value - 1 );
```

Bu tür dönüştürme, C'de önerilir ancak gerekli değildir.

```
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */
{
    false,     /* false = 0, true = 1 */
    true
};

enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */
```

Bu bildirim olarak da belirtilebilir

```
enum BOOLEAN { false, true } end_flag, match_flag;\
```

veya

```
enum BOOLEAN { false, true } end_flag;
enum BOOLEAN match_flag;
```

Bu değişkenler kullanan bir örnek şuna benzeyebilir:

```
if ( match_flag == false )
    {
     .
     .   /* statement */
     .
    }
    end_flag = true;
```

Adsız Numaralandırıcı veri türleri de bildirilebilir. Veri türü adını atlanırsa, ancak değişkenleri bildirilebilir. Değişken `response` bir değişken türünün tanımlanan:

```
enum { yes, no } response;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sabit Listeleri](../cpp/enumerations-cpp.md)