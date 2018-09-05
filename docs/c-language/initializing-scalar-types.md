---
title: Ölçekli türleri başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe692b6eb1d29492605e7a6d2e7d6839a3a33b71
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754598"
---
# <a name="initializing-scalar-types"></a>Ölçekli Türleri Başlatma

Ne zaman başlatılırken skaler türleri, değerini *atama ifadesi* değişkenine atanır. Atama için dönüştürme kuralları geçerlidir. (Bkz [tür dönüştürmeleri](../c-language/type-conversions-c.md) dönüştürme kuralları hakkında daha fazla bilgi için.)

## <a name="syntax"></a>Sözdizimi

*bildirimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim tanımlayıcıları* *init-declarator-list*<sub>iyileştirilmiş</sub> **;**

*bildirim tanımlayıcıları*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı tanımlayıcısı* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirim tanımlayıcıları*<sub>iyileştirilmiş</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci* **=** *Başlatıcı*  / \* skaler başlatma \*/

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*

Aşağıdaki kurallara uyan koşuluyla herhangi bir türde değişken başlatabilirsiniz:

- Dosya kapsamı düzeyinde bildirilen değişkenleri başlatılabilir. Bir değişken dış düzeyde açıkça başlatmazsanız, varsayılan olarak 0 olarak başlatılır.

- Sabit bir ifade ile bildirilen herhangi bir genel değişken başlatmak için kullanılan **statik** *depolama sınıfı tanımlayıcısı*. Değişkenler olacak şekilde **statik** program yürütme başladığında başlatılır. Siz açıkça genel başlatmazsanız **statik** değişken, 0 için varsayılan olarak başlatılır ve işaretçi türüne sahip her üye bir null işaretçi atanır.

- Değişkenleri **otomatik** veya **kaydetme** depolama sınıfı tanımlayıcısı, her zaman yürütme denetim bloğuna geçer başlatılır, bildirildikleri. Bir bildirimi başlatıcısından atlarsanız bir **otomatik** veya **kaydetme** değişken, değişkenin başlangıç değeri tanımsızdır. Otomatik ve YAZMAÇ değerlerini, başlatıcı bir sabit; olmaya kısıtlı değil Bu önceden tanımlanmış değerler, hatta işlev çağrıları içeren herhangi bir ifade olabilir.

- Dış değişken bildirimleri ve tüm ilk değerleri **statik** değişkenleri, harici veya dahili, sabit ifadeler olmalıdır. (Daha fazla bilgi için [sabit ifadeler](../c-language/c-constant-expressions.md).) Herhangi bir harici olarak bildirilen veya statik değişken adresini sabit olduğundan, bu bir dahili olarak bildirilen başlatmak için kullanılabilir **statik** işaretçi değişkeninin. Ancak, adresini bir **otomatik** değişkeni bloğun her yürütme için farklı olabileceği için statik bir başlatıcı olarak kullanılamaz. Sabit veya değişken değerleri başlatmak için kullanabileceğiniz **otomatik** ve **kaydetme** değişkenleri.

- Bir tanımlayıcının bildirimi blok kapsamına sahiptir ve tanımlayıcının dış bağlantısı vardır, bildirimi bir başlatma sahip olamaz.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, başlatmalar gösterir:

```C
int x = 10;
```

Tamsayı değişkeni `x` sabit ifade başlatılır `10`.

```C
register int *px = 0;
```

İşaretçi `px` "null" bir işaretçi üretme 0 olarak başlatılır.

```C
const int c = (3 * 1024);
```

Bu örnekte sabit bir ifade `(3 * 1024)` başlatmak için `c` nedeniyle değiştirilemeyen sabit bir değer **const** anahtar sözcüğü.

```C
int *b = &x;
```

Bu bildirimi işaretçi başlatır `b` başka bir değişken, adresini `x`.

```C
int *const a = &z;
```

İşaretçi `a` adlı değişkenin adresini ile başlatılmış `z`. Ancak, beri belirtilen olacak şekilde bir **const**, değişken `a` yalnızca, hiçbir zaman değişiklik başlatılabilir. Her zaman aynı konuma işaret eder.

```C
int GLOBAL ;

int function( void )
{
    int LOCAL ;
    static int *lp = &LOCAL;   /* Illegal initialization */
    static int *gp = &GLOBAL;  /* Legal initialization   */
    register int *rp = &LOCAL; /* Legal initialization   */
}
```

Genel değişken `GLOBAL` genel ömrü sahiptir dış düzeyinde bildirilir. Yerel değişken `LOCAL` sahip **otomatik** depolama sınıfı ve yalnızca bu bildirilen işlev yürütülürken bir adresine sahiptir. Bu nedenle, başlatılmaya çalışılırken **statik** işaretçi değişkeninin `lp` adresiyle `LOCAL` izin verilmez. **Statik** işaretçi değişkeninin `gp` adresine başlatılabilir `GLOBAL` bu adrese her zaman aynı olduğu için. Benzer şekilde, `*rp` çünkü başlatılabilir `rp` yerel bir değişkendir ve nonconstant başlatıcısına sahip olabilir. Blok, her girildiğinde `LOCAL` sonra atanan yeni bir adresi olan `rp`.

## <a name="see-also"></a>Ayrıca Bkz.

[Başlatma](../c-language/initialization.md)