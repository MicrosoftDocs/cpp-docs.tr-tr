---
title: align (C++)
ms.date: 12/17/2018
f1_keywords:
- align_cpp
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
ms.openlocfilehash: 0a1212f1c78f49029f82be5a2f5d82ea1788b6e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227666"
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 ve üzeri sürümlerde, **`alignas`** hizalamayı denetlemek Için c++ 11 standart tanımlayıcısını kullanın. Daha fazla bilgi için bkz. [Hizalama](../cpp/alignment-cpp-declarations.md).

**Microsoft'a Özgü**

`__declspec(align(#))`Kullanıcı tanımlı verilerin hizalamasını tam olarak denetlemek için kullanın (örneğin, statik ayırmalar veya bir işlevdeki otomatik veriler).

## <a name="syntax"></a>Sözdizimi

> **__declspec (align (** *#* **))** *bildirimci*

## <a name="remarks"></a>Açıklamalar

En son işlemci yönergelerini kullanan uygulamalar yazmak, bazı yeni kısıtlamalar ve sorunlar getirir. Birçok yeni yönerge, 16 baytlık sınırlara hizalanmış veriler gerektirir. Ayrıca, sık kullanılan verileri işlemcinin önbellek satırı boyutuna hizalayarak, önbellek performansını geliştirebilirsiniz. Örneğin, boyutu 32 bayttan daha az olan bir yapı tanımlarsanız, bu yapı türünün nesnelerinin etkin bir şekilde önbelleğe alınıp alınmamasını sağlamak için 32 bayt hizalaması isteyebilirsiniz.

\#hizalama değeridir. Geçerli girişler 2, 4, 8, 16, 32 veya 64 gibi 1 ile 8192 (bayt) arasında iki adet tamsayı üstür. `declarator`hizalanmış olarak bildirdiğiniz veri.

Türünün hizalama gereksinimi olan bir değer değeri döndürme hakkında daha fazla bilgi için `size_t` bkz [`alignof`](../cpp/alignof-operator.md) .. 64 bit işlemcileri hedeflerken hizalanmamış işaretçiler bildirme hakkında daha fazla bilgi için bkz [`__unaligned`](../cpp/unaligned.md) ..

`__declspec(align(#))`Bir **`struct`** ,, veya tanımladığınızda **`union`** **`class`** veya bir değişken bildirdiğinizde kullanabilirsiniz.

Derleyici, bir kopyalama veya veri dönüştürme işlemi sırasında verilerin hizalama özniteliğini garanti etmez veya korumaya çalışır. Örneğin, [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md) ile belirtilen bir yapıyı `__declspec(align(#))` herhangi bir konuma kopyalayabilir. Normal ayırıcılar (örneğin, [`malloc`](../c-runtime-library/reference/malloc.md) C++ [`operator new`](new-operator-cpp.md) ve Win32 ayırıcıları), genellikle yapılar `__declspec(align(#))` veya yapı dizileri için yeterince hizalı olmayan bellek döndürür. Bir kopyalama veya veri dönüştürme işleminin hedefinin doğru şekilde hizalandığından emin olmak için kullanın [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md) . Ya da kendi ayırıcıyı yazın.

İşlev parametreleri için hizalama belirtemezsiniz. Bir hizalama özniteliği olan verileri yığında değere göre geçirdiğinizde, hizalaması çağırma kuralına göre denetlenir. Çağrılan işlevde veri hizalaması önemliyse, kullanmadan önce parametresini doğru hizalanmış belleğe kopyalayın.

Olmadan `__declspec(align(#))` , derleyici genellikle hedef işlemciye, verilerin boyutuna ve 32 bitlik işlemcilerde 4 baytlık sınırlara ve 64 bit işlemcilerde 8 baytlık sınırlara göre verileri doğal sınırlara göre hizalar. Sınıflardaki veya yapılardaki veriler, doğal hizalamasının ve geçerli paketleme ayarının (from `#pragma pack` veya derleyici seçeneğinden) en az bir sınıf veya yapıda hizalanır `/Zp` .

Bu örnek, öğesinin kullanımını gösterir `__declspec(align(#))` :

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

Bu türün artık 32 baytlık bir hizalama özniteliği vardır. Tüm statik ve otomatik örneklerin 32 baytlık bir sınır üzerinde başlayacağı anlamına gelir. Bu tür bir üye olarak belirtilen ek yapı türleri, bu türün hizalama özniteliğini korur, diğer bir deyişle, bir öğesi olan herhangi bir yapıda, `Str1` en az 32 Hizalama özniteliği vardır.

Burada `sizeof(struct Str1)` 32 eşittir. Bir `Str1` nesne dizisi oluşturulduysa ve dizinin temeli 32 bayt hizalı ise, dizinin her üyesinin da 32 baytlık hizalı olduğunu belirtir. Temeli dinamik bellekte doğru şekilde hizalanan bir dizi oluşturmak için kullanın [`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md) . Ya da kendi ayırıcıyı yazın.

**`sizeof`** Herhangi bir yapının değeri, son üyenin ve bu üyenin boyutunun en büyük üye hizalama değerinin veya tüm yapı hizalama değerinin (hangisi daha büyükse) en yakın katına yuvarlandı.

Derleyici, yapı hizalaması için bu kuralları kullanır:

- İle geçersiz kılınmadıkça `__declspec(align(#))` , skaler bir yapı üyesinin hizalaması en az boyutu ve geçerli paketleme olur.

- Geçersiz kılınmadığı müddetçe `__declspec(align(#))` , bir yapının hizalaması, üyelerinin tek tek hizalamasının en fazla sayısıdır.

- Yapı üyesi, bir önceki üyenin sonundaki uzaklığa eşit veya daha büyük hizalamasının en küçük katı olan üst yapısının başlangıcından itibaren bir uzaklığa yerleştirilir.

- Bir yapının boyutu, hizalamasının en küçük katı veya en son üyesinin sonuna kadar olan uzaklığa eşittir.

`__declspec(align(#))`yalnızca hizalama kısıtlamalarını artırabilir.

Daha fazla bilgi için bkz.

- [`align`Örnekler](#vclrfalignexamples)

- [İle yeni türler tanımlama`__declspec(align(#))`](#vclrf_declspecaligntypedef)

- [Iş parçacığı yerel depolama alanında verileri hizalama](#vclrfthreadlocalstorageallocation)

- [`align`Veri paketleme ile çalışma](#vclrfhowalignworkswithdatapacking)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

## <a name="align-examples"></a><a name="vclrfalignexamples"></a>Örnekleri Hizala

Aşağıdaki örneklerde, `__declspec(align(#))` veri yapılarının boyutunu ve hizalamasını nasıl etkilediği gösterilmektedir. Örneklerde aşağıdaki tanımlar varsayılmaktadır:

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

Bu örnekte, `S1` Yapı kullanılarak tanımlanmıştır `__declspec(align(32))` . `S1`Bir değişken tanımı veya diğer tür bildirimlerinde tüm kullanımları 32 bayt hizalı. `sizeof(struct S1)`32 döndürür ve `S1` dört tamsayının saklanması için gereken 16 baytlık bir 16 doldurma baytı içerir. Her **`int`** üye 4 baytlık hizalama gerektirir, ancak yapının kendisi için hizalama 32 olarak belirtilir. Sonra, Genel hizalama 32 ' dir.

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

Bu örnekte, `sizeof(struct S2)` en büyük hizalama gereksiniminden (8 ' den çok) çok katı olduğundan, tam olarak üye boyutlarının toplamı olan 16 döndürür.

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

Bu örnekte, `a` doğal türünün hizalandığına, bu durumda 4 bayt olduğuna dikkat edin. Ancak, `S1` 32 bayt hizalı olmalıdır. 28 bayt doldurma izler `a` , bu nedenle `s1` 32 uzaklığında başlar. `S4``S1`yapıda en büyük hizalama gereksinimi olduğundan, öğesinin hizalama gereksinimini devralır. `sizeof(struct S4)`64 döndürür.

```cpp
struct S4 {
   int a;
   // 28 bytes padding
   struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

Aşağıdaki üç değişken bildirimi de kullanır `__declspec(align(#))` . Her durumda, değişken 32 bayta hizalı olmalıdır. Dizide, her dizi üyesi değil, dizinin temel adresi 32 bayt hizalı olur. **`sizeof`** Her dizi üyesinin değeri, kullandığınızda etkilenmez `__declspec(align(#))` .

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

`S6`ve `S7` aynı hizalama, ayırma ve boyut özelliklerine sahiptir.

Bu örnekte, a, b, c ve d 'nin başlangıç adreslerinin hizalaması sırasıyla 4, 1, 4 ve 1 ' dir.

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

Yığın üzerinde bellek ayrıldığında hizalama, hangi ayırma işlevinin çağrdığına bağlıdır.  Örneğin, kullanırsanız `malloc` , sonuç, işlenen boyutuna bağlıdır. *Bağımsız değişken* >= 8 ise, döndürülen bellek 8 bayt hizalı olur. *Arg* < 8 ise, döndürülen belleğin hizalaması 2 ' nin ilk gücünden *bağımsız değişken*olur. Örneğin, kullanırsanız `malloc(7)` , hizalama 4 bayttır.

## <a name="defining-new-types-with-__declspecalign"></a><a name="vclrf_declspecaligntypedef"></a>İle yeni türler tanımlama`__declspec(align(#))`

Hizalama özelliği ile bir tür tanımlayabilirsiniz.

Örneğin, **`struct`** Şu şekilde bir hizalama değeri ile bir tanımlayabilirsiniz:

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

Artık `aType` ve `bType` aynı boyutta (8 bayt), ancak tür değişkenleri `bType` 32 bayt hizalı.

## <a name="aligning-data-in-thread-local-storage"></a><a name="vclrfthreadlocalstorageallocation"></a>İş parçacığı yerel depolama alanında verileri hizalama

Özniteliğiyle oluşturulan statik iş parçacığı yerel depolaması (TLS) `__declspec(thread)` ve görüntünün TLS bölümüne, normal statik veriler gibi hizalama için de uygundur. TLS verileri oluşturmak için işletim sistemi, TLS bölümünün boyutunu bellek ayırır ve TLS bölüm hizalaması özniteliğine uyar.

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

## <a name="how-align-works-with-data-packing"></a><a name="vclrfhowalignworkswithdatapacking"></a>`align`Veri paketleme ile çalışma

`/Zp`Derleyici seçeneği ve pragma, `pack` Yapı ve birleşim üyeleri için veri paketleme etkisine sahiptir. Bu örnek, nasıl `/Zp` birlikte çalıştığını gösterir `__declspec(align(#))` :

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

Aşağıdaki tabloda, her üyenin farklı `/Zp` (veya `#pragma pack` ) değerler altında, iki etkileşime geçme şeklini gösteren fark listelenmektedir.

|Değişken|/ZP1|/ZP2|/ZP4|/ZP8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|f|41|42|44|48|
|sizeof|64|64|64|64|

Daha fazla bilgi için bkz. [ `/Zp` (struct üye hizalaması)](../build/reference/zp-struct-member-alignment.md).

Bir nesnenin boşluğu, nesnenin bir özniteliği yoksa, önceki nesnenin ve geçerli paketleme ayarının sapmasını temel alır `__declspec(align(#))` . Bu durumda, hizalama önceki nesnenin sapmasını ve `__declspec(align(#))` nesnenin değerini temel alır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)<br/>
[ARM ABı kurallarına genel bakış](../build/overview-of-arm-abi-conventions.md)<br/>
[x64 yazılım kuralları](../build/x64-software-conventions.md)
