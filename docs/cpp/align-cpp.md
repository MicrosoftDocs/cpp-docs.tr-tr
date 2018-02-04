---
title: Hizalama (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- align_cpp
dev_langs:
- C++
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10c83ebb195cf4ee75c7be15b4d2ab9607f46743
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 ve sonraki sürümlerinde, C ++ 11 standardını kullanan `alignas` denetim hizalaması için tanımlayıcısı. Daha fazla bilgi için bkz: [hizalama](../cpp/alignment-cpp-declarations.md).

**Microsoft Specific**

Kullanım `__declspec(align(#))` tam olarak (örneğin, statik ayırma veya bir işlevdeki otomatik veri) kullanıcı tanımlı veri hizalamasını denetlemek için.

## <a name="syntax"></a>Sözdizimi

> **__declspec (hizalama (**  *#*  **))** *bildirimcisi*  

## <a name="remarks"></a>Açıklamalar

En son işlemci yönergeleri kullanan uygulamalar yazma, bazı yeni kısıtlamaları ve sorunlarını tanıtır. Özellikle, birçok yeni yönergeleri veri 16 bayt sınırları hizalanmalıdır gerektirir. Ayrıca, belirli bir işlemci önbellek satır boyutu için sık kullanılan veri hizalayarak önbellek performansınızı iyileştirir. Örneğin, büyüklüğü 32 bayt'tan küçük olan bir yapı tanımlarsanız, o yapısı türündeki nesneleri verimli bir şekilde önbelleğe alınan emin olmak için 32 bayt Hizala isteyebilirsiniz.

\#Hizalama değerdir. 1 8192 (bayt), 2, 4, 8, 16, 32 veya 64 gibi iki tamsayı tabanların geçerli girişlerdir. `declarator`hizalı gibi bildirme verilerdir.

Türünde bir değer döndürmesi hakkında bilgi için `size_t` türü hizalama gereksinimi olan bkz [__alignof](../cpp/alignof-operator.md). 64-bit işlemciler hedeflerken hizalanmamış işaretçileri bildirme hakkında daha fazla bilgi için bkz: [__unaligned](../cpp/unaligned.md).

Kullanabileceğiniz `__declspec(align(#))` tanımladığınızda bir `struct`, `union`, veya `class`, veya bir değişken bildirme zaman.

Derleyici garanti ya da bir kopyalama veya veri dönüştürme işlemi sırasında veri hizalama özniteliğini korumak girişimi. Örneğin, [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) ile bildirilen yapı kopyalayabilirsiniz `__declspec(align(#))` herhangi bir konuma. Not sıradan allocators — Örneğin, [malloc](../c-runtime-library/reference/malloc.md), C++ [new işleci](new-operator-cpp.md)ve Win32 allocators — dönüş genellikle yeterince hizalanır olmayan bellek `__declspec(align(#))` yapıları veya dizileri yapıları. Hedef bir kopya veya veri dönüştürme işlemi için doğru hizalanır güvence altına almak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), ya da kendi ayırıcısı yazma.

İşlev parametreleri için hizalama belirtemezsiniz. Bir hizalama özniteliği veri yığında değeriyle geçirildiğinde kendi hizalama çağırma tarafından denetlenir. Veri hizalama çağrılan işlev önemliyse, kullanmadan önce doğru hizalanmış belleğe parametresi kopyalayın.

Olmadan `__declspec(align(#))`, derleyici genellikle verileri hedef işlemci ve en fazla 32-bit işlemciler, 4-bayt sınırları verilerin boyutunu temel alarak doğal sınırları ve 64-bit işlemciler 8-bayt sınırları hizalar. Sınıf veya yapı en az doğal hizalama ve geçerli paket ayarı hizalanması veri sınıflarını veya yapıları (#pragma gelen `pack` veya **/Zp** derleyici seçeneği).

Bu örnek kullanımını gösteren `__declspec(align(#))`:

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

Bu tür şimdi bir 32 baytlık hizalama özniteliği vardır. Bu, tüm statik ve otomatik örnekleri 32 baytlık sınırında Başlat anlamına gelir. Bu tür bir üye olarak bildirilen ek yapı türleri bu türü hizalama özniteliğini korumak, diğer bir deyişle, tüm yapısı `Str1` en az 32 hizalama özniteliği bir öğeye sahip olarak.

Unutmayın `sizeof(struct Str1)` 32 ile eşittir. Bu, Str1 nesnelerinin bir dizisi oluşturulur ve 32-bayt hizalı dizisinin temel ise, her bir dizi üyesi de 32 bayt hizalı değil anlamına gelir. Dinamik bellek, temel düzgün hizalanmış bir dizi oluşturmak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), ya da kendi ayırıcısı yazma.

`sizeof` Herhangi yapısı için değer son üye yanı sıra, o üyenin boyutu, en büyük üyesi hizalama değeri veya tüm yapı hizalama değeri en yakın katına yuvarlanan uzaklığını, hangisi daha büyük.

Derleyici, bu kurallar için yapı hizalama kullanır:

- İle geçersiz kılınmadığı sürece `__declspec(align(#))`, skaler yapı üyesi hizalama boyutuna ve geçerli paket en düşük gereksinimdir.

- İle geçersiz kılınmadığı sürece `__declspec(align(#))`, bir yapı hizalama onun üyeleri tek tek hizalamasını, en yüksek değer.

- Yapı üyesi en küçük birden çok alt hizalama önceki üyeyi sonuna uzaklığını eşit veya daha büyük olan üst yapısını başından bir uzaklığındaki yerleştirilir.

- En küçük birden çok alt hizalama son üyesini sonuna uzaklığını eşit veya daha büyük bir yapı boyutudur.

`__declspec(align(#))`Hizalama kısıtlamaları yalnızca artırabilirsiniz.

Daha fazla bilgi için bkz.:

- [Örnekler hizalayın](#vclrfalignexamples)

- [__Declspec(align(#)) ile yeni türleri tanımlama](#vclrf_declspecaligntypedef)

- [İş parçacığı yerel depolama birimindeki verileri hizalama](#vclrfthreadlocalstorageallocation)

- [Veri paketleme ile Works nasıl hizalayın](#vclrfhowalignworkswithdatapacking)

- [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md) (x64 belirli)

##  <a name="vclrfalignexamples"></a>Örnekler hizalayın

Aşağıdaki örneklerde gösterildiği nasıl `__declspec(align(#))` boyutunu ve veri yapıları hizalamasını etkiler. Örnekler aşağıdaki tanımları varsayın:

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

Bu örnekte, `S1` yapısı kullanarak tanımlanmış `__declspec(align(32))`. Tüm kullanımlarını `S1` değişken tanımı için veya diğer tür bildirimleri 32 bayt hizalı olan. `sizeof(struct S1)`32, döndürür ve `S1` 16 dört tamsayılar tutmak için gereken bayt izleyen 16 doldurma bayt vardır. Her `int` üye 4-bayt hizalama gerektiriyor, ancak yapısı hizalamasını 32 olarak bildirilir. Bu nedenle, Genel hizalama 32'dir.

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

Bu örnekte, `sizeof(struct S2)` döndürür 16, en büyük hizalama gereksinim (birden fazla 8) birden fazla olduğu için tam olarak üye boyutlarının toplamıdır.

```cpp
__declspec(align(8)) struct S2 {
   int a, b, c, d;
};
```

Aşağıdaki örnekte, `sizeof(struct S3)` 64 döndürür.

```cpp
struct S3 {
   struct S1 s1;   // S3 inherits cache alignment requirement
                  // from S1 declaration
   int a;         // a is now cache aligned because of s1
                  // 28 bytes of trailing padding
};
```

Bu örnekte, dikkat `a` doğal türü, bu durumda, 4 bayt hizalamasını sahiptir. Ancak, `S1` 32-bayt hizalı gerekir. İzleme doldurma yirmi sekiz bayt `a`, böylece `s1` uzaklığı 32 başlar. `S4`Hizalama gereksinimi devralır `S1`, yapısındaki en büyük hizalama gereksinimi olduğundan. `sizeof(struct S4)`64 döndürür.

```cpp
struct S4 {
   int a;
   // 28 bytes padding
    struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

Aşağıdaki üç değişken bildirimleri de `__declspec(align(#))`. Her durumda, değişkeni 32 bayt hizalı olması gerekir. Söz konusu olduğunda, taban adresi olmayan her dizi üyesini dizisinin 32 bayt hizalı dizidir. `sizeof` Kullandığınızda her dizi üyesini etkilenmez için bir değer `__declspec(align(#))`.

```cpp
CACHE_ALIGN int i;
CACHE_ALIGN int array[128];
CACHE_ALIGN struct s2 s;
```

Bir dizinin her bir üyesi hizalamak için bu gibi kodu kullanılmalıdır:

```cpp
typedef CACHE_ALIGN struct { int a; } S5;
S5 array[10];
```

Bu örnekte, yapı hizalama ve ilk öğe hizalama aynı etkiye sahip dikkat edin:

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

`S6`ve `S7` aynı hizalama, ayırma ve boyutu özelliklere sahiptir.

Bu örnekte, başlangıç hizalama adresleri a, b, c ve d: 4, 1, 4 ve 1, sırasıyla.

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

Bellek ve yığında ayrılan zaman hizalama hangi ayırma işlevini çağırdı bağlıdır.  Örneğin, kullanırsanız `malloc`, sonuç işleneni boyutuna bağlıdır. Varsa *arg* > = 8, 8 baytlık hizalanması bellek döndürdü. Varsa *arg* < 8, döndürülen bellek hizalamasını olan 2'in ilk üssü değerinden *arg*. Örneğin, malloc(7) kullanırsanız, hizalama 4 bayt'tır.

##  <a name="vclrf_declspecaligntypedef"></a>__Declspec(align(#)) ile yeni türleri tanımlama

Bir hizalama karakteristiğini türüyle tanımlayabilirsiniz.

Örneğin, tanımlayabilirsiniz bir `struct` bu şekilde bir hizalama değeri:

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

Şimdi, `aType` ve `bType` aynı boyutta (8 bayt) ancak türündeki değişkenler `bType` 32 bayt hizalı şunlardır.

##  <a name="vclrfthreadlocalstorageallocation"></a>İş parçacığı yerel depolama birimindeki verileri hizalama

İle oluşturulan statik iş parçacığı yerel depolaması (TLS) `__declspec(thread)` özniteliği ve tam olarak normal statik verileri gibi hizalama görüntü works TLS bölümünde yerleştirin. TLS verileri oluşturmak için işletim sistemi TLS bölümünün boyutunu bellek ayırır ve TLS bölüm hizalama özniteliği dikkate alır.

Bu örnek, iş parçacığı yerel depolama alanına hizalanmış verileri yerleştirmek için çeşitli yollar gösterir.

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

##  <a name="vclrfhowalignworkswithdatapacking"></a>Veri paketleme ile Works nasıl hizalayın

**/Zp** derleyici seçeneği ve `pack` pragma yapı ve birleşim üyeleri için veri sevk etkisini sahip. Bu örnekte gösterilir nasıl **/Zp** ve `__declspec(align(#))` birlikte çalışır:

```c[[]]
struct S {
   char a;
   short b;
   double c;
   CACHE_ALIGN double d;
   char e;
   double f;
};
```

Aşağıdaki tabloda, çeşitli altında her üyesinin uzaklık listeler **/Zp** (veya #pragma `pack`) iki nasıl etkileşim gösteren değer.

|Değişken|/Zp1|/Zp2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1.|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|f|41|42|44|48|
|sizeof (S)|64|64|64|64|

Daha fazla bilgi için bkz: [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md).

Nesne olmadıkça bir nesne uzaklığını önceki nesne ve geçerli paket ayarı uzaklığını dayalı bir `__declspec(align(#))` özniteliği, önceki nesne uzaklığını hizalama; bu durumda dayanır ve `__declspec(align(#))` nesne değeri.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)  
[ARM ABI Kurallarına Genel Bakış](../build/overview-of-arm-abi-conventions.md)  
[x64 Çağırma Kurallarına Genel Bakış](../build/overview-of-x64-calling-conventions.md)  
