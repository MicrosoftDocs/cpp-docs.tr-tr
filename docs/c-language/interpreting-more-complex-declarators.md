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
ms.openlocfilehash: 2dd51e4e8a3c6805b9facfef54565368252e87df
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391671"
---
# <a name="interpreting-more-complex-declarators"></a>Daha Karmaşık Bildirimcileri Yorumlama
Tüm bildirimcisi bir "karmaşık bildirimcisi." belirli yorumu belirtmek için parantez içine alın Karmaşık bildirimcisi birden fazla dizi, işaretçi veya işlevi belirleyici tam bir tanımlayıcıdır. Dizi, işaretçi ve işlev değiştiricileri çeşitli tek bir tanımlayıcı uygulayabilirsiniz. Genellikle `typedef` bildirimleri basitleştirmek için kullanılabilir. Bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md).  
  
 Karmaşık bildirimcileri yorumlama içinde köşeli ayraçlar ve parantez (diğer bir deyişle, değiştiricileri tanımlayıcı sağında) yıldız işareti (diğer bir deyişle, değiştiricileri tanımlayıcı solundaki) önceliklidir. Köşeli parantez aynı önceliğe sahip ve soldan sağa ilişkilendirin. Bildirimcisi tam olarak yorumlanan sonra tür belirteci son adım olarak uygulanır. Parantez kullanarak varsayılan ilişki sırası geçersiz kılmak ve belirli bir yorumlama zorlar. Hiçbir zaman parantez, ancak, tek başına bir tanımlayıcı adı geçici kullanın. Bu parametre listesi yorumlanabileceğinden.  
  
 Bunları "Inside out" aşağıdaki dört adımları kullanarak okunacak karmaşık bildirimcileri yorumlama basit bir yol değil:  
  
1.  Tanımlayıcısına sahip başlatmak ve doğrudan sağındaki köşeli veya parantez (varsa) bakın.  
  
2.  Bu köşeli ayraç veya parantez yorumlama sonra için yıldız sola arayın.  
  
3.  Her aşamada sağ parantez karşılaşırsanız, geri dönün ve kural 1 ve 2 parantez içinde her şeyi uygulanır.  
  
4.  Tür belirteci uygulayın.  
  
    ```  
    char *( *(*var)() )[10];  
     ^   ^  ^ ^ ^   ^    ^  
     7   6  4 2 1   3    5  
    ```  
  
Bu örnekte, adımları sırayla numaralandırılır ve şu şekilde yorumlanabilir:  
  
1.  Tanımlayıcı `var` olarak bildirilir  
  
2.  bir işaretçi  
  
3.  döndüren bir işlev  
  
4.  bir işaretçi  
  
5.  bir dizi olan 10 öğeleri  
  
6.  işaretçiler  
  
7.  `char` değerler.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnekler diğer karmaşık bildirimleri göstermek ve parantez bir bildirimi anlamını nasıl etkileyebileceğini gösterir.  
  
```  
int *var[5]; /* Array of pointers to int values */  
```  
  
 Dizi değiştiricisi böylece işaretçi değiştiricisi, daha yüksek önceliğe sahip `var` bir dizi olarak bildirilmedi. İşaretçi değiştiricisi dizi öğeleri türü için geçerlidir; Bu nedenle, dizi öğeleri işaretçileridir `int` değerleri.  
  
```  
int (*var)[5]; /* Pointer to array of int values */  
```  
  
 Bu bildirimi için `var`, parantez dizi değiştiricisi işaretçi değiştiricisi daha yüksek önceliğe verin ve `var` beş bir dizi için bir işaretçi olarak bildirilen `int` değerleri.  
  
```  
long *var( long, long ); /* Function returning pointer to long */  
```  
  
 İşlevi değiştiricileri de işaretçi değiştiriciler, daha yüksek önceliği bu nedenle bu bildirim için `var` bildirir `var` gösteren bir işaretçi döndüren bir işlev olacak şekilde bir **uzun** değeri. İşlev iki yapılacak bildirilmiş **uzun** bağımsız değişken değerleri.  
  
