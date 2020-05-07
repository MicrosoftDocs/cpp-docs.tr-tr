---
title: Daha Karmaşık Bildirimcileri Yorumlama
ms.date: 11/04/2016
helpviewer_keywords:
- complex declarators
- interpreting complex declarators
ms.assetid: dd5b7019-c86d-4645-a5cc-21f834de6f4a
ms.openlocfilehash: 13c81728f02963863b641348b58380da099b0013
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232871"
---
# <a name="interpreting-more-complex-declarators"></a>Daha Karmaşık Bildirimcileri Yorumlama

"Karmaşık Bildirimcinin" belirli bir yorumunu belirtmek için herhangi bir bildirimcisini parantez içine alabilirsiniz. Karmaşık bildirimci, birden fazla dizi, işaretçi veya işlev değiştiricisi tarafından nitelenmiş bir tanıtıcıdır. Array, pointer ve Function değiştiricilerin çeşitli birleşimlerini tek bir tanımlayıcıya uygulayabilirsiniz. Genel `typedef` olarak, bildirimleri basitleştirmek için kullanılabilir. Bkz. [typedef bildirimleri](../c-language/typedef-declarations.md).

Karmaşık bildirimcilerin, köşeli ayraçlar ve parantezleri (yani, tanımlayıcının sağına yönelik değiştiriciler) yorumlama sırasında, yıldız (tanımlayıcı solunda değiştiriciler) arasında önceliklidir. Köşeli ayraçlar ve parantezler aynı önceliğe sahiptir ve soldan sağa ilişkilendirin. Bildirimci tamamen yorumladıktan sonra, tür belirleyicisi son adım olarak uygulanır. Parantez kullanarak varsayılan ilişkilendirme sırasını geçersiz kılabilir ve belirli bir yorumu zorlayabilirsiniz. Bununla birlikte, bir tanımlayıcı adı etrafında, hiçbir şekilde parantez kullanmayın. Bu, parametre listesi olarak yanlış yorumlanabilir.

Karmaşık bildirimcilerin yorumlanması için basit bir yol, aşağıdaki dört adımı kullanarak "içten" içinden okunmalıdır:

1. Tanımlayıcıyla başlayın ve köşeli ayraçlar veya parantezler (varsa) için doğrudan sağa bakın.

1. Bu köşeli ayraçları veya ayraçları yorumlayın ve sonra yıldız işaretleri için sola bakın.

1. Herhangi bir aşamada sağ parantez ile karşılaşırsanız, geri dönün ve parantez içindeki her şeye 1. ve 2. kuralları uygulayın.

1. Tür belirticisini uygulayın.

    ```
    char *( *(*var)() )[10];
     ^   ^  ^ ^ ^   ^    ^
     7   6  4 2 1   3    5
    ```

Bu örnekte, adımlar sırayla numaralandırılır ve şu şekilde yorumlanabilir:

1. Tanımlayıcı `var` şöyle bildirilmiştir

1. bir işaretçisi

1. döndüren bir işlev

1. bir işaretçisi

1. 10 öğeden oluşan bir dizi

1. işaretçiler

1. `char`deðerler.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde diğer karmaşık bildirimler gösterilmektedir ve parantezlerin bir bildirimin anlamını nasıl etkileyebileceği gösterilmektedir.

```
int *var[5]; /* Array of pointers to int values */
```

Dizi değiştiricisinin işaretçi değiştiricisinden daha yüksek önceliği vardır, bu `var` nedenle dizi olarak bildirilmiştir. İşaretçi değiştiricisi dizi öğelerinin türü için geçerlidir; Bu nedenle, dizi öğeleri `int` değer işaretçileridir.

```
int (*var)[5]; /* Pointer to array of int values */
```

Bu bildirimde `var`, parantez işaretçi değiştiricisini dizi değiştiricisinden daha yüksek öncelik olarak verir ve `var` beş `int` değerden oluşan bir dizi işaretçisi olarak bildirilmiştir.

```
long *var( long, long ); /* Function returning pointer to long */
```

