---
title: Yöneltmesi ve adresi işleçlerin | Microsoft Docs
ms.custom: ''
ms.date: 02/16/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75afd44b8c0a31d9f3731a4c6f9fb86c15de4328
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389426"
---
# <a name="indirection-and-address-of-operators"></a>İşleçlerin Yöneltmesi ve Adresi

Birli indirection işleci (__&#42;__) bir değer bir işaretçi dolaylı olarak erişir. İşlenen bir işaretçi türü olmalıdır. İşlemin sonucu, işlenen tarafından ele alınan değerdir; yani işlenenin işaret ettiği adresteki değerdir. Sonucun türü, işlenenin ele aldığı türdür.

İndirection işleci sonucu *türü* işlenenin türü ise *yazmak için işaretçi*. İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir nesneye işaret ediyorsa, nesne atayan bir lvalue sonucudur.

İndirection işleci sonucunu işaretçi değeri geçerli değil, tanımlanmamıştır. Bu işaretçi değeri geçersiz kılmak en yaygın koşulların bazıları şunlardır:

- İşaretçi, bir null işaretçidir.

- İşaretçinin nesneyi adresini başvurusu aynı anda yaşam süresi (örneğin, bir nesne kapsam dışında gitti veya, serbest) bitişinden sonra belirtir.

- İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.

- İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.

Address-of birli işleci (**&**), işlenen adresini verir. İşleneni, bildirilmemiş olan bir nesne atayan bir ya da lvalue olmalıdır __kaydetmek__ ve bit alanı ya da bir tekli sonucunu __&#42;__ işleci veya bir dizi başvuru (__&#91; &#93;__) operatör ya da bir işlevi tanımlayıcı. Sonuç türü olan *yazmak için işaretçi* bir işlenen türü için *türü*.

İşlenen bir tekli sonucunu ise __&#42;__ işleci, hiçbiri işleci değerlendirilir ve her ikisi de atlanmış gibi sonucudur. Sonuç bir lvalue değil ve işleçler kısıtlamalar hala geçerlidir. İşlenen sonucu ise bir __&#91; &#93;__ işleci, hiçbiri __&__ ya da birli işleç __&#42;__ tarafındankapsanan __&#91; &#93;__ işleci değerlendirildiği. Sonucu kaldırma aynı etkiye sahip __&__ işleci ve değiştirme __&#91; &#93;__ işleci bir __+__ işleci. Aksi takdirde, sonuç nesnesi veya işlenen tarafından belirlenen işlevi bir işaretçidir.


## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, bu ortak bildirimleri kullanın:

```C
int *pa, x;
int a[20];
double d;
```

Address-of işleci bu bildirimi kullanır (**&**) dizisinin altıncı öğesi adresini yapılacak `a`. Sonuç işaretçi değişkende depolanır `pa`:

```C  
pa = &a[5];
```

İndirection işleci (__&#42;__) erişmek için bu örnekte kullanılan `int` depolanan adresi değerinde `pa`. Değer tamsayı değişkenine atanan `x`:

```C
x = *pa;
```

Bu örnekte gösterilmiştir adresine indirection işleci uygulanıyor sonucunu `x` aynı `x`:

```C
assert( x == *&x );
```

Bu örnek, bir işlev işaretçisi bildirme eşdeğer yollarını gösterir:

```C
int roundup( void );     /* Function declaration */

int  *proundup  = roundup;
int  *pround  = &roundup;
assert( pround == proundup );
```  

`roundup` işlevi bildirildiğinde, iki `roundup` işaretçisi bildirilir ve başlatılır. İlk işaretçi `proundup` yalnızca işlevin adı kullanılarak başlatılır, ikinci işaretçi `pround` ise başlatma sırasında adres işlecini kullanır. Başlatma işlemleri eşdeğerdir.

## <a name="see-also"></a>Ayrıca bkz.

[Yönlendirme işleci:&#42;](../cpp/indirection-operator-star.md)  
[Address-of İşleci: &](../cpp/address-of-operator-amp.md)  
