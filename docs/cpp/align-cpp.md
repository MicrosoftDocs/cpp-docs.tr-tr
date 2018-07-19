---
title: Hizalama (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- align_cpp
dev_langs:
- C++
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54a83adda5acc51bd7e2d85e907d84e62a70d5cb
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940734"
---
# <a name="align-c"></a>align (C++)

Visual Studio 2015 ve sonraki sürümlerinde, C ++ 11 standardı kullanın `alignas` denetim hizalaması için tanımlayıcısı. Daha fazla bilgi için [hizalama](../cpp/alignment-cpp-declarations.md).

**Microsoft'a özgü**

Kullanım `__declspec(align(#))` tam olarak (örneğin, statik atamalar veya otomatik veriler bir işlevde) kullanıcı tanımlı veri hizalamasını denetlemek için.

## <a name="syntax"></a>Sözdizimi

> **__declspec (hizalama (** *#* **))** *bildirimcisi*  

## <a name="remarks"></a>Açıklamalar

Son İşlemci yönergeleri kullanan uygulamalar yazmak, bazı yeni sınırlamalar ve sorunlar getirir. Özellikle çoğu yeni yönerge veri 16 bayt sınırlarıyla hizalanmasını gerektirir. Ayrıca, sık kullanılan veriler için belirli bir işlemcinin önbellek satırı boyutuna hizalayarak önbellek performansını arttırın. Örneğin, boyutu 32 bayttan küçük olan bir yapı tanımlarsanız, yapı türündeki nesnelerin etkili bir şekilde önbelleğe emin olmak için 32 bayt ile hizalamanız isteyebilirsiniz.

\# Hizalama değeridir. Geçerli girişler 1 8192 (bayt), 2, 4, 8, 16, 32 veya 64 gibi ikinin tamsayı powers oluşur. `declarator` hizalı olarak bildirdiğiniz veridir.

Dönüş türü bir değeri hakkında bilgi için `size_t` türün hizalama gereksinimi olan bkz [__alignof](../cpp/alignof-operator.md). 64-bit işlemcileri hedeflerken hizalanmayan işaretçileri bildirme hakkında daha fazla bilgi için bkz: [__unaligned](../cpp/unaligned.md).

Kullanabileceğiniz `__declspec(align(#))` tanımladığınızda bir **yapı**, **birleşim**, veya **sınıfı**, veya bir değişken bildirdiğinizde.

Derleyici garanti vermez veya kopyalama ya da veri dönüştürme işlemi sırasında veri hizalama özniteliğini korumak çalışır. Örneğin, [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) ile bildirilen bir yapı kopyalayabilirsiniz `__declspec(align(#))` herhangi bir konuma. Unutmayın, normal ayırıcılar — Örneğin, [malloc](../c-runtime-library/reference/malloc.md), C++ [new işleci](new-operator-cpp.md)ve Win32 ayırıcıların — dönüş genellikle yeterince için hizalanmamış bellek `__declspec(align(#))` yapıları veya dizileri yapılar. Hedef bir kopya veya veri dönüştürme işlemi düzgün hizalanmış sağlamak için kullanmak [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), veya kendi ayırıcınızı yazın.

İşlev parametreleri için hizalama belirtemezsiniz. Hizalama özniteliğine sahip veri değerine göre yığında geçirildiğinde hizalamanın çağırma kuralı tarafından denetlenir. Veri hizalama çağrılan işlev önemli ise, parametre kullanmadan önce düzgün şekilde hizalanmış belleğe kopyalayın.

Olmadan `__declspec(align(#))`, derleyici genellikle verileri hedef işlemci ve 4 baytlık sınırlarda, 32-bit işlemciler üzerinde en fazla veri boyutuna göre doğal sınırlara ve 64-bit işlemci 8 baytlık sınırlardaki hizalar. Sınıflar veya yapılardaki veriler, sınıf veya yapıda doğal hizalaması ve geçerli paket ayarının minimumunda hizalanır (#pragma gelen **paketi** veya **/ZP** derleyici seçeneği).

Bu örnek kullanımını gösterir `__declspec(align(#))`:

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

Bu tür artık 32 bayt hizalama özniteliğine sahiptir. Bu, tüm örnekleri statik ve otomatik bir 32 bayt sınırlarında başlaması anlamına gelir. Bir üye olarak bu türle bildirilen ek yapı türleri, bu türün hizalama özniteliğini korumak, diğer bir deyişle, tüm yapısı `Str1` bir öğe bir en az 32 hizalama özniteliğine sahip olduğundan.

Unutmayın `sizeof(struct Str1)` 32 değerine eşittir. Bu, Str1 nesnelerinden oluşan bir dizi oluşturulur ve dizi temeli 32 bayt hizalı, dizinin her üyesini de 32 bayt hizalı olduğunu gösterir. Dinamik bellek temeli düzgün şekilde hizalanmış bir dizi oluşturmak için kullanın [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), veya kendi ayırıcınızı yazın.

`sizeof` Herhangi bir yapının değeri en büyük üye hizalama değerinin ya da tam yapı hizalama değerinin en yakın katına yuvarlanmış, bu üyenin boyutudur yanı sıra son üye uzaklığı, hangisi daha büyükse.

Derleyici, yapı hizalama için kurallar kullanır:

- İle geçersiz kılınmadığı sürece `__declspec(align(#))`, boyutunun ve geçerli paketleme en azından bir skalar yapı üyesinin hizalanması gereklidir.

- İle geçersiz kılınmadığı sürece `__declspec(align(#))`, bir yapının hizalanması, bireysel hizalanmalarının en yüksek değer.

- Yapı üyesi, bir uzaklık değerinden büyük veya önceki üyenin sonuna uzaklığı eşit hizalamanın en küçük katı kendi ana yapısının başlangıcından yerleştirilir.

- Büyük veya bitiş, son üyesinin uzaklık eşit hizalamanın en küçük katı bir yapının boyutudur.

`__declspec(align(#))` yalnızca hizalama kısıtlamalarını artırır.

Daha fazla bilgi için bkz.:

- [Örnekleri Hizala](#vclrfalignexamples)

- [__Declspec(align(#)) ile yeni türler tanımlama](#vclrf_declspecaligntypedef)

- [İş parçacığı yerel depolamasında verileri hizalama](#vclrfthreadlocalstorageallocation)

- [Nasıl veri Paketlemeyle hizalama](#vclrfhowalignworkswithdatapacking)

- [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md) (x64 belirli)

##  <a name="vclrfalignexamples"></a> Örnekleri Hizala

Aşağıdaki örneklerde gösterildiği nasıl `__declspec(align(#))` boyutu ve hizalama veri yapılarının etkiler. Örnekler aşağıdaki tanımlamaları varsayar:

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

Bu örnekte, `S1` yapısı, kullanılarak tanımlanır `__declspec(align(32))`. Tüm kullanımları `S1` değişken bir tanım veya diğer tür 32 bayt hizalıdır bildirimlerdir. `sizeof(struct S1)` 32 döndürür ve `S1` 16 doldurma baytı dört tamsayının tutulması gereken 16 bayt vardır. Her **int** üyesi 4 baytlık hizalama gerektirir, ancak yapının kendi hizalaması 32 olarak bildirilmiştir. Bu nedenle, Genel hizalama 32'dir.

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

Bu örnekte, `sizeof(struct S2)` döndürür, 16, en büyük hizalama gereksinimi (8'in katı) katı olduğundan, tam olarak üye boyutlarının toplamıdır.

```cpp
__declspec(align(8)) struct S2 {
   int a, b, c, d;
};
```

Aşağıdaki örnekte, `sizeof(struct S3)` 64 değerini döndürür.

```cpp
struct S3 {
   struct S1 s1;   // S3 inherits cache alignment requirement
                  // from S1 declaration
   int a;         // a is now cache aligned because of s1
                  // 28 bytes of trailing padding
};
```

Bu örnekte, dikkat `a` doğal türde hizalaması kendi, bu durumda 4 bayt vardır. Ancak, `S1` 32 baytla uyumlu olmalıdır. Yirmi sekiz bayt doldurma `a`, böylece `s1` 32 uzaklığında başlar. `S4` ardından öğesinin hizalama gereksinimini devralır `S1`yapısındaki en büyük hizalama gereksinimi olduğundan. `sizeof(struct S4)` 64 değerini döndürür.

```cpp
struct S4 {
   int a;
   // 28 bytes padding
    struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

Aşağıdaki üç değişken bildirimi de `__declspec(align(#))`. Her durumda, değişken 32 baytla olmalıdır. Dizi olması durumunda değil her dizi üyesini dizinin temel adresi 32 bayt hizalıdır ' dir. `sizeof` Kullandığınızda her dizi üyesini etkilenmez için bir değer `__declspec(align(#))`.

```cpp
CACHE_ALIGN int i;
CACHE_ALIGN int array[128];
CACHE_ALIGN struct s2 s;
```

Bir dizinin her üyesini hizalamak için bu gibi bir kod kullanılmalıdır:

```cpp
typedef CACHE_ALIGN struct { int a; } S5;
S5 array[10];
```

Bu örnekte, yapının kendisiyle hizalanmasının ve ilk öğeyle hizalanmasının aynı etkiye sahip olduğuna dikkat edin:

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

Bu örnekte, adreslerinin hizalaması başlangıç a, b, c ve D'nin 4, 1, 4 ve 1, sırasıyla.

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

Yığında bellek tahsis edildiğinde hizalama hangi ayırma işlevinin çağrıldığına bağlıysa.  Örneğin, kullanırsanız **malloc**, sonuç işlenen boyutuna bağlıdır. Varsa *arg* > = 8, 8 byte hizalı olan bellek döndürdü. Varsa *arg* < 8, döndürülen bellek hizalama 2'in ilk üssü olan küçüktür *arg*. Örneğin, malloc(7) kullanırsanız, hizalama 4 bayt ' dir.

##  <a name="vclrf_declspecaligntypedef"></a> __Declspec(align(#)) ile yeni türler tanımlama

Hizalama özelliğine sahip bir tür tanımlayabilirsiniz.

Örneğin, tanımlayabileceğiniz bir `struct` bu şekilde bir hizalama değeriyle:

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

Şimdi, `aType` ve `bType` aynı boyuttadır (8 bayt) ancak türündeki değişkenler `bType` olan 32 bayt hizalıdır.

##  <a name="vclrfthreadlocalstorageallocation"></a> İş parçacığı yerel depolamasında verileri hizalama

Oluşturulan statik iş parçacığı yerel depolama (TLS) `__declspec(thread)` özniteliği ve tam olarak normal statik veriler gibi hizalama için resim çalışmalarında TLS bölümüne yerleştirin. TLS veri oluşturmak için işletim sistemi, TLS bölümünün boyutuna bellek ayırır ve TLS bölümü hizalama özniteliğini dikkate alır.

Bu örnek, iş parçacığı yerel deposuna hizalanmış verileri yerleştirmek için çeşitli yollar gösterir.

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

##  <a name="vclrfhowalignworkswithdatapacking"></a> Nasıl veri Paketlemeyle hizalama

**/ZP** derleyici seçeneği ve **paketi** pragma yapı ve birleşim üyeleri için verileri paketleme etkisi vardır. Bu örnek gösterir nasıl **/ZP** ve `__declspec(align(#))` birlikte çalışır:

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

Aşağıdaki tabloda çeşitli her üyenin uzaklığını listeler **/ZP** (veya #pragma **paketi**) nasıl etkileştiğini gösteren değer.

|Değişken|/Zp1|/ Zp2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1.|2|2|2|
|c|3|4|4|8|
|d|32|32|32|32|
|e|40|40|40|40|
|F|41|42|44|48|
|sizeof (S)|64|64|64|64|

Daha fazla bilgi için [/Zp (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md).

Nesneye sahip olmadığı sürece bir nesnenin uzaklığı önceki nesne ve geçerli paketleme ayarına sapmasını dayalı bir `__declspec(align(#))` özniteliği, bu durumda, hizalama önceki nesnenin uzaklığı üzerinde temel alır ve `__declspec(align(#))` nesne değeri.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)  
[ARM ABI Kurallarına Genel Bakış](../build/overview-of-arm-abi-conventions.md)  
[x64 Çağırma Kurallarına Genel Bakış](../build/overview-of-x64-calling-conventions.md)  
