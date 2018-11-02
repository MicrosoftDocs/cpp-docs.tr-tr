---
title: İşleçlerin Yöneltmesi ve Adresi
ms.date: 02/16/2018
helpviewer_keywords:
- address-of operator (&)
- '* operator'
- operators [C++], address-of
- ampersand operator (&)
- '* operator, indirection operator'
- addresses [C++], indirection
- addresses [C++]
- indirection operator
- '& operator, address-of operator'
- null pointers [C++]
- '* operator, address-of operator'
- operators [C++], indirection
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
ms.openlocfilehash: 146f84c90aa56b5abf6ae5212c1729022cb7e4dc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534374"
---
# <a name="indirection-and-address-of-operators"></a>İşleçlerin Yöneltmesi ve Adresi

Birli yöneltme işleci (__&#42;__) bir değere işaretçi aracılığıyla dolaylı olarak erişir. İşlenen bir işaretçi türü olmalıdır. İşlemin sonucu, işlenen tarafından ele alınan değerdir; yani işlenenin işaret ettiği adresteki değerdir. Sonucun türü, işlenenin ele aldığı türdür.

Yöneltme işlecinin sonucu *türü* işlenenin türü ise *işaretçi türüne*. İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir nesneye işaret ediyorsa sonuç nesneyi gösteren bir lvalue olur.

İşaretçi değeri geçersizse, yöneltme işlecinin sonucu tanımsızdır. Bir işaretçi değerini geçersiz kılan en yaygın koşulların bazılarını şunlardır:

- İşaretçi, bir null işaretçidir.

- İşaretçi başvurusu zamanında bir nesnenin adresini (örneğin, bir nesne kapsam dışına gitti veya, serbest bırakılmış) yaşam süresi dolduktan sonra belirtir.

- İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.

- İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.

Birli adres işleci (**&**), işlenenin adresini verir. İşlenen, bildirilmemiş bir nesneyi gösteren bir ya da bir lvalue olmalıdır __kaydetme__ ve bir bit alanına ya da bir tekli sonucunu __&#42;__ işleci veya bir dizi başvurma (__&#91; &#93;__) işleci veya bir işlev göstergesi. Sonuç türünde *işaretçi türüne* türünde bir işlenen için *türü*.

İşlenen bir tekli sonucunu ise __&#42;__ işleci, hiçbiri işleci değerlendirilir ve her ikisi de atlanmış gibi sonucudur. Sonuç bir lvalue değildir ve işleçler kısıtlamalar hala geçerlidir. İşlenen sonucunu ise bir __&#91; &#93;__ işleci, hiçbiri __&__ ya da birli işleç __&#42;__ tarafındankapsanan __&#91; &#93;__ işleci değerlendirilir. Sonuç kaldırma aynı etkiye sahip __&__ işleci ve değiştirme __&#91; &#93;__ işleci bir __+__ işleci. Aksi halde, sonuç nesne veya işlev işlenen tarafından belirlenen şekilde bir işaretçisidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, yaygın Bu bildirimler kullanılmaktadır:

```C
int *pa, x;
int a[20];
double d;
```

Bu deyim adres işlecini kullanır (**&**) dizisinin altıncı öğesinin adresini almak için `a`. Sonuç işaretçi değişkeninde depolanır `pa`:

```C
pa = &a[5];
```

Yöneltme işleci (__&#42;__) erişmek için bu örnekte kullanılan `int` değeri depolanan adresteki `pa`. Değer tamsayı değişkenine atanır `x`:

```C
x = *pa;
```

Bu örnek, gösterir yöneltme işleci adresine sonucu `x` aynı `x`:

```C
assert( x == *&x );
```

Bu örnek için bir işleve işaretçi bildirme eşdeğer yöntemler gösterilmektedir:

```C
int roundup( void );     /* Function declaration */

int  *proundup  = roundup;
int  *pround  = &roundup;
assert( pround == proundup );
```

`roundup` işlevi bildirildiğinde, iki `roundup` işaretçisi bildirilir ve başlatılır. İlk işaretçi `proundup` yalnızca işlevin adı kullanılarak başlatılır, ikinci işaretçi `pround` ise başlatma sırasında adres işlecini kullanır. Başlatma işlemleri eşdeğerdir.

## <a name="see-also"></a>Ayrıca bkz.

[Yöneltme işleci:&#42;](../cpp/indirection-operator-star.md)<br/>
[Address-of İşleci: &](../cpp/address-of-operator-amp.md)
