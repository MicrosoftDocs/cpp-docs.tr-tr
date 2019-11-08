---
title: MSVC deneysel Önişlemci genel bakış
description: MSVC Önişlemci, C/C++ standartları ile uyumluluk açısından güncelleştiriliyor.
ms.date: 11/06/2019
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 446603b34d9309c256afba9abd7234ae2ab16f5c
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73797178"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC deneysel Önişlemci genel bakış

Microsoft C++ Önişlemci, standartlara uygunluğu artırmak, longhataları onarmak ve resmi olarak tanımsız bazı davranışları değiştirmek için şu anda güncelleştiriliyor. Ayrıca, makro tanımlarındaki hatalarda uyarı almak için yeni Tanılamalar eklenmiştir.

Geçerli durumundaki bu değişiklikler, Visual Studio 2017 veya Visual Studio 2019 ' de [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Varsayılan ön işlemci davranışı önceki sürümlerde olduğu gibi kalır.

## <a name="new-predefined-macro"></a>Yeni önceden tanımlanmış makro

Hangi Önişlemci 'nin derleme zamanında kullanımda olduğunu tespit edebilirsiniz. Geleneksel Önişlemci 'nin kullanımda olup olmadığını söylemek için [MSVC\_\_](predefined-macros.md) önceden tanımlanmış makronun değerini denetleyin. Bu makro, kendisini destekleyen derleyicinin, Önişlemci 'nin çağrıldığı bağımsız sürümleriyle koşulsuz olarak ayarlanır. Geleneksel Önişlemci için değeri 1 ' dir. Bu, uyumsuz deneysel Önişlemci için 0 ' dır:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>Deneysel Önişlemci 'daki davranış değişiklikleri

Deneysel ön işlemci üzerindeki ilk iş, MSVC derleyicisinin geleneksel davranışlar nedeniyle şu anda engellenmiş olan kitaplıklarla kullanımını etkinleştirmek için tüm makro genişleimleri 'nin uyumlu hale getirilmesi konusunda odaklanılmıştır. Aşağıda, güncelleştirilmiş Önişlemci gerçek dünya projeleriyle test edilirken, daha yaygın olarak çalıştırılan bazı değişikliklerin bir listesi verilmiştir.

### <a name="macro-comments"></a>Makro açıklamaları

Geleneksel Önişlemci, Önişlemci belirteçleri yerine karakter arabelleklerine dayalıdır. Bu, aşağıdaki Önişlemci açıklama eli gibi olağandışı davranışa izin verir ve bu durum, uyumlu Önişlemci altında çalışmayacaktır:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

Standartlarla uyumlu düzeltmeler, `int myVal` uygun `#ifdef/#endif` yönergelerinin içinde bildirilmelidir:

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L # Val