İşlev değiştiriciler aynı zamanda işaretçi değiştiricilerine kıyasla daha yüksek önceliğe sahiptir, bu `var` nedenle `var` , için bu bildirimin **uzun** bir değere işaretçi döndüren bir işlev olduğunu bildirir. İşlevi bağımsız değişken olarak iki **uzun** değer alacak şekilde bildirilmiştir.

```
long (*var)( long, long ); /* Pointer to function returning long */
```

Bu örnek, öncekiyle benzerdir. Parantezler, işaretçi değiştiriciye işlev değiştiricisinden daha yüksek öncelik verir ve `var` **uzun** bir değer döndüren bir işlevin işaretçisi olarak bildirilmiştir. Yine, işlev iki **uzun** bağımsız değişken alır.

```
struct both       /* Array of pointers to functions */
{                 /*   returning structures         */
    int a;
    char b;
} ( *var[5] )( struct both, struct both );
```

Bir dizinin öğeleri işlev olamaz, ancak bu bildirimde bunun yerine işlevlere bir dizi işaretçi bildirimi yapılacağı gösterilmektedir. Bu örnekte, `var` iki üyeli yapılar döndüren işlevlere beş işaretçinin bir dizisi olacak şekilde bildirilmiştir. İşlevlerin bağımsız değişkenleri aynı yapı türüne sahip iki yapı olacak şekilde bildirilmiştir `both`. Çevreleyen `*var[5]` parantezler gerekli olduğunu unutmayın. Bu olmadan, bildirim, aşağıda gösterildiği gibi bir dizi işlev için geçersiz bir girişimdir:

```
/* ILLEGAL */
struct both *var[5](struct both, struct both);
```

Aşağıdaki ifade bir işaretçiler dizisi bildirir.

```
unsigned int *(* const *name[5][10] ) ( void );
```

`name` Dizide çok boyutlu bir dizide düzenlenmiş 50 öğe vardır. Öğeler, sabit olan bir işaretçiye yönelik işaretçilerdir. Bu sabit işaretçi, parametresi olmayan ve işaretsiz bir türe işaretçi döndüren bir işleve işaret eder.

Bu sonraki örnek, üç **Double** değerin dizisine bir işaretçi döndüren bir işlevdir.

```
double ( *var( double (*)[3] ) )[3];
```

Bu bildirimde, diziler döndüren işlevler geçersiz olduğundan, bir işlev bir diziye yönelik bir işaretçi döndürür. Burada `var` , üç **Double** değerin dizisine bir işaretçi döndüren bir işlev olarak bildirilmiştir. İşlev `var` bir bağımsız değişken alır. Dönüş değeri gibi bağımsız değişken, üç **Double** değer dizisinin bir işaretçisidir. Bağımsız değişken türü karmaşık bir *soyut bildirimci*tarafından verilir. Bağımsız değişken türündeki yıldız işareti etrafındaki parantezler gereklidir; Bunlar olmadan bağımsız değişken türü, **iki** değere üç işaretçilerin bir dizisi olur. Özet bildirimcilerin bir tartışması ve örnekleri için bkz. [soyut Bildirimciler](../c-language/c-abstract-declarators.md).

```
union sign         /* Array of arrays of pointers */
{                  /* to pointers to unions       */
     int x;
     unsigned y;
} **var[5][5];
```

Yukarıdaki örnekte gösterildiği gibi, bir işaretçi başka bir işaretçiye işaret edebilir ve bir dizi öğe olarak diziler içerebilir. İşte `var` beş öğeden oluşan dizi. Her öğe, iki üyeli birleşimler için işaretçilerin işaretçilerinden oluşan beş öğeli bir dizidir.

```
union sign *(*var[5])[5]; /* Array of pointers to arrays
                             of pointers to unions        */
```

Bu örnekte, ayracın yerleşiminin bildirimin anlamı nasıl değiştiği gösterilmektedir. Bu örnekte, `var` birleşimlere işaretçilerin beş öğeli dizileri için işaretçilerin beş öğeli bir dizisidir. Karmaşık bildirimlerin olmaması için kullanmanın `typedef` örnekleri için bkz. [typedef bildirimleri](../c-language/typedef-declarations.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve türler](../c-language/declarations-and-types.md)