```  
long (*var)( long, long ); /* Pointer to function returning long */  
```  
  
 Bu örnek önceki bir benzer. Parantez işlevi değiştiricisi işaretçi değiştiricisi daha yüksek önceliğe verin ve `var` döndüren bir işlev işaretçisi olarak bildirilen bir **uzun** değeri. Yeniden, işlev iki alır **uzun** bağımsız değişkenler.  
  
```  
struct both       /* Array of pointers to functions */  
{                 /*   returning structures         */  
    int a;  
    char b;  
} ( *var[5] )( struct both, struct both );  
```  
  
 Dizi öğelerini işlevleri olamaz, ancak bu bildirim bir dizi işlev işaretçileri bunun yerine bildirmek gösterilmiştir. Bu örnekte, `var` iki üyeleriyle yapıları döndüren işlevler için beş işaretçiler bir dizi olarak bildirilmedi. İşlevleri bağımsız değişkenleri aynı yapısı türünde iki yapıları olması bildirilir `both`. Çevreleyen parantez unutmayın `*var[5]` gereklidir. Bunları bildirimi işlevleri, bir dizi bildirmek için geçersiz bir deneme aşağıda gösterildiği gibi şöyledir:  
  
```  
/* ILLEGAL */  
struct both *var[5](struct both, struct both);  
```  
  
 Aşağıdaki ifade, bir dizi işaretçileri bildirir.  
  
```  
unsigned int *(* const *name[5][10] ) ( void );  
```  
  
 `name` Sahip çok boyutlu bir diziye düzenlenmiş 50 öğeleri dizisi. Bir sabit değer bir işaretçi işaretçiler öğelerdir. Hiçbir parametre yoktur ve işaretçi imzasız bir türü döndüren bir işlev sabit this işaretçisi işaret ediyor.  
  
 Bu sonraki örnekte bir dizi üç için bir işaretçi döndüren bir işlev, **çift** değerleri.  
  
```  
double ( *var( double (*)[3] ) )[3];  
```  
  
 Bu bildirim bir diziye bir işaretçi bir işlev döndürür, bu yana işlevleri döndürmeyi diziler geçersiz. Burada `var` bir dizi üç için bir işaretçi döndüren bir işlev olarak bildirilen **çift** değerleri. İşlev `var` bir bağımsız değişken. Dönüş değeri gibi bağımsız değişkeni gösteren bir işaretçidir üç bir dizi **çift** değerleri. Bağımsız değişken türü bir karmaşık tarafından verilen *Özet bildirimcisi*. Bağımsız değişken türü yıldız işareti parantezler gereklidir; bunları bağımsız değişken türü üç işaretçiler bir dizi olacaktır **çift** değerleri. Bir tartışma ve soyut Bildirimciler örnekleri için bkz: [soyut Bildirimciler](../c-language/c-abstract-declarators.md).  
  
```  
union sign         /* Array of arrays of pointers */  
{                  /* to pointers to unions       */  
     int x;  
     unsigned y;  
} **var[5][5];  
```  
  
 Yukarıdaki örnekte gösterildiği gibi başka bir işaretçi bir işaretçi işaret edebilir ve bir dizi öğeleri olarak diziler içerebilir. Burada `var` beş öğeleri dizisidir. Her iki üyeleriyle birleşimler işaretçiler işaretçiler beş öğeli bir dizi öğedir.  
  
```  
union sign *(*var[5])[5]; /* Array of pointers to arrays  
                             of pointers to unions        */  
```  
  
 Bu örnek, parantez yerleşimini bildirimi anlamını nasıl değiştiğini gösterir. Bu örnekte, `var` birleşimler işaretçiler beş öğesi dizileri işaretçiler beş öğesi dizisidir. Kullanımıyla ilgili örnekler için `typedef` karmaşık bildirimleri önlemek için bkz: [Typedef bildirimleri](../c-language/typedef-declarations.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimler ve Türler](../c-language/declarations-and-types.md)
