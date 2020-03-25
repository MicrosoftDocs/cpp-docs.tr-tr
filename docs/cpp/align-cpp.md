---
title: align (C++)
ms.date: 12/17/2018
f1_keywords:
- align_cpp
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
ms.openlocfilehash: 227053fbfa4190dc6227ba7096a7c76aef30bb54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181557"
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 ve üzeri sürümlerde, hizalamayı denetlemek için C++ 11 standart `alignas` belirticisini kullanın. Daha fazla bilgi için bkz. [Hizalama](../cpp/alignment-cpp-declarations.md).

**Microsoft 'a özgü**

Kullanıcı tanımlı verilerin hizalamasını tam olarak denetlemek için `__declspec(align(#))` kullanın (örneğin, statik ayırmalar veya bir işlevdeki otomatik veriler).

## <a name="syntax"></a>Sözdizimi

> **__declspec (align (** *#* **))** *bildirimci*

## <a name="remarks"></a>Açıklamalar

En son işlemci yönergelerini kullanan uygulamalar yazmak, bazı yeni kısıtlamalar ve sorunlar getirir. Özellikle, birçok yeni yönerge, verilerin 16 baytlık sınırlara hizalanmalıdır. Ayrıca, sık kullanılan verileri belirli bir işlemcinin önbellek satırı boyutuna hizalayarak, önbellek performansını geliştirebilirsiniz. Örneğin, boyutu 32 bayttan daha az olan bir yapı tanımlarsanız, bu yapı türünün nesnelerinin etkin bir şekilde önbelleğe alınıp alınmamasını sağlamak için onu 32 bayta hizalamak isteyebilirsiniz.

hizalama değeri \#. Geçerli girişler 2, 4, 8, 16, 32 veya 64 gibi 1 ile 8192 (bayt) arasında iki adet tamsayı üstür. `declarator`, hizalanmış olarak bildirdiğiniz veri.

Türünün hizalama gereksinimidir `size_t` türünde bir değer döndürme hakkında daha fazla bilgi için bkz. [__alignof](../cpp/alignof-operator.md). 64-bit işlemcileri hedeflerken hizalanmamış işaretçiler bildirme hakkında daha fazla bilgi için bkz. [__unaligned](../cpp/unaligned.md).

Bir **Yapı**, **birleşim**veya **sınıf**tanımlarken ya da bir değişken bildirdiğinizde `__declspec(align(#))` kullanabilirsiniz.

Derleyici, bir kopyalama veya veri dönüştürme işlemi sırasında verilerin hizalama özniteliğini korumaya garantilemez veya bu özniteliği korumayı denemez. Örneğin, [memckopyala](../c-runtime-library/reference/memcpy-wmemcpy.md) , `__declspec(align(#))` ile belirtilen bir yapıyı herhangi bir konuma kopyalayabilir. Normal ayırıcıların (örneğin, [malloc](../c-runtime-library/reference/malloc.md), C++ [New operatörü](new-operator-cpp.md)ve Win32 ayırıcıların), genellikle `__declspec(align(#))` yapıları veya yapı dizileri için yeterince hizalanmamış bir bellek döndürmesi gerektiğini unutmayın. Bir kopyalama veya veri dönüştürme işleminin hedefinin doğru hizalandığını garantilemek için [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)kullanın veya kendi ayırıcılarınızı yazın.

İşlev parametreleri için hizalama belirtemezsiniz. Hizalama özniteliğine sahip veriler yığın üzerinde değer ile geçirildiğinde, hizalaması çağırma kuralına göre denetlenir. Çağrılan işlevde veri hizalaması önemliyse, kullanmadan önce parametresini doğru hizalanmış belleğe kopyalayın.

`__declspec(align(#))`olmadan derleyici, verileri hedef işlemciye, verilerin boyutuna ve 32 bitlik işlemcilerde 4 baytlık sınırlara ve 64 bit işlemcilerde 8 baytlık sınırlara göre genel olarak doğal sınırlara göre hizalar. Sınıflardaki veya yapılardaki veriler, doğal hizalamasının ve geçerli paketleme ayarının (#pragma `pack` veya `/Zp` derleyici seçeneğinden) en az bir sınıf veya yapıda hizalanır.

Bu örnekte `__declspec(align(#))`kullanımı gösterilmektedir:

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

Bu türün artık 32 baytlık bir hizalama özniteliği vardır. Bu, tüm statik ve otomatik örneklerin 32 baytlık bir sınırın üzerinde başlayacağı anlamına gelir. Bu tür bir üye olarak belirtilen ek yapı türleri, bu türün hizalama özniteliğini korur, diğer bir deyişle, öğe olarak `Str1` olan herhangi bir yapı, en az 32 hizalama özniteliğine sahiptir.

`sizeof(struct Str1)` 32 ' e eşit olduğunu unutmayın. Bu, bir dizi str1 nesnesi oluşturulduysa ve dizinin temeli 32 bayt hizalı ise, dizinin her üyesinin da 32 baytlık hizalı olduğunu gösterir. Temeli dinamik bellekte doğru şekilde hizalanan bir dizi oluşturmak için [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)kullanın veya kendi ayırıcılarınızı yazın.

Herhangi bir yapı için `sizeof` değeri, son üyenin ve bu üyenin boyutunun en büyük üye hizalama değerinin en yakın katına yuvarlanarak, hangisi daha büyükse, tam yapı hizalama değeri olan uzaklığa yuvarlanır.

Derleyici, yapı hizalaması için bu kuralları kullanır:

- `__declspec(align(#))`ile geçersiz kılınmamışsa, skaler bir yapı üyesinin hizalaması en düşük boyut ve geçerli paketleme olur.

- `__declspec(align(#))`geçersiz kılınmamışsa, bir yapının hizalaması, üyelerinin tek tek hizalamasının en fazla sayısıdır.

- Yapı üyesi, bir önceki üyenin sonundaki uzaklığa eşit veya daha büyük hizalamasının en küçük katı olan üst yapısının başlangıcından itibaren bir uzaklığa yerleştirilir.

- Bir yapının boyutu, hizalamasının en küçük katı veya en son üyesinin sonuna kadar olan uzaklığa eşittir.

`__declspec(align(#))`, yalnızca hizalama kısıtlamalarını artırabilir.

Daha fazla bilgi için bkz.

- [Örnekleri Hizala](#vclrfalignexamples)

- [__Declspec ile yeni türler tanımlama (align (#))](#vclrf_declspecaligntypedef)

- [Iş parçacığı yerel depolama alanında verileri hizalama](#vclrfthreadlocalstorageallocation)

- [Veri paketleme ile nasıl hizalanır?](#vclrfhowalignworkswithdatapacking)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

## <a name="align-examples"></a><a name="vclrfalignexamples"></a>Örnekleri Hizala

Aşağıdaki örneklerde, `__declspec(align(#))` veri yapılarının boyutunu ve hizalamasını nasıl etkilediği gösterilmektedir. Örneklerde aşağıdaki tanımlar varsayılmaktadır:

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

Bu örnekte, `S1` yapısı `__declspec(align(32))`kullanılarak tanımlanmıştır. Bir değişken tanımı veya diğer tür bildirimlerinde tüm `S1` kullanımları 32 bayta hizalanır. `sizeof(struct S1)` 32 döndürür ve `S1` dört tamsayı tutmak için gereken 16 bayttan sonra 16 doldurma baytı vardır. Her bir **int** üyesi 4 baytlık hizalama gerektirir, ancak yapının kendisi için hizalama 32 olarak bildirilmiştir. Bu nedenle, Genel hizalama 32 ' dir.

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

Bu örnekte `sizeof(struct S2)`, en büyük hizalama gereksiniminden (8 ' den çok) çok katı olduğundan, tam olarak üye boyutlarının toplamı olan 16 döndürür.

```cpp
__declspec(align(8)) struct S2 {
   int a, b, c, d;
};
```

Aşağıdaki örnekte `sizeof(struct S3)` 64 döndürür.

```cpp
struct S3 {
   struct S1 s1;   // S3 inherits cache alignment requirement
                  // from S1 declaration
   int a;         // a is now cache aligned because of s1
                  // 28 bytes of trailing padding
};
```

Bu örnekte `a`, bu örnekte 4 bayt olmak üzere doğal türünün hizalandığına dikkat edin. Ancak, `S1` 32 bayt hizalı olmalıdır. Yirmi sekiz basamaklı doldurma `a`, `s1` 32 uzaklığında başlar. `S4`, yapıda en büyük hizalama gereksinimi olduğundan `S1`hizalama gereksinimini devralır. `sizeof(struct S4)` 64 döndürür.

```cpp
struct S4 {
   int a;
   // 28 bytes padding
    struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

Aşağıdaki üç değişken bildirimi de `__declspec(align(#))`kullanır. Her durumda, değişken 32 bayta hizalı olmalıdır. Dizi durumunda, her dizi üyesi değil, dizinin temel adresi 32 bayt hizalı olur. `__declspec(align(#))`kullandığınızda her dizi üyesinin `sizeof` değeri etkilenmez.

```cpp
CACHE_ALIGN int i;
CACHE_ALIGN int array[128];
CACHE_ALIGN struct s2 s;
```

Bir dizinin her üyesini hizalamak için, bu gibi bir kod kullanılmalıdır:

```cpp
typedef CACHE_ALIGN struct { int a; } S5;
S5 array[10];
```

Bu örnekte, yapının kendisini hizalayarak ve ilk öğenin hizalanmasının aynı etkiye sahip olduğuna dikkat edin:

```cpp
CACHE_ALIGN struct S6 {
   int a;
   int b;
};

struct S7 {
   CACHE_ALIGN int a;
               int b;
};
```

`S6` ve `S7` aynı hizalama, ayırma ve boyut özelliklerine sahiptir.

Bu örnekte, a, b, c ve d 'nin başlangıç adreslerinin hizalaması sırasıyla 4, 1, 4 ve 1 ' dir.

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

Yığın üzerinde bellek ayrıldığında hizalama, hangi ayırma işlevinin çağrdığına bağlıdır.  Örneğin, `malloc`kullanırsanız, sonuç, işlenen boyutuna bağlıdır. *Bağımsız değişken* > = 8 ise, döndürülen bellek 8 bayt hizalı olur. *Arg* < 8 ise, döndürülen belleğin hizalaması 2 ' nin ilk gücünden *bağımsız değişken*olur. Örneğin, malloc (7) kullanırsanız, hizalama 4 bayttır.

## <a name="defining-new-types-with-__declspecalign"></a><a name="vclrf_declspecaligntypedef"></a>__Declspec ile yeni türler tanımlama (align (#))

Hizalama özelliği ile bir tür tanımlayabilirsiniz.

Örneğin, hizalama değeri bu şekilde bir `struct` tanımlayabilirsiniz:

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

Artık `aType` ve `bType` aynı boyutta (8 bayt), ancak `bType` türündeki değişkenler 32 bayt hizalı.

## <a name="aligning-data-in-thread-local-storage"></a><a name="vclrfthreadlocalstorageallocation"></a>Iş parçacığı yerel depolama alanında verileri hizalama

`__declspec(thread)` özniteliğiyle oluşturulan ve görüntünün TLS bölümüne yerleştirilen statik iş parçacığı yerel depolaması (TLS), normal statik verilerle tam olarak hizalama için geçerlidir. TLS verileri oluşturmak için işletim sistemi, TLS bölümünün boyutunu bellek ayırır ve TLS bölüm hizalaması özniteliğine uyar.

Bu örnekte, hizalanmış verileri iş parçacığı yerel depolama alanına yerleştirmek için çeşitli yollar gösterilmektedir.

```cpp
// put an aligned integer in TLS
__declspec(thread) __declspec(align(32)) int a;

// define an aligned structure and put a variable of the struct type
// into TLS
__declspec(thread) __declspec(align(32)) struct F1 { int a; int b; } a;

// create an aligned structure
struct CACHE_ALIGN S9 {
   int a;
   int b;
};
// put a variable of the structure type into TLS
__declspec(thread) struct S9 a;
```

## <a name="how-align-works-with-data-packing"></a><a name="vclrfhowalignworkswithdatapacking"></a>Veri paketleme ile nasıl hizalanır?

`/Zp` derleyici seçeneği ve `pack` pragması, yapı ve birleşim üyeleri için veri paketleme etkisine sahiptir. Bu örnekte `/Zp` ve `__declspec(align(#))` birlikte nasıl çalıştığı gösterilmektedir:

```cpp
struct S {
   char a;
   short b;
   double c;
   CACHE_ALIGN double d;
   char e;
   double f;
};
```

Aşağıdaki tabloda, her üyenin farklı `/Zp` (veya #pragma `pack`) değerlerinin altında, iki etkileşim kurmayı gösteren bir konum listelenmektedir.

|Değişken|/Zp1|/ZP2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|vadeli|41|42|44|48|
|sizeof|64|64|64|64|

Daha fazla bilgi için bkz. [/Zp (struct üye hizalaması)](../build/reference/zp-struct-member-alignment.md).

Nesnenin boşluğu, `__declspec(align(#))` bir önceki nesnenin ve geçerli paketleme ayarının sapmasını temel alır. Bu durumda, hizalama önceki nesnenin sapmasını ve nesne için `__declspec(align(#))` değeri temel alır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[ARM ABI Kurallarına Genel Bakış](../build/overview-of-arm-abi-conventions.md)<br/>
[x64 yazılım kuralları](../build/x64-software-conventions.md)
