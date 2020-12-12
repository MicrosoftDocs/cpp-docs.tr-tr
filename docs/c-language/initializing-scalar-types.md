---
description: 'Daha fazla bilgi edinin: skaler türleri başlatma'
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
ms.openlocfilehash: a9294f04f39e6984a2068c5c8f79e48641834236
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181838"
---
# <a name="initializing-scalar-types"></a>Ölçekli Türleri Başlatma

Skaler türleri başlatırken, değeri *`assignment-expression`* değişkenine atanır. Atama için dönüştürme kuralları geçerlidir. (Bkz. dönüştürme kuralları hakkında bilgi için [tür dönüştürmeleri](../c-language/type-conversions-c.md) .)

## <a name="syntax"></a>Syntax

*`declaration`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declaration-specifiers`**`init-declarator-list`* <sub>opt</sub>**`;`**

*`declaration-specifiers`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`storage-class-specifier`**`declaration-specifiers`* <sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`type-specifier`**`declaration-specifiers`* <sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`type-qualifier`**`declaration-specifiers`* <sub>opt</sub>

*`init-declarator-list`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`init-declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`init-declarator-list`* **`,`** *`init-declarator`*

*`init-declarator`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declarator`*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`declarator`***`=`** *`initializer`* /\* Skaler başlatma için\*/

*`initializer`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`assignment-expression`*

Aşağıdaki kurallara uyacak şekilde herhangi bir türdeki değişkenleri başlatabilirsiniz:

- Dosya kapsamı düzeyinde belirtilen değişkenler başlatılabilir. Dış düzeyde açıkça bir değişken başlatıdıysanız varsayılan olarak 0 olarak başlatılır.

- Sabit bir ifade, ile belirtilen herhangi bir genel değişkeni başlatmak için kullanılabilir **`static`** *`storage-class-specifier`* . **`static`** Program yürütme başladığında, olarak belirtilen değişkenler başlatılır. Genel bir değişkeni açıkça başlatmadıysanız **`static`** , varsayılan olarak 0 olarak başlatılır ve işaretçi türüne sahip her üyeye null işaretçi atanır.

- **`auto`** Veya **`register`** depolama sınıfı belirticisiyle belirtilen değişkenler, her yürütme denetimi bildirildiği bloğa her geçtiğinde başlatılır. Bir veya değişkeni bildiriminden bir başlatıcı atlarsanız **`auto`** **`register`** , değişkenin başlangıçtaki değeri tanımsızdır. Otomatik ve kayıt değerleri için, başlatıcı bir sabit olacak şekilde kısıtlanmaz; Bu, daha önce tanımlanmış değerleri, hatta işlev çağrılarını içeren herhangi bir ifade olabilir.

- Dış değişken bildirimlerinin ve **`static`** dış ya da iç, sabit deyimler olması gereken tüm değişkenlerin başlangıç değerleri. (Daha fazla bilgi için bkz. [sabit ifadeler](../c-language/c-constant-expressions.md).) Herhangi bir harici olarak tanımlanmış veya statik değişkenin adresi sabit olduğundan, dahili olarak tanımlanmış bir işaretçi değişkenini başlatmak için kullanılabilir **`static`** . Ancak, bir değişkenin adresi bir **`auto`** statik başlatıcı olarak kullanılamaz, çünkü bloğun her yürütmesi için farklı olabilir. Ve değişkenlerini başlatmak için sabit ya da değişken değerlerini kullanabilirsiniz **`auto`** **`register`** .

- Bir tanımlayıcının bildiriminde blok kapsamı varsa ve tanımlayıcının dış bağlantısı varsa, bildirimin bir başlatması olamaz.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde başlatmalar gösterilmektedir:

```C
int x = 10;
```

Tamsayı değişkeni `x` sabit ifade olarak başlatılır `10` .

```C
register int *px = 0;
```

İşaretçi `px` 0 olarak başlatılır ve bir "null" işaretçisi üretir.

```C
const int c = (3 * 1024);
```

Bu örnek `(3 * 1024)` `c` , anahtar sözcüğü nedeniyle değiştirilemeyen sabit bir değere başlatmak için sabit bir ifade kullanır **`const`** .

```C
int *b = &x;
```

Bu ifade `b` , işaretçiyi başka bir değişkenin adresiyle başlatır `x` .

```C
int *const a = &z;
```

İşaretçi `a` adlı bir değişkenin adresiyle başlatılır `z` . Ancak, bir olarak belirtildiğinden **`const`** , değişken `a` yalnızca başlatılabilir, hiçbir şekilde değiştirilmez. Her zaman aynı konuma işaret eder.

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

Genel değişken, `GLOBAL` dış düzeyde bildirildiği için genel ömür süresi vardır. Yerel değişken `LOCAL` **`auto`** depolama sınıfına sahiptir ve yalnızca bildirildiği işlevin yürütülmesi sırasında bir adrese sahiptir. Bu nedenle, **`static`** öğesinin adresine sahip işaretçi değişkenini başlatmaya çalışmak için `lp` `LOCAL` izin verilmez. **`static`** `gp` `GLOBAL` Bu adres her zaman aynı olduğundan, işaretçi değişkeni adresini adresine başlatılabilir. Benzer şekilde, `*rp` `rp` yerel bir değişken olduğu ve sabit olmayan bir başlatıcıya sahip olduğu için başlatılabilir. Bloğun her girildiği her seferinde `LOCAL` Yeni bir adrese sahiptir ve bu, öğesine atanır `rp` .

## <a name="see-also"></a>Ayrıca bkz.

[Başlatma](../c-language/initialization.md)
