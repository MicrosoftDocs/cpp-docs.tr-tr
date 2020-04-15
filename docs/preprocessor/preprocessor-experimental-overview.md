---
title: MSVC deneysel önişlemciye genel bakış
description: MSVC önişlemcisi C/C++ standartlarına uygunluk için güncellenmektedir.
ms.date: 02/09/2020
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 00c34ef75270e505d3781cf7eedf4d8aba95ee6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337477"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC deneysel önişlemciye genel bakış

::: moniker range="vs-2015"

Visual Studio 2015, Standart C++'a uymayan geleneksel önişlemciyi kullanır. Visual Studio 2017 ve Visual Studio 2019'da [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak deneysel bir önişlemci mevcuttur. Visual Studio 2017 ve Visual Studio 2019'da yeni ön işlemcikullanımı hakkında daha fazla bilgi edinilebilir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=vs-2017"

Standartlara uygunluğu iyileştirmek, uzun süredir devam eden hataları düzeltmek ve resmi olarak tanımlanmamış bazı davranışları değiştirmek için Microsoft C++ ön işlemcisini güncelliyoruz. Makro tanımlarında hatalar konusunda uyarmak için yeni tanılamalar da ekledik.

Bu değişiklikler Visual Studio 2017 veya Visual Studio 2019'daki [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Varsayılan önişlemci davranışı önceki sürümlerde olduğu gibi kalır.

Visual Studio 2019 sürüm 16.5'ten başlayarak, C++20 standardı için deneysel önişlemci desteği özellik tamlamasıdır.

## <a name="new-predefined-macro"></a>Yeni önceden tanımlanmış makro

Derleme zamanında hangi ön işlemcinin kullanıldığını algılayabilirsiniz. Geleneksel önişlemcinin kullanımda olup olmadığını söylemek için önceden tanımlanmış [ \_msvc\_TRADITIONAL](predefined-macros.md) makrounun değerini kontrol edin. Bu makro, önişlemcinin çağrıldığı bağımsız olarak, onu destekleyen derleyicinin sürümleri tarafından koşulsuz olarak ayarlanır. Değeri geleneksel önişlemci için 1'dir. Uygun önişlemci için 0.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>Deneysel önişlemcideki davranış değişiklikleri

Deneysel önişlemci üzerinde yapılan ilk çalışma, tüm makro genişletmelerinin standarda uygun hale getirilmesine odaklanmıştır. MsVC derleyicisini, şu anda geleneksel davranışlar tarafından engellenen kitaplıklarla kullanmanıza olanak tanır. Güncellenmiş önişlemciyi gerçek dünya projelerinde test ettik. Bulduğumuz daha yaygın kırılma değişikliklerinden bazıları şunlardır:

### <a name="macro-comments"></a>Makro yorumları

Geleneksel önişlemci, önişlemci belirteçleri yerine karakter arabelleklerini temel adatır. Uygun önişlemci altında çalışmayan aşağıdaki önişlemci yorumu hilesi gibi olağandışı davranışlara izin verir:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

Standartlara uygun düzeltme, uygun `int myVal` `#ifdef/#endif` direktifler içinde beyan etmektir:

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L#val

Geleneksel önişlemci, [stringizing işleci (#) işlecinin](stringizing-operator-hash.md) sonucuna bir dize önekini yanlış birleştirir:

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

Bu durumda, `L` önek gereksizdir, çünkü bitişik dize literalleri makro genişletmeden sonra yine de birleştirilir. Geriye uyumlu düzeltme tanımı değiştirmektir:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Aynı sorun, bağımsız değişkeni geniş bir dize edebi olarak "dizeleyen" kolaylık makrolarında da bulunur:

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

Sorunu çeşitli şekillerde çözebilirsiniz:

- Dize concatenation `L""` `#str` ve önek eklemek için kullanın. Bitişik dize literals makro genişletme sonra birleştirilir:

   ```cpp
   #define STRING1(str) L""#str
   ```

- Ek makro genişletme `#str` ile dize edildikten sonra önek ekleme

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- Belirteçleri birleştirmek `##` için birleştirme işleci kullanın. Tüm derleyiciler `##` `#` bu durumda daha önce `#` `##` işleci değerlendirmek gibi görünse de, için ve belirtilmemiş işlemler sırası.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>Geçersiz uyarı\#\#

[Belirteç yapıştırma işleci (##)](token-pasting-operator-hash-hash.md) tek bir geçerli ön işleme belirteci yle sonuçlanmadığında, davranış tanımsız dır. Geleneksel önişlemci sessizce belirteçleri birleştirmek için başarısız olur. Yeni önişlemci, diğer derleyicilerin çoğu yla eşleşir ve tanılama yayır.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Variadik makrolarda virgül elision

Geleneksel MSVC önişlemcisi boş `__VA_ARGS__` değiştirmelerden önce her zaman virgülleri kaldırır. Deneysel önişlemci diğer popüler çapraz platform derleyicilerinin davranışını daha yakından izler. Virgül kaldırılabilir için, variadic bağımsız değişken (sadece boş değil) eksik olması `##` gerekir ve bir işleç ile işaretlenmiş olmalıdır. Aşağıdaki örneği inceleyin:

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

Aşağıdaki örnekte, `FUNC2(1)` çağrıda variadik bağımsız değişken çağrılan makroda eksiktir. Variadic `FUNC2(1, )` bağımsız değişkene yapılan çağrıda boş, ancak eksik değil (bağımsız değişken listesindeki virgüle dikkat edin).

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

Yaklaşan C++20 standardında, bu sorun eklenerek `__VA_OPT__`ele alınmıştır. Visual Studio 2019 sürüm 16.5'ten başlayarak deneysel önişlemci desteği `__VA_OPT__` mevcuttur.

### <a name="c20-variadic-macro-extension"></a>C++20 variadik makro uzantısı

Deney önişlemcisi C++20 variadik makro bağımsız değişken iyetini destekler:

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

Bu kod C++20 standardından önce uygun değildir. MSVC'de, deney öncesi işlemci bu C++20 davranışını daha**`/std:c++14`** **`/std:c++17`** düşük dil standart modlarına (, ) genişletir. Bu uzantı, diğer büyük çapraz platform C++ derleyicilerinin davranışıyla eşleşir.

### <a name="macro-arguments-are-unpacked"></a>Makro bağımsız değişkenleri "ambalajsız"

Geleneksel önişlemcide, bir makro bağımsız değişkenlerinden birini başka bir bağımlı makroya ilediyorsa, bağımsız değişken eklendiğinde "açılmaz". Genellikle bu optimizasyon fark edilmeden gider, ancak olağandışı davranışa yol açabilir:

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

Genişletirken, `A()`geleneksel önişlemci, TWO_STRINGS ilk bağımsız `__VA_ARGS__` değişkenine paketlenmiş tüm bağımsız değişkenleri ileterek `TWO_STRINGS` boş değişkeni bırakır. Bu da sonucun `#first` sadece "1" yerine "1, 2" olması neden olur. Eğer yakından takip ediyorsanız, o zaman geleneksel önişlemci genişleme `#__VA_ARGS__` sonucu ne oldu merak ediyor olabilirsiniz: variadik parametre boş ise `""`boş bir dize literal neden olmalıdır. Ayrı bir sorun, boş dize gerçek belirteci oluşturulmasını engelledi.

### <a name="rescanning-replacement-list-for-macros"></a>Makrolar için değiştirme listesini yeniden tarama

Makro değiştirildikten sonra, ortaya çıkan belirteçler değiştirilecek ek makro tanımlayıcıları için yeniden taranmaktadır. Rescan yapmak için geleneksel önişlemci tarafından kullanılan algoritma, gerçek koda dayalı bu örnekte gösterildiği gibi, uyumlu değildir:

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

Bu örnek biraz yapışık gibi görünse de, bunu gerçek dünya kodunda gördük. Neler olduğunu görmek için, aşağıdakilerden başlayarak genişlemeyi `DO_THING`bozabiliriz:

1. `DO_THING(1, "World")`genişletir`CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)`genişletir `IMPL ## 1`, hangi genişletir`IMPL1`
1. Şimdi belirteçleri bu durumda:`IMPL1 ECHO(("Hello", "World"))`
1. Önişlemci işlev benzeri makro tanımlayıcısını `IMPL1`bulur. Bir tarafından takip edilmediä `(`i için, iþlev gibi makro çağırması olarak kabul edilmez.
1. Önişlemci aşağıdaki belirteçlere geçer. Bu işlev gibi makro `ECHO` çağrılabilir `ECHO(("Hello", "World"))`bulur: , hangi genişletir`("Hello", "World")`
1. `IMPL1`genişleme için tekrar kabul asla, bu nedenle genişlemelerin tam sonucu:`IMPL1("Hello", "World");`

Makroyu hem deneysel önişlemci hem de geleneksel önişlemci altında aynı şekilde olacak şekilde değiştirmek için başka bir yönlendirme katmanı ekleyin:

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

## <a name="incomplete-features"></a>Eksik özellikler

Visual Studio 2019 sürüm 16.5'ten başlayarak, deneysel ön işlemci C++20 için özellik tamlamasıdır. Visual Studio'nun önceki sürümlerinde, bazı önişlemci yönergeleri mantığı hala geleneksel davranışa geri dönse de, deneysel önişlemci çoğunlukla tamamlanmıştır. Visual Studio sürümlerindeki eksik özelliklerin kısmi bir listesi 16.5'tir:

- Destek için`_Pragma`
- C++20 özellikleri
- Engelleme hatasını öne çıkarma: Önişlemci sabit ifadelerindeki mantıksal işleçler sürüm 16.5'ten önce yeni önişlemcide tam olarak uygulanmaz. Bazı `#if` yönergelerde, yeni önişlemci geleneksel önişlemciye geri dönebilir. Bu etki yalnızca geleneksel önişlemciyle uyumsuz makrolar genişletildiğinde fark edilir. Boost önişlemci yuvalarını kurarken gerçekleşebilir.

::: moniker-end
