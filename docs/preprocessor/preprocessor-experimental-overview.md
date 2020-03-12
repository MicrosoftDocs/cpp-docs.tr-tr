---
title: MSVC deneysel Önişlemci genel bakış
description: MSVC Önişlemci, C/C++ standartları ile uyumluluk açısından güncelleştiriliyor.
ms.date: 02/09/2020
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: eb861b18a8d42c73429f6d00a3f47b35c9b198ca
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2020
ms.locfileid: "79090550"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC deneysel Önişlemci genel bakış

::: moniker range="vs-2015"

Visual Studio 2015, standart C++ile uyumlu olmayan geleneksel Önişlemci 'yi kullanır. Visual Studio 2017 ve Visual Studio 2019 ' de [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak deneysel bir Önişlemci mevcuttur. Visual Studio 2017 ve Visual Studio 2019 ' de yeni Önişlemci kullanımı hakkında daha fazla bilgi mevcuttur. Görmek için, bu sürümlerden birini seçmek üzere belge sürümü seçicisini kullanın.

::: moniker-end

::: moniker range=">=vs-2017"

Standartlara uygunluğu geliştirmek, uzunları onarmak ve resmi olarak tanımsız bazı davranışları değiştirmek için Microsoft C++ Önişlemci 'yi güncelleştiriyoruz. Ayrıca makro tanımlarındaki hatalarda uyarı almak için yeni Tanılamalar ekledik.

Bu değişiklikler, Visual Studio 2017 veya Visual Studio 2019 ' de [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Varsayılan ön işlemci davranışı önceki sürümlerde olduğu gibi kalır.

Visual Studio 2019 sürüm 16,5 ' den başlayarak, C++ 20 standardı için deneysel ön işlemci desteği Özellik tamamlanmıştır.

## <a name="new-predefined-macro"></a>Yeni önceden tanımlanmış makro

Hangi Önişlemci 'nin derleme zamanında kullanımda olduğunu tespit edebilirsiniz. Geleneksel Önişlemci 'nin kullanımda olup olmadığını söylemek için [MSVC\_\_](predefined-macros.md) önceden tanımlanmış makronun değerini denetleyin. Bu makro, kendisini destekleyen derleyicinin, Önişlemci 'nin çağrıldığı bağımsız sürümleriyle koşulsuz olarak ayarlanır. Geleneksel Önişlemci için değeri 1 ' dir. Bu, uyumlu Önişlemci için 0 ' dır.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>Deneysel Önişlemci 'daki davranış değişiklikleri

Deneysel ön işlemci üzerindeki ilk iş, tüm makro genişleimleri standart ile uyumlu hale getirilmesi üzerine odaklanmıştır. Bu, MSVC derleyicisini geleneksel davranışlar tarafından şu anda engellenen kitaplıklarla kullanmanıza olanak sağlar. Güncelleştirilmiş Önişlemci 'yi gerçek dünyada projeler üzerinde test ettik. Bulduğumuz daha yaygın önemli değişikliklerden bazıları aşağıda verilmiştir:

### <a name="macro-comments"></a>Makro açıklamaları

Geleneksel Önişlemci, Önişlemci belirteçleri yerine karakter arabelleklerine dayalıdır. Aşağıdaki önişlemci yorumu eli gibi olağan dışı davranışlara izin verir ve bu, uyumlu Önişlemci altında çalışmaz:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

Standartlara uyan düzeltmeler, `int myVal` uygun `#ifdef/#endif` yönergelerinin içinde bildirilmelidir:

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

Bu durumda, bitişik dize değişmez değerleri de makro genişletmesinden sonra birleştirildiğinden `L` ön eki gereksizdir. Geriye dönük olarak uyumlu düzeltmeler, tanımı değiştirmemize sahiptir:

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

- Önek eklemek için `L""` ve `#str` dize birleştirmesini kullanın. Bitişik dize değişmez değerleri, makro genişletmesinden sonra birleştirilir:

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

[Belirteç yapıştırma işleci (# #)](token-pasting-operator-hash-hash.md) , tek bir geçerli ön işleme belirteci ile sonuçlanmazsa, davranış tanımsızdır. Geleneksel Önişlemci sessizce bu belirteçleri birleştiremez. Yeni Önişlemci, diğer derleyicilerin büyük bir davranışıyla eşleşir ve bir tanılama yayar.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Değişken bağımsız değişken makrolarda virgül

Geleneksel MSVC Önişlemci her zaman boş `__VA_ARGS__` değiştirmadan önce virgülleri kaldırır. Deneysel ön işlemci diğer popüler platformlar arası derleyicilerin davranışına daha yakından uyar. Virgülün kaldırılması için, değişen sayıda bağımsız değişken eksik olmalıdır (yalnızca boş olmamalıdır) ve bir `##` işleciyle işaretlenmelidir. Aşağıdaki örnek göz önünde bulundurun:

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the
    // following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the
    // following macro with: func(1, ), which
    // results in a syntax error.
    FUNC(1, );
}
```

Aşağıdaki örnekte, çağrılan makroda değişen sayıda bağımsız değişkeni `FUNC2(1)` çağrısı yok. `FUNC2(1, )` çağrısında değişen sayıda bağımsız değişken boş, ancak yok (bağımsız değişken listesinde virgül olduğunu fark edin).

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

Yakında düzenlenecek C++ 20 standardında, bu sorun `__VA_OPT__`eklenerek giderilmiştir. `__VA_OPT__` için deneysel ön işlemci desteği Visual Studio 2019 sürüm 16,5 ' den başlayarak kullanılabilir.

### <a name="c20-variadic-macro-extension"></a>C++ 20 variadıc Macro uzantısı

Deneysel Önişlemci C++ 20 değişen ADIC Macro bağımsız değişkenini destekler:

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

Bu kod, C++ 20 standardına göre uyumlu değildir. MSVC ' de deneysel Önişlemci, bu C++ 20 davranışını daha düşük dil standart modlarına ( **`/std:c++14`** , **`/std:c++17`** ) genişletir. Bu uzantı, diğer ana platformlar arası C++ derleyicilerin davranışıyla eşleşir.

### <a name="macro-arguments-are-unpacked"></a>Makro bağımsız değişkenleri "paketten çıkarılan"

Geleneksel Önişlemci 'de, bir makro bağımsız değişkenlerinden birini başka bir bağımlı makroya ilettiğinde, bu, eklendiği zaman değişkeni "paketten çıkarılan" almaz. Genellikle bu iyileştirme fark edilmemiş olur, ancak olağan dışı davranışa yol açabilir:

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conforming preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

`A()`genişletilirken geleneksel Önişlemci, `__VA_ARGS__` paketlenmiş tüm bağımsız değişkenleri TWO_STRINGS ilk bağımsız değişkenine iletir ve bu, değişen sayıda `TWO_STRINGS` boş olan bağımsız değişkenini bırakır. Bu, `#first` sonucunun yalnızca "1" yerine "1, 2" olmasına neden olur. Daha yakından takip ediyorsanız, geleneksel ön işlemci genişletmesinin `#__VA_ARGS__` sonucuna ne olduğunu merak ediyor olabilirsiniz: değişen sayıda bağımsız değişken boşsa boş bir dize sabit değeri `""`oluşur. Ayrı bir sorun, boş dize sabit değerinin oluşturulmasını bir şekilde tutmaktadır.

### <a name="rescanning-replacement-list-for-macros"></a>Makrolar için değiştirme listesini yeniden tarama

Bir makro değiştirildikten sonra, değiştirilecek ek makro tanımlayıcıları için ortaya çıkan belirteçler yeniden taranıp. Bu örnekte gösterildiği gibi, yeniden taramayı gerçekleştirmek için geleneksel ön işlemci tarafından kullanılan algoritma, gerçek koda bağlı olarak uygun değildir:

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
// Conforming preprocessor:
// IMPL1 ( "Hello","World");
```

Bu örnekte bir bit contrived görünebilir, ancak bunu gerçek dünya kodunda gördük. Neler olduğunu görmek için, `DO_THING`ile başlayarak genişletmeyi kesebilirsiniz:

1. `DO_THING(1, "World")` `CAT(IMPL, 1) ECHO(("Hello", "World"))` genişletilir
1. `CAT(IMPL, 1)`, `IMPL ## 1`genişleterek `IMPL1`
1. Belirteçler şu durumda: `IMPL1 ECHO(("Hello", "World"))`
1. Önişlemci `IMPL1`işlev benzeri makro tanımlayıcısını bulur. Bir `(`izlenmediğinden, bir işlev benzeri makro çağrısı kabul edilmez.
1. Ön işlemci aşağıdaki belirteçlere gider. Çağrılan `ECHO` işlev benzeri makroyu bulur: `ECHO(("Hello", "World"))``("Hello", "World")` genişleyen
1. `IMPL1` genişletme için hiçbir daha kabul edilmez, bu nedenle genişletmeleri 'in tam sonucu: `IMPL1("Hello", "World");`

Makroyu deneysel Önişlemci ve geleneksel Önişlemci altında aynı şekilde davranacak şekilde değiştirmek için, başka bir yöneltme katmanı ekleyin:

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

Visual Studio 2019 sürüm 16,5 ' den başlayarak deneysel Önişlemci, C++ 20 için özellik tamamlanmıştır. Visual Studio 'nun önceki sürümlerinde deneysel ön işlemci genellikle tamamlanmıştır, ancak bazı Önişlemci yönergesi mantığı yine de geleneksel davranışa geri döner. Aşağıda 16,5 öncesi Visual Studio sürümlerindeki eksik özelliklerin kısmi bir listesi verilmiştir:

- `_Pragma` desteği
- C++ 20 özellikleri
- Hata engellemeyi arttırma: Önişlemci sabit ifadelerindeki mantıksal işleçler, 16,5 sürümünden önceki yeni Önişlemci içinde tam olarak uygulanmaz. Bazı `#if` yönergeleriyle, yeni Önişlemci geleneksel ön işlemci 'ye geri dönebilirler. Bu efekt yalnızca geleneksel Önişlemci ile uyumsuz makrolar genişletilmiş olduğunda görülür. Boost Önişlemci yuvaları oluşturulurken bu durum oluşabilir.

::: moniker-end
