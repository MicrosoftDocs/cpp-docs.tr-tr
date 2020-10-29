---
title: MSVC yeni Önişlemci genel bakış
description: MSVC Önişlemci, C/C++ standartları ile uyumluluk açısından güncelleştiriliyor.
ms.date: 09/10/2020
helpviewer_keywords:
- preprocessor, experimental
- preprocessor, new
ms.openlocfilehash: 5327a8148f78a07e222fae7fb92e6ed741d12011
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924580"
---
# <a name="msvc-new-preprocessor-overview"></a>MSVC yeni Önişlemci genel bakış

::: moniker range="msvc-140"

Visual Studio 2015, standart C++ veya C99 uyumlu olmayan geleneksel Önişlemci 'yi kullanır. Visual Studio 2019 sürüm 16,5 ' den başlayarak, C++ 20 Standard için yeni Önişlemci desteği Özellik tamamlanmıştır. Bu değişiklikler [/Zc: Önişlemci](../build/reference/zc-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Yeni Önişlemci 'nin deneysel sürümü, Visual Studio 2017 sürüm 15,8 ve sonrasında [/deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Visual Studio 2017 ve Visual Studio 2019 ' de yeni Önişlemci kullanımı hakkında daha fazla bilgi mevcuttur. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=msvc-150"

Standart uyumluluğu artırmak, uzunları onarmak ve resmi olarak tanımsız bazı davranışları değiştirmek için Microsoft C++ Önişlemci 'yi güncelleştiriyoruz. Ayrıca makro tanımlarındaki hatalarda uyarı almak için yeni Tanılamalar ekledik.

Visual Studio 2019 sürüm 16,5 ' den başlayarak, C++ 20 standardı için Önişlemci desteği Özellik tamamlanmıştır. Bu değişiklikler [/Zc: Önişlemci](../build/reference/zc-preprocessor.md) derleyici anahtarı kullanılarak kullanılabilir. Yeni Önişlemci 'nin deneysel sürümü, Visual Studio 2017 sürüm 15,8 ' den başlayarak daha önceki sürümlerde kullanılabilir. [/Deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarını kullanarak etkinleştirebilirsiniz. Varsayılan ön işlemci davranışı önceki sürümlerde olduğu gibi kalır.

## <a name="new-predefined-macro"></a>Yeni önceden tanımlanmış makro

Hangi Önişlemci 'nin derleme zamanında kullanımda olduğunu tespit edebilirsiniz. [`_MSVC_TRADITIONAL`](predefined-macros.md)Geleneksel Önişlemci 'nin kullanımda olup olmadığını söylemek için önceden tanımlanmış makronun değerini denetleyin. Bu makro, kendisini destekleyen derleyicinin, Önişlemci 'nin çağrıldığı bağımsız sürümleriyle koşulsuz olarak ayarlanır. Geleneksel Önişlemci için değeri 1 ' dir. Bu, uyumlu Önişlemci için 0 ' dır.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-new-preprocessor"></a>Yeni Önişlemci 'de davranış değişiklikleri

Yeni Önişlemci üzerindeki ilk iş, tüm makro genişleimleri standart ile uyumlu hale getirilmesi üzerine odaklanılmıştır. Bu, MSVC derleyicisini geleneksel davranışlar tarafından şu anda engellenen kitaplıklarla kullanmanıza olanak sağlar. Güncelleştirilmiş Önişlemci 'yi gerçek dünyada projeler üzerinde test ettik. Bulduğumuz daha yaygın önemli değişikliklerden bazıları aşağıda verilmiştir:

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

Standartlarla uyumlu düzeltmeler, `int myVal` uygun yönergelerin içinde bildirilmelidir `#ifdef/#endif` :

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

Bu durumda, `L` bitişik dize değişmez değerleri yine de makro genişletmesinden sonra birleştirildiğinden, ön ek gereksizdir. Geriye dönük olarak uyumlu düzeltmeler, tanımı değiştirmemize sahiptir:

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

- `L""`Ön ek eklemek için ve ' nin dize birleştirmesini kullanın `#str` . Bitişik dize değişmez değerleri, makro genişletmesinden sonra birleştirilir:

   ```cpp
   #define STRING1(str) L""#str
   ```

- Daha sonra `#str` ek makro genişletme ile dize oluşturulduktan sonra öneki ekleyin

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- `##`Belirteçleri birleştirmek için birleştirme işlecini kullanın. Ve için işlem sırası `##` `#` belirtilmemiş, ancak tüm derleyiciler `#` Bu durumda önceki işleci değerlendirse gibi görünüyor `##` .

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>Uyarı geçersiz \#\#

[Belirteç yapıştırma işleci (# #)](token-pasting-operator-hash-hash.md) , tek bir geçerli ön işleme belirteci ile sonuçlanmazsa, davranış tanımsızdır. Geleneksel Önişlemci sessizce bu belirteçleri birleştiremez. Yeni Önişlemci, diğer derleyicilerin büyük bir davranışıyla eşleşir ve bir tanılama yayar.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Değişken bağımsız değişken makrolarda virgül

Geleneksel MSVC Önişlemci her zaman boş değiştirmeler öncesinde virgülleri kaldırır `__VA_ARGS__` . Yeni Önişlemci, diğer popüler platformlar arası derleyicilerin davranışını daha yakından izler. Virgülün kaldırılması için, değişen sayıda bağımsız değişken eksik olmalıdır (yalnızca boş olmamalıdır) ve bir `##` işleçle işaretlenmelidir. Aşağıdaki örneği inceleyin:

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

Aşağıdaki örnekte, `FUNC2(1)` çağrılan makroda, değişen sayıda bağımsız değişken çağrısında yok. `FUNC2(1, )`Değişen sayıda bağımsız değişken çağrısında boş, ancak yok (bağımsız değişken listesinde virgül olduğuna dikkat edin).

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

Yakında düzenlenecek C++ 20 standardında, bu sorun eklenerek giderilmiştir `__VA_OPT__` . İçin yeni Önişlemci desteği  `__VA_OPT__` Visual Studio 2019 sürüm 16,5 ' den başlayarak kullanılabilir.

### <a name="c20-variadic-macro-extension"></a>C++ 20 variadıc Macro uzantısı

Yeni Önişlemci C++ 20 değişen ADIC Macro bağımsız değişkenini destekler:

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

Bu kod, C++ 20 standardına göre uyumlu değildir. MSVC ' de, yeni Önişlemci bu C++ 20 davranışını daha düşük dil standart modlarına ( **`/std:c++14`** ,) göre genişletir **`/std:c++17`** . Bu uzantı, diğer ana platformlar arası C++ derleyicilerinin davranışıyla eşleşir.

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

Genişletildiğinde `A()` , geleneksel Önişlemci ' de paketlenmiş tüm bağımsız değişkenleri `__VA_ARGS__` TWO_STRINGS ilk bağımsız değişkenine iletir. Bu, değişen sayıda bağımsız değişken boş olarak bırakır `TWO_STRINGS` . Bu, sonucunun `#first` yalnızca "1" yerine "1, 2" olmasına neden olur. Daha yakından takip ediyorsanız, geleneksel ön işlemci genişletmesinin sonucuna ne olduğunu merak ediyor olabilirsiniz `#__VA_ARGS__` : değişen bağımsız değişken parametresi boşsa boş bir dize sabit değeri ile sonuçlanır `""` . Ayrı bir sorun, boş dize sabit değerinin oluşturulmasını bir şekilde tutmaktadır.

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

Bu örnekte bir bit contrived görünebilir, ancak bunu gerçek dünyada kodda gördük.

Neler olduğunu görmek için genişletmeyi şu şekilde kesebilirsiniz `DO_THING` :

1. `DO_THING(1, "World")` Şunu genişletir `CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)`öğesini genişleterek `IMPL ## 1``IMPL1`
1. Artık belirteçler bu durumda: `IMPL1 ECHO(("Hello", "World"))`
1. Önişlemci, işlev benzeri makro tanımlayıcısını bulur `IMPL1` . Bir tarafından izlenmediğinden `(` , bir işlev benzeri makro çağrısı kabul edilmez.
1. Ön işlemci aşağıdaki belirteçlere gider. İşlev benzeri makroyu bulur `ECHO` : `ECHO(("Hello", "World"))` , öğesine genişleyen `("Hello", "World")`
1. `IMPL1` genişletmesi için hiçbir daha kabul edilmez, bu nedenle genişletmeleri 'in tam sonucu şu şekilde olur: `IMPL1("Hello", "World");`

Makroyu hem yeni Önişlemci hem de geleneksel Önişlemci altında aynı şekilde davranacak şekilde değiştirmek için, başka bir yöneltme katmanı ekleyin:

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

## <a name="incomplete-features-before-165"></a>16,5 öncesi eksik Özellikler

Visual Studio 2019 sürüm 16,5 ' den başlayarak yeni Önişlemci, C++ 20 için özellik tamamlanmıştır. Visual Studio 'nun önceki sürümlerinde, bazı Önişlemci yönergesi mantığı yine de geleneksel davranışa geri düşerse, yeni Önişlemci genellikle tamamlanmıştır. Aşağıda 16,5 öncesi Visual Studio sürümlerindeki eksik özelliklerin kısmi bir listesi verilmiştir:

- İçin destek `_Pragma`
- C++ 20 özellikleri
- Hata engellemeyi arttırma: Önişlemci sabit ifadelerindeki mantıksal işleçler, 16,5 sürümünden önceki yeni Önişlemci içinde tam olarak uygulanmaz. Bazı `#if` yönergelerden yeni Önişlemci, geleneksel ön işlemci 'ye geri dönebilir. Bu efekt yalnızca geleneksel Önişlemci ile uyumsuz makrolar genişletilmiş olduğunda görülür. Boost Önişlemci yuvaları oluşturulurken bu durum oluşabilir.

::: moniker-end