Geleneksel Önişlemci, dize önekini yanlış bir şekilde dize öneki ile birleştirir [işleç (#)](stringizing-operator-hash.md) işlecinin sonucu:

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

Bu durumda, bitişik dize değişmez değerleri de makro genişletmesinden sonra birleştirildiğinden `L` ön eki gereksizdir. Geriye dönük olarak uyumlu düzeltmeler, tanımı aşağıdaki şekilde değiştirmek için kullanılır:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Aynı sorun, bağımsız değişkeni geniş bir dize değişmez değeri olarak "stringize" olan kolay makrolar içinde de bulunur:

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

Sorunu çeşitli yollarla giderebilirsiniz:

- Önek eklemek için `L""` ve `#str` dize birleştirmesini kullanın. Bu, bitişik dize değişmez değerleri makro genişletmesinden sonra birleştirildiğinden işe yarar:

   ```cpp
   #define STRING1(str) L""#str
   ```

- `#str`, ek makro genişlemesiyle dize eklendikten sonra öneki ekleyin

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- Belirteçleri birleştirmek için `##` birleştirme işlecini kullanın. `##` ve `#` işlemlerinin sırası belirtilmemiş, ancak tüm derleyiciler Bu durumda `##` önce `#` işlecini değerlendirmek gibi görünüyor.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>Geçersiz \#\# uyarısı

[Belirteç yapıştırma işleci (# #)](token-pasting-operator-hash-hash.md) , tek bir geçerli ön işleme belirtecine neden olmadığında, davranış tanımsızdır. Geleneksel Önişlemci, belirteçleri birleştiremeyecek şekilde sessizce başarısız olur. Yeni Önişlemci, diğer derleyicilerin büyük bir davranışıyla eşleşecek ve bir tanılamayı yayacaktır.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Değişken bağımsız değişken makrolarda virgül

Geleneksel MSVC Önişlemci her zaman boş `__VA_ARGS__` değiştirmadan önce virgülleri kaldırır. Deneysel ön işlemci diğer popüler platformlar arası derleyicilerin davranışına daha yakından uyar. Virgülün kaldırılması için, değişen sayıda bağımsız değişken eksik olmalıdır (yalnızca boş olmamalıdır) ve bir `##` işleciyle işaretlenmelidir. Aşağıdaki örneği göz önünde bulundurun:

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor will replace the following macro with: func(1, ), which will result in a syntax error.
    FUNC(1, );
}
```

Aşağıdaki örnekte, değişen sayıda bağımsız değişken `FUNC2(1)` yapılan çağrıda, yürütülen makroda yok. `FUNC2(1, )` çağrısında değişen sayıda bağımsız değişken boş, ancak yok (bağımsız değişken listesinde virgül olduğunu fark edin).

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
   // Expands to func(1)
   FUNC2(1);

   // Expands to func(1, )
   FUNC2(1, );
}
```

Yakında bulunan C + + 2A standardında bu sorun, henüz uygulanmayan `__VA_OPT__`eklenerek giderilmiştir.

### <a name="macro-arguments-are-unpacked"></a>Makro bağımsız değişkenleri "paketten çıkarılan"

Geleneksel Önişlemci 'de, bir makro bağımsız değişkenlerinden birini başka bir bağımlı makroya ilettiğinde bağımsız değişken, yerine "paketten çıkarılan" almaz. Genellikle bu iyileştirme fark edilmemiş olur, ancak olağan dışı davranışa yol açabilir:

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conformant preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

`A()`genişletilirken geleneksel Önişlemci, `__VA_ARGS__` paketlenmiş tüm bağımsız değişkenleri TWO_STRINGS ' in ilk bağımsız değişkenine iletir ve bu da değişen sayıda `TWO_STRINGS` boş bağımsız değişkenini bırakır. Bu, `#first` sonucunun yalnızca "1" yerine "1, 2" olmasına neden olur. Daha yakından takip ediyorsanız, geleneksel ön işlemci genişletmesinin `#__VA_ARGS__` sonucuna ne olduğunu merak ediyor olabilirsiniz: değişen sayıda bağımsız değişken boşsa boş bir dize sabit değeri `""`oluşur. Ayrı bir sorun nedeniyle boş dize değişmez değeri oluşturulamadı.

### <a name="rescanning-replacement-list-for-macros"></a>Makrolar için değiştirme listesini yeniden tarama

Bir makro değiştirildikten sonra, ortaya çıkan belirteçler, değiştirilmesini gerektiren ek makro tanımlayıcıları için yeniden taranır. Bu örnekte gösterildiği gibi, yeniden taramayı gerçekleştirmek için geleneksel ön işlemci tarafından kullanılan algoritma, gerçek koda bağlı olarak aşağıdaki örnekte gösterildiği gibi uyumlu değildir:

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))
DO_THING(1, "World");

// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conformant preprocessor:
// IMPL1 ( "Hello","World");
```

Bu örnek bir bit contrived görünmesine rağmen gerçek bir dünya kodu gerçekleşmiştir. Ne olduğunu görmek için `DO_THING`ile başlayarak genişletmeyi kesebilirsiniz:

1. `DO_THING(1, "World")` `CAT(IMPL, 1) ECHO(("Hello", "World"))` genişletilir
1. `CAT(IMPL, 1)`, `IMPL1` genişleten `IMPL ## 1` genişletilir
1. Belirteçler şu durumda: `IMPL1 ECHO(("Hello", "World"))`
1. Önişlemci `IMPL1`işlev benzeri makro tanımlayıcısını bulur, ancak bundan sonra bir `(`değildir, bu nedenle işlev benzeri bir makro çağrısı kabul edilmez. 
1. Aşağıdaki belirteçlere gider ve çağrılan işlev benzeri makro `ECHO` bulur: `ECHO(("Hello", "World"))``("Hello", "World")`
1. `IMPL1` genişletme için hiçbir daha kabul edilmez, bu nedenle genişletmeleri 'in tam sonucu: `IMPL1("Hello", "World");`

Makro, başka bir yöneltme katmanını ekleyerek deneysel Önişlemci ve geleneksel ön işlemci altında aynı şekilde değiştirilebilir:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))
DO_THING_FIXED(1, "World");

// macro expands to:
// do_thing_one( "Hello", "World");
```

## <a name="incomplete-features"></a>Tamamlanmamış Özellikler

Deneysel Önişlemci genellikle tamamlanmıştır, ancak bazı Önişlemci yönergesi mantığı yine de geleneksel davranışa geri döner. Tamamlanmamış özelliklerin kısmi bir listesi aşağıda verilmiştir:

- `_Pragma` için destek
- C++ 20 özellikleri
- Engellemeyi artırma hatası: ön işlemci sabit ifadelerinde mantıksal işleçler, yeni Önişlemci 'da tam olarak uygulanmaz. Bazı `#if` yönergeleriyle, yeni Önişlemci geleneksel ön işlemci 'ye geri dönebilirler. Bu efekt yalnızca, geleneksel Önişlemci ile uyumsuz olan makrolar genişletildiğinde ve bu durum, Boost Önişlemci yuvaları oluşturulurken meydana gelebileceği fark edilir.
