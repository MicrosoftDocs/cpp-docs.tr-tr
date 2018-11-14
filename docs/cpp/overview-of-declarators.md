---
title: Bildiricilere Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
ms.openlocfilehash: 66f1068fd3f69d3e4546f159ec22b34024bd2057
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326764"
---
# <a name="overview-of-declarators"></a>Bildiricilere Genel Bakış

Bildirimciler, nesne veya işlev adlarını belirten bir bildirimin bileşenleridir. Bildirimciler, adlandırılmış nesnelerin bir nesne, işaretçi, başvuru veya dizi olduğunu da belirtir.  Bildirimciler temel türü belirtmese de, işaretçiler, başvurular ve diziler gibi türetilmiş türleri belirtmek için temel türdeki tür bilgilerini değiştirir.  İşlevlere uygulanan bildirimci, bir işlevin dönüş türünü nesne, işaretçi veya başvuru olarak belirtmek için tür tanımlayıcısı ile birlikte çalışır. (De ele alınan tanımlayıcılar, [bildirimlerinin ve tanımlarının](declarations-and-definitions-cpp.md), tür ve depolama sınıfı gibi özellikleri iletmek. Bu bölümde hem de ele alınan değiştiriciler [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md), bildirimcileri değiştirir.) Aşağıdaki şekilde, tam bir `MyFunction` bildirimi gösterilmekte ve bildirimin bileşenleri çağrılmaktadır.

![Değiştiriciler, tanımlayıcıların ve bildirimcilerin](../cpp/media/vc38qy1.gif "vc38QY1") tanımlayıcılar, değiştiriciler ve Bildirimciler

**Microsoft'a özgü**

Microsoft'un genişletilmiş çoğu anahtar sözcüğü, türetilmiş türler oluşturmak için değiştiriciler olarak kullanılabilir; tanımlayıcı veya bildirimci değildirler. (Bkz [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md).)

**END Microsoft özgü**

Bildirimciler, isteğe bağlı bir tanımlayıcılar listesinden sonra bildirim sözdiziminde görünür. Bu tanımlayıcılar ele alınmıştır [bildirimleri.](declarations-and-definitions-cpp.md) Bir bildirim, birden fazla bildirimci içerebilir, ancak her bildirimci yalnızca bir ad bildirir.

Aşağıdaki örnek bildirimde, tanımlayıcıların ve bildirimcilerin tam bir bildirim oluşturmak için nasıl birleştirildiği gösterilmektedir:

```cpp
const char *pch, ch;
```

Önceki bildirimde, anahtar sözcükleri **const** ve **char** tanımlayıcıların listesini olun. İki bildirimci listelenmiştir: `*pch` ve `ch`.  Birden fazla varlığı bildiren bir bildirim, sırasıyla bir tür tanımlayıcısı, virgülle ayrılmış bir bildirimciler listesi ve bir noktalı virgülden oluşur.

**Basit nesneler için Bildirimciler**

int veya double gibi basit bir nesnenin bildirimcisi, isteğe bağlı parantezlerle birlikte kendi adından oluşur.

`int i; // declarator is i`

`int (i); // declarator is (i)`

**İşaretçiler, başvurular ve diziler için Bildirimciler**

Adın önüne yerleştirilen işaretçi işleçleri, nesnenin bir işaretçi veya başvuru olmasına neden olur.  <strong>\*</strong> İşleci adı işaretçi; olarak bildirir **&** işleci, bir başvuru olarak bildirir.

```cpp
int *i; // declarator is *i
int **i; // declarator is **i;
int &i = x; // declaratory is &i
```

Ekleme **const** veya **geçici** işaretçiyi bu özel özellikleri sağlar.  Bir tanımlayıcıların bir bildirimcide (tür tanımlayıcısına karşılık olarak) kullanılması, işaret edilen nesnenin değil, işaretçinin özelliklerini değiştirir:

```cpp
char *const cpc; // const pointer to char
const char *pcc; // pointer to const char
const char *const cpcc; // const pointer to const char
```

Daha fazla bilgi bulunabilir [const ve volatile işaretçileri](../cpp/const-and-volatile-pointers.md).

Bir sınıf veya yapı üyesinin işaretçisi, uygun iç içe geçmiş ad tanımlayıcısı ile bildirilir:

```cpp
int X::* pIntMember;
int ::X::* pIntMember; // the initial :: specifies X is in global scope
char Outer::Inner::* pIntMember; // pointer to char in a nested class
```

Addan sonra isteğe bağlı bir sabit ifadeyi çevreleyen köşeli parantezler, nesnenin bir dizi olmasına neden olur.  Art arda gelen köşeli parantezler, diziye ek boyutlar bildirir.

```cpp
int i[5]; // array with five elements of type int numbered from 0 to 4
int i[]; // array of unknown size
char *s[4]; // array of pointers to char
int i[2][2]; // two dimensional array
```

**İşlevler için Bildirimciler**

Bağımsız değişken listesini içeren parantezler, bir işlev bildirmek için addan sonra kullanılır.  Aşağıdaki dönüş türünde bir işlev bildirir **int** ve türünde üç bağımsız değişken **int**.

```cpp
int f(int a, int b, int c);
```

İşlevlerin işaretçileri ve başvuruları, işaretçi veya başvuru işleci aşağıda gösterildiği gibi işlev adının önüne eklenerek bildirilir.  Bir işlev işaretçisini bir işaretçi döndüren bir işlevden ayırmak için normalde isteğe bağlı olan parantezlerin kullanılması gerekir:

