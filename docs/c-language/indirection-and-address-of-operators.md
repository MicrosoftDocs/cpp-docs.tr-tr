---
description: 'Daha fazla bilgi edinin: yöneltme ve adres Işleçleri'
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
ms.openlocfilehash: bd05d9eee4a453d9d99198a1a8481fcebcf103dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137599"
---
# <a name="indirection-and-address-of-operators"></a>İşleçlerin Yöneltmesi ve Adresi

Birli yöneltme işleci (__&#42;__) bir işaretçi aracılığıyla bir değere dolaylı olarak erişir. İşlenen bir işaretçi türü olmalıdır. İşlemin sonucu, işlenen tarafından ele alınan değerdir; yani işlenenin işaret ettiği adresteki değerdir. Sonucun türü, işlenenin ele aldığı türdür.

Terim türü *işaretçi* türünde ise, yöneltme işlecinin sonucu *tür* olur. İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir nesneye işaret ediyorsa, sonuç nesneyi atayan bir lvalue olur.

İşaretçi değeri geçerli değilse, yöneltme işlecinin sonucu tanımsız olur. Bunlar, bir işaretçi değerini geçersiz kılan en yaygın koşulların bazılarıdır:

- İşaretçi, bir null işaretçidir.

- İşaretçi, geçerlilik süresinin sonundan sonra bir nesnenin adresini belirtir (örneğin, kapsam dışı olan veya serbest bırakılmış olan bir nesne gibi), başvuru sırasında.

- İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.

- İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.

Birli adres işleci ( **&** ), işleneninin adresini verir. İşlenen, __kayıt__ bildirilmemiş ve bir bit alanı olmayan bir nesne ya da bir birli __&#42;__ işlecinin veya dizi başvuru (__&#91;&#93;__) işlecinin veya bir işlev göstergesinin sonucu olan bir lvalue olmalıdır. Sonuç *tür türü işleneni* için *tür işaretçisinin* türü.

İşlenen, birli __&#42;__ işlecinin sonucudur, hiçbir işleç değerlendirilir ve sonuç her ikisi de atlanmış gibi olur. Sonuç bir lvalue değil ve işleçlere ilişkin kısıtlamalar hala geçerlidir. İşlenen bir __&#91;&#93;__ işlecinin sonucu ise, __&__ __&#91;&#93;__ işleci tarafından kapsanan işleç veya birli __&#42;__ değerlendirilir. Sonuç, __&__ işleci kaldırma ve __&#91;&#93;__ işlecini bir işleçle değiştirme ile aynı etkiye sahiptir __+__ . Aksi takdirde sonuç, işlenen tarafından atanan nesne veya işleve yönelik bir işaretçidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler şu ortak bildirimleri kullanır:

```C
int *pa, x;
int a[20];
double d;
```

Bu ifade, **&** dizinin altıncı öğesinin adresini almak için Address-of işlecini () kullanır `a` . Sonuç, işaretçi değişkeninde saklanır `pa` :

```C
pa = &a[5];
```

Bu örnekte,____ **`int`** içinde depolanan adresteki değere erişmek için yöneltme işleci (&#42;) kullanılır `pa` . Değer, tamsayı değişkenine atanır `x` :

```C
x = *pa;
```

Bu örnek, yöneltme işlecinin adresini uygulamanın sonucunun `x` ile aynı olduğunu gösterir `x` :

```C
assert( x == *&x );
```

Bu örnek, bir işleve işaretçi bildirmesinin eşdeğer yollarını gösterir:

```C
int roundup( void );     /* Function declaration */

int  *proundup  = roundup;
int  *pround  = &roundup;
assert( pround == proundup );
```

`roundup` işlevi bildirildiğinde, iki `roundup` işaretçisi bildirilir ve başlatılır. İlk işaretçi `proundup` yalnızca işlevin adı kullanılarak başlatılır, ikinci işaretçi `pround` ise başlatma sırasında adres işlecini kullanır. Başlatma işlemleri eşdeğerdir.

## <a name="see-also"></a>Ayrıca bkz.

[Yöneltme Işleci: &#42;](../cpp/indirection-operator-star.md)<br/>
[Address-of İşleci: &](../cpp/address-of-operator-amp.md)
