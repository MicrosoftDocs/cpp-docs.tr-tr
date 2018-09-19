---
title: Daha karmaşık Bildirimcileri yorumlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- complex declarators
- interpreting complex declarators
ms.assetid: dd5b7019-c86d-4645-a5cc-21f834de6f4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc5b831d00c83569bc01a5580f511d126fb97bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083112"
---
# <a name="interpreting-more-complex-declarators"></a>Daha Karmaşık Bildirimcileri Yorumlama

Bildirimci herhangi bir "karmaşık bildirimci.", belirli bir yorumu belirtmek için ayraç içine alın Karmaşık bildirimci, birden fazla dizi, işaretçisi veya işlev değiştiricisi göre koşullu bir tanımlayıcıdır. Dizi, işaretçi ve işlev değiştiricisinden çeşitli birleşimlerini için tek bir tanımlayıcı uygulayabilirsiniz. Genellikle `typedef` bildirimleri basitleştirmek için kullanılabilir. Bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md).

Karmaşık bildirimcileri yorumlama köşeli ayraçlar ve parantez (diğer bir deyişle, değiştiriciler tanımlayıcıyı sağındaki) yıldız işareti (diğer bir deyişle, değiştiriciler tanımlayıcıyı solundaki) göre önceliklidir. Köşeli parantez aynı önceliğe sahip ve soldan sağa ilişkilendirilir. Bildirimci tam olarak yorumlanan sonra tür belirticisi son adım olarak uygulanır. Parantezler kullanarak varsayılan ilişkilendirme sırası geçersiz kılmak ve belirli bir yorumu zorla. Hiçbir zaman parantezler, ancak bir tanımlayıcı adı kendisi tarafından geçici olarak kullanın. Bir parametre listesi olarak yanlış.

Bunları "içinden," dört aşağıdaki adımları kullanarak okunacak karmaşık bildirimcileri yorumlama için basit bir yol verilmiştir:

1. Tanımlayıcı ile başlayın ve doğrudan için sağ köşeli ayraç veya parantezler (varsa) bakın.

1. Bu parantezler veya parantez yorumlama ardından için yıldız işareti sola bakın.

1. Herhangi bir aşamasında sağ ayraç karşılaşırsanız, geri dönün ve kuralları 1 ve 2 parantez içindeki her şey için geçerlidir.

1. Tür belirticisi uygulayın.

    ```
    char *( *(*var)() )[10];
     ^   ^  ^ ^ ^   ^    ^
     7   6  4 2 1   3    5
    ```

Bu örnekte, adımları sırayla numaralandırılır ve şu şekilde yorumlanabilir:

1. Tanımlayıcı `var` olarak bildirilir

1. Bir işaretçi

1. döndüren bir işlev

1. Bir işaretçi

1. bir dizi olan 10 öğeleri

1. işaretçiler

1. `char` değerler.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, karmaşık diğer bildirimleri göstermek ve parantez anlamı bildiriminin nasıl etkileyebileceğini gösterir.

```
int *var[5]; /* Array of pointers to int values */
```

Dizi değiştiricisi işaretçi değiştirici, daha yüksek önceliğe serileştirilmesini `var` bir dizi olmasını bildirilir. İşaretçi değiştirici, dizi öğelerinin türü için geçerlidir; Bu nedenle, dizi öğelerinin işaretçileri olan `int` değerleri.

```
int (*var)[5]; /* Pointer to array of int values */
```

Bu bildirimi için `var`, parantezler, dizi değiştiricisi, işaretçi değiştirici daha yüksek önceliğe verin ve `var` beş bir dizi işaretçi olarak bildirilmiştir `int` değerleri.

```
long *var( long, long ); /* Function returning pointer to long */
```

İşlev değiştiricisinden de işaretçi değiştiriciler, daha yüksek önceliğe bu nedenle bu bildirimin `var` bildirir `var` olması için bir işaretçi döndüren bir işlevin bir **uzun** değeri. İki yararlanmak için bildirilen işlev **uzun** bağımsız değişkenler olarak değerleri.

```
long (*var)( long, long ); /* Pointer to function returning long */
```

Bu örnek Öncekine benzer. Parantez işlev değiştirici işaretçi değiştirici daha yüksek önceliğe verin ve `var` döndüren bir işlev işaretçisi olarak bildirilen bir **uzun** değeri. Yeniden işlevi iki alır **uzun** bağımsız değişkenler.

```
struct both       /* Array of pointers to functions */
{                 /*   returning structures         */
    int a;
    char b;
} ( *var[5] )( struct both, struct both );
```

Bir dizinin öğeleri işlevler olamaz, ancak bu bildirim, bunun yerine bir dizi işlev işaretçileri bildirmek gösterilmektedir. Bu örnekte, `var` yapıları iki üyeli döndüren işlevleri için beş işaretçiler dizisi olarak bildirilir. İşlevlere bağımsız değişkenler aynı yapı türünde iki yapıları olması bildirilir `both`. Çevresindeki parantezler unutmayın `*var[5]` gereklidir. Bunlar olmadan bildirimi işlevlerinin bir diziyi bildirmek için geçersiz bir girişimde bulunuldu aşağıda gösterildiği gibi şu şekildedir:

```
/* ILLEGAL */
struct both *var[5](struct both, struct both);
```

Aşağıdaki deyim, bir işaretçiler dizisi bildirir.

```
unsigned int *(* const *name[5][10] ) ( void );
```

`name` Sahip çok boyutlu bir dizi düzenlenmiş 50 öğeleri dizisi. Bir sabit bir işaretçi işaretçileri öğeleridir. Bu sabit bir işaretçi parametresi yok ve bir işaretsiz türe işaretçi döndüren bir işleve işaret eder.

Bu örnekte üç dizi için işaretçi döndüren bir işlevdir **çift** değerleri.

```
double ( *var( double (*)[3] ) )[3];
```

Bu bildirim bir dizisine bir işaretçi bir işlev döndürür, bu yana işlevleri döndüren dizileri geçersizdir. Burada `var` üç dizi için işaretçi döndüren bir işlev için bildirilen **çift** değerleri. İşlev `var` bir bağımsız değişken alır. Bağımsız değişkeni dönüş değeri gibi bir dizi üç işaretçisidir **çift** değerleri. Bağımsız değişken türü bir karmaşık tarafından verilen *soyut bildirimci*. Bağımsız değişken türü yıldız işareti parantez gereklidir; bunlar olmadan bir dizi üç bağımsız değişken türü olacaktır **çift** değerleri. Bir tartışma ve soyut Bildirimciler örnekleri için bkz: [soyut Bildirimciler](../c-language/c-abstract-declarators.md).

```
union sign         /* Array of arrays of pointers */
{                  /* to pointers to unions       */
     int x;
     unsigned y;
} **var[5][5];
```

Yukarıdaki örnekte gösterildiği gibi bir işaretçi başka bir işaretçiye işaret edebilir ve dizileri öğe olarak bir dizi içerebilir. Burada `var` beş öğe dizisidir. Her iki üyeli birleşimler işaretçileri işaretçilere beş öğe dizisi öğedir.

```
union sign *(*var[5])[5]; /* Array of pointers to arrays
                             of pointers to unions        */
```

Bu örnekte, parantezler yerleşimini bildirim anlamını nasıl değiştiğini gösterir. Bu örnekte, `var` birleşimler işaretçiler beş öğe diziler işaretçilere beş öğe dizisidir. Nasıl kullanılacağına ilişkin örnekler için `typedef` karmaşık bildirimlerinden kaçınmak için bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Türler](../c-language/declarations-and-types.md)