```cpp
int (*pf)(int); // pointer to function returning int
int *f(int i); // function returning pointer to int
int (&pf)(int); // reference to function
```

Üye işlevlerinin işaretçileri, iç içe geçmiş ad tanımlayıcıları ile ayırt edilir:

```cpp
int (X::* pmf)(); // pointer to member function of X returning int
int* (X::* pmf)(); // pointer to member function returning pointer to int
```

Ayrıca bkz: [üye işaretçileri](../cpp/pointers-to-members.md).

**Aynı bildirimde alanındaki işlevler ve nesneler**

İşlevler ve nesneler aşağıdaki gibi aynı bildirimde bildirilebilir:

```cpp
int i, *j, f(int k);  // int, pointer to int, function returning int
```

Sözdizimi, bazı durumlarda yanıltıcı olabilir.  Aşağıdaki bildirim

```cpp
int* i, f(int k);  // pointer to int, function returning int (not int*)
```

bildirimi olarak görünebilir bir **int** işaretçi ve döndüren bir işlevin `int*`, ancak böyle değildir.  Çünkü \* bildirimcisinin bir parçasıdır `i`, bildirimcisi parçası `f`.

**Typedef ile bildirimci sözdizimini basitleştirme**

Daha iyi bir tekniktir ancak kullanmaktır bir **typedef** veya bir birleşimini parantez ve **typedef** anahtar sözcüğü. İşlevler için bir dizi işaretçi bildirmeyi göz önünde bulundurun:

```cpp
//  Function returning type int that takes one
//   argument of type char *.
typedef int (*PIFN)( char * );
//  Declare an array of 7 pointers to functions
//   returning int and taking one argument of type
//   char *.
PIFN pifnDispatchArray[7];
```

Eşdeğer bildirimi olmadan yazılabilir **typedef** bildirimi, ancak hata potansiyeli herhangi bir avantaj aştığını kadar karmaşık:

```cpp
int ( *pifnDispatchArray[7] )( char * );
```

Typedef hakkında daha fazla bilgi için bkz. [diğer adlar ve tür tanımları](aliases-and-typedefs-cpp.md).

İşaretçiler, başvurular, tek bir temel türün dizileri tek bir bildirimde şu şekilde birleştirilebilir (virgüllerle ayrılarak)

```cpp
int a, *b, c[5], **d, &e=a;
```

**Daha karmaşık bildirimci sözdizimi**

- İşaretçi, başvuru, dizi ve işlev bildirimcileri, böyle nesneleri işlev işaretçilerinin dizileri, dizi işaretçileri, vb. olarak belirtecek şekilde birleştirilemez.

- Aşağıdaki özyinelemeli dilbilgisi, işaretçi bildirimcisi sözdizimini tam olarak açıklar.

- Bir `declarator` şunlardan biri olarak tanımlanır:

  - tanımlayıcı
  - tam ad
  - bildirimci (bağımsız değişken listesi) [MS-qualfiers] [özel durum belirtimi]
  - bildirimci [[sabit-ifade]]
  - İşaretçi işleci bildirimcisi
  - (bildirimci)

- ve *işaretçi işleci* biridir:

  - \* [cv niteleyicileri]
  - & [cv niteleyicileri]:: iç içe-adı-specifier \* [cv niteleyicileri]

Bir bildirimci bildirimciler içerebileceği için yukarıdaki kurallar kullanılarak işaretçi dizileri, işlev işaretçilerinin dizilerini döndüren işlevler gibi daha karmaşık türetilmiş türler oluşturulabilir.  Oluşturma işleminin her adımı için temel veri türünü temsil eden tanımlayıcı ile işe başlayın ve önceki ifadeyle birlikte `declarator` olarak yukarıdaki sözdizimi kuralını uygulayın.  Sözdizimi kurallarını uyguladığınız sıra, ifadenin İngilizce olarak belirtildiği yönün tersi olmalıdır.  Uygulanıyorsa *işaretçi işleci* sözdizimi kuralı bir dizi veya işlev ifade, dizi veya işlev, aşağıdaki tabloda Son satırda olduğu gibi bir işaretçiye istiyorsanız parantezler kullanın.

Aşağıdaki örnekte, "10 int işaretçi dizisinin işaretçisi" oluşturulmuştur.

|Sözlü ifade|Bildirimciler|Uygulanan Sözdizimi Kuralı|
|-----------------------|----------------|-------------------------|
||`i`|1.|
|işaretçileri|`*i`|5|
|10 dizisi|`(*i)[10]`|4|
|işaretçisi|`*((*i)[10])`|6 ve sonra 5|

Birden fazla işaretçi, başvuru, dizi veya işlev değiştiricisi kullanıldığında, bildiriciler çok karmaşık hale gelebilir.  Konu [daha karmaşık Bildirimcileri yorumlama](../c-language/interpreting-more-complex-declarators.md) daha karmaşık bildirimci sözdiziminin nasıl okunacağı açıklanmaktadır.  C++'ta olsa da, herhangi bir konu hem C hem de C++ için uygun \* MyClass gibi bir tam adı bir işaretçiyi göstermek için kullanılan::\* bir sınıfın bir üye işaretçisi belirtmek için kullanılabilir.