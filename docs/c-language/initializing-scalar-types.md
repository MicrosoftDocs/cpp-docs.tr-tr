---
title: Ölçekli Türleri Başlatma
ms.date: 11/04/2016
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
ms.openlocfilehash: 3cf7eddcf43a65a787de60c391863d6471be7bcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232949"
---
# <a name="initializing-scalar-types"></a>Ölçekli Türleri Başlatma

Skaler türleri başlatırken, *atama ifadesinin* değeri değişkenine atanır. Atama için dönüştürme kuralları geçerlidir. (Bkz. dönüştürme kuralları hakkında bilgi için [tür dönüştürmeleri](../c-language/type-conversions-c.md) .)

## <a name="syntax"></a>Sözdizimi

*bildirim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirim-belirteçleri* *init-declarator-list*<sub>opt</sub> **;**

*bildirim-tanımlayıcılar*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*depolama sınıfı Belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür niteleyicisi* *bildirimi-tanımlayıcılar*<sub>kabul</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list* **,** *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;skaler başlatma için *bildirimci* **=** *başlatıcısı*  / \*\*/

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*atama ifadesi*

Aşağıdaki kurallara uyacak şekilde herhangi bir türdeki değişkenleri başlatabilirsiniz:

- Dosya kapsamı düzeyinde belirtilen değişkenler başlatılabilir. Dış düzeyde açıkça bir değişken başlatıdıysanız varsayılan olarak 0 olarak başlatılır.

- Sabit bir ifade, **statik** *depolama sınıfı Belirleyicisi*ile belirtilen genel bir değişkeni başlatmak için kullanılabilir. **Statik** olarak belirtilen değişkenler program yürütmesi başladığında başlatılır. Genel **statik** bir değişkeni açıkça başlatmadıysanız, varsayılan olarak 0 olarak başlatılır ve işaretçi türü olan her üyeye null işaretçi atanır.

- **Otomatik** veya **yazmaç** depolama sınıfı belirticisiyle belirtilen değişkenler, her yürütme denetimi bildirildiği bloğa her geçtiğinde başlatılır. Bir **Otomatik** veya **yazmaç** değişkeni bildiriminden bir başlatıcı atlarsanız, değişkenin başlangıçtaki değeri tanımsızdır. Otomatik ve kayıt değerleri için, başlatıcı bir sabit olacak şekilde kısıtlanmaz; Bu, daha önce tanımlanmış değerleri, hatta işlev çağrılarını içeren herhangi bir ifade olabilir.

- Dış değişken bildirimlerinin ve dış ya da iç, sabit ifadeler olması gereken tüm **statik** değişkenlerin başlangıç değerleri. (Daha fazla bilgi için bkz. [sabit ifadeler](../c-language/c-constant-expressions.md).) Herhangi bir harici olarak tanımlanmış veya statik değişkenin adresi sabit olduğundan, dahili olarak tanımlanmış bir **statik** işaretçi değişkenini başlatmak için kullanılabilir. Ancak, bir **Otomatik** değişkenin adresi bir statik başlatıcı olarak kullanılamaz, çünkü her bloğun yürütülmesi için farklı olabilir. **Otomatik** ve **kayıt** değişkenlerini başlatmak için sabit ya da değişken değerlerini kullanabilirsiniz.

- Bir tanımlayıcının bildiriminde blok kapsamı varsa ve tanımlayıcının dış bağlantısı varsa, bildirimin bir başlatması olamaz.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde başlatmalar gösterilmektedir:

```C
int x = 10;
```

Tamsayı değişkeni `x` sabit ifade `10`olarak başlatılır.

```C
register int *px = 0;
```

İşaretçi `px` 0 olarak başlatılır ve bir "null" işaretçisi üretir.

```C
const int c = (3 * 1024);
```

Bu örnek, **const** anahtar sözcüğü `(3 * 1024)` nedeniyle değiştirilemeyen `c` sabit bir değere başlatmak için sabit bir ifade kullanır.

```C
int *b = &x;
```

Bu ifade, `b` `x`işaretçiyi başka bir değişkenin adresiyle başlatır.

```C
int *const a = &z;
```

İşaretçi `a` adlı `z`bir değişkenin adresiyle başlatılır. Ancak, bir **const**olarak belirtildiğinden, değişken `a` yalnızca başlatılabilir, hiçbir şekilde değiştirilmez. Her zaman aynı konuma işaret eder.

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

Genel değişken `GLOBAL` , dış düzeyde bildirildiği için genel ömür süresi vardır. Yerel değişken `LOCAL` **Otomatik** depolama sınıfına sahiptir ve yalnızca bildirildiği işlevin yürütülmesi sırasında bir adrese sahiptir. Bu nedenle, adresi `LOCAL` ile **statik** işaretçi değişkeni `lp` başlatılmaya çalışılması buna izin verilmez. **Statik** işaretçi değişkeni `gp` , adresi her zaman aynı olduğu için adresine `GLOBAL` başlatılabilir. Benzer şekilde `*rp` , yerel bir değişken `rp` olduğu ve sabit olmayan bir başlatıcıya sahip olduğu için başlatılabilir. Bloğun her girildiği her seferinde yeni bir `LOCAL` adrese sahiptir ve bu, öğesine `rp`atanır.

## <a name="see-also"></a>Ayrıca bkz.

[Başlatılmasında](../c-language/initialization.md)
