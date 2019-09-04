---
title: '/Deneysel: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)'
description: 'Standart bir uyumlu Önişlemci için deneysel derleyici desteğini etkinleştirmek üzere/deneysel: Önişlemci derleyici seçeneğini kullanın.'
ms.date: 09/03/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 3055cfa2a32d1d668dbe0c51b5542415b5bb0af4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294423"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/Deneysel: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)

Bu seçenek, C99 Önişlemci özellikleri de dahil olmak üzere C++ 11 standartlarına uyan deneysel, belirteç tabanlı bir Önişlemci sağlar.

## <a name="syntax"></a>Sözdizimi

> **/deneysel: Önişlemci** [ **-** ]

## <a name="remarks"></a>Açıklamalar

Deneysel uyumlu Önişlemci 'yi etkinleştirmek için **/deneysel: Önişlemci** derleyici seçeneğini kullanın. Geleneksel Önişlemci 'yi açıkça belirtmek için **/deneysel: Önişlemci-** seçeneğini kullanabilirsiniz.

**/Deneysel: Önişlemci** seçeneği, Visual Studio 2017 sürüm 15,8 ' den başlayarak kullanılabilir.

Hangi Önişlemci 'nin derleme zamanında kullanımda olduğunu tespit edebilirsiniz. Geleneksel Önişlemci 'nin kullanımda olup olmadığını söylemek için önceden tanımlanmış [ \_MSVC\_](../../preprocessor/predefined-macros.md) Macro değerini denetleyin. Bu makro, kendisini destekleyen derleyicinin, Önişlemci 'nin çağrıldığı bağımsız sürümleriyle koşulsuz olarak ayarlanır. Geleneksel Önişlemci için değeri 1 ' dir. Bu, uyumsuz deneysel Önişlemci için 0 ' dır:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

### <a name="behavior-changes-in-the-experimental-preprocessor"></a>Deneysel Önişlemci 'daki davranış değişiklikleri

Önişlemci uyumluluk modu etkinleştirildiğinde daha yaygın olarak karşılaşılan bazı değişiklikler aşağıda verilmiştir:

#### <a name="macro-comments"></a>Makro açıklamaları

Geleneksel Önişlemci Önişlemci belirteçleri yerine karakter arabellekleri kullanır. Bu, bu Önişlemci yorumu eli gibi bazı Olağandışı davranışa izin verir ve bu, uyumlu Önişlemci altında çalışmaz:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
// To make standards compliant, wrap the following line with the appropriate #if/#endif
DISAPPEARING_TYPE myVal;
```

#### <a name="string-prefixes-lval"></a>Dize önekleri (L # Val)

Geleneksel Önişlemci dize önekini yanlış bir şekilde bir dize öneki olarak birleştirir [(#)](../../preprocessor/stringizing-operator-hash.md):

```cpp
#define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

Burada, bitişik dize değişmez değerleri makro genişletmesinden sonra birleştirildiğinden, önekgereksizdir.`L` Geriye dönük olarak uyumlu düzeltmeler, tanımın şu şekilde değiştirilmesini sağlar:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Bu sorun, bağımsız değişkeni geniş bir dize sabit değeri olarak ' stringize ' olan kolay makrolar içinde de bulunur:

```cpp
// The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str

// Potential fixes:
// Use string concatenation of L"" and #str to add prefix
// This works because adjacent string literals are combined after macro expansion
#define STRING1(str) L""#str

// Add the prefix after #str is stringized with additional macro expansion
#define WIDE(str) L##str
#define STRING2(str) WIDE(#str)

// Use concatenation operator ## to combine the tokens.
// The order of operations for ## and # is unspecified, although all compilers
// checked perform the # operator before ## in this case.
#define STRING3(str) L## #str
```

#### <a name="warning-on-invalid"></a>Uyarı geçersiz ##

[Belirteç yapıştırma işleci (# #)](../../preprocessor/token-pasting-operator-hash-hash.md) tek, geçerli bir ön işleme belirteciyle sonuçlanmazsa, davranış tanımsızdır. Geleneksel Önişlemci sessizce bu belirteçleri birleştiremez. Yeni Önişlemci, diğer derleyicilerin büyük bir davranışıyla eşleşir ve bir tanılama yayar.

```cpp
// The ## is unnecessary and doesn't result in a single preprocessing token.
#define ADD_STD(x) std::##x

// Declare a std::string
ADD_STD(string) s;
```

#### <a name="comma-elision-in-variadic-macros"></a>Değişken bağımsız değişken makrolarda virgül

Aşağıdaki örnek göz önünde bulundurun:

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // The following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the following macro with:
    // func(1, );
    // which results in a syntax error.
    FUNC(1, );
}
```

Tüm ana derleyiciler, bu sorunu gidermenize yardımcı olan bir ön işlemci uzantısına sahiptir. Geleneksel MSVC Önişlemci her zaman boş `__VA_ARGS__` değiştirmeler öncesinde virgülleri kaldırır. Güncelleştirilmiş Önişlemci, diğer popüler platformlar arası derleyicilerin davranışını daha yakından izler. Virgülün kaldırılması için, değişen sayıda bağımsız değişken eksik, yalnızca boş olmalıdır ve bir `##` işleçle işaretlenmelidir:

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
    // The variadic argument is missing in the macro being evoked
    // The comma is removed and replaced with:
    // func(1)
    FUNC2(1);

    // The variadic argument is empty, but not missing. (Notice the
    // comma in the argument list.) The comma isn't removed
    // when the macro is replaced:
    // func(1, )
    FUNC2(1, );
}
```

Yakında çıkacak olan C + + 2A standardında, bu sorun henüz uygulanmayan, eklenerek `__VA_OPT__`giderilmiştir.

#### <a name="macro-arguments-are-unpacked"></a>Makro bağımsız değişkenleri ' paketten çıkarılan '

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

Genişletildiğinde `A()`, geleneksel Önişlemci ' de paketlenmiş tüm bağımsız değişkenleri ' `__VA_ARGS__` ın `TWO_STRINGS`ilk bağımsız değişkenine iletir. Değişen sayıda bağımsız `TWO_STRINGS` değişken boş ve bu, `#first` sonucunun yalnızca `"1"`yerine bırakılmasına `"1, 2"` neden olur. Geleneksel Önişlemci genişletmesinin sonucuna `#__VA_ARGS__` ne olduğunu merak ediyor olabilirsiniz. variadıc parametresi boşsa, boş bir "" dize sabit değeri ile sonuçlanmalıdır. Ayrı bir sorun nedeniyle boş dize değişmez değer belirteci üretilmedi.

#### <a name="rescanning-replacement-list-for-macros"></a>Makrolar için değiştirme listesini yeniden tarama

Bir makro değiştirildikten sonra, değiştirilecek ek makro tanımlayıcıları için ortaya çıkan belirteçler yeniden taranıp. Geleneksel Önişlemci tarafından kullanılan yeniden tarama algoritması, bu örnekte gösterildiği gibi gerçek koda bağlı olarak uyumlu değildir:

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

Bu örnekte neler olduğunu görmek için, aşağıdaki ile `DO_THING`başlayarak genişletmeyi ayırdık:

`DO_THING(1, "World")` ->
`CAT(IMPL, 1) ECHO(("Hello", "World"))`

İkincisi, kedı genişletilir:

`CAT(IMPL, 1)` -> `IMPL ## 1` -> `IMPL1`

Belirteçleri bu duruma geçirir:

`IMPL1 ECHO(("Hello", "World"))`

Önişlemci işlev benzeri makro tanımlayıcısını `IMPL1`bulur, ancak bundan sonra bir "(" değildir, bu nedenle işlev benzeri bir makro çağrısı kabul edilmez. Aşağıdaki belirteçlere gider ve çağrılan işlev benzeri makroyu `ECHO` bulur:

`ECHO(("Hello", "World"))` -> `("Hello", "World")`

`IMPL1`genişletmesi için hiçbir daha kabul edilmez, bu nedenle genişletmeleri 'in tam sonucu şu şekilde olur:

`IMPL1("Hello", "World");`

Makro, deneysel Önişlemci ve geleneksel Önişlemci altında aynı şekilde davranır. Bu çözüm başka bir yöneltme katmanı eklemektir:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))

DO_THING_FIXED(1, "World");
// macro expanded to:
// do_thing_one( "Hello", "World");
```

### <a name="conformance-mode-conformance"></a>Uygunluk modu uyumluluğu

Deneysel ön işlemci henüz tamamlanmamış ve bazı Önişlemci yönergesi mantığı yine de geleneksel davranışa geri döner. Tamamlanmamış özelliklerin kısmi bir listesi aşağıda verilmiştir:

- İçin destek`_Pragma`
- C++ 20 özellikleri
- Ek tanılama geliştirmeleri
- /E ve/P altındaki çıktıyı denetlemek için anahtarlar
- Engelleme hatasını artırma: Önişlemci sabit ifadelerindeki mantıksal işleçler, yeni Önişlemci 'de tam olarak uygulanmaz. Bazı `#if` yönergelerden yeni Önişlemci, geleneksel ön işlemci 'ye geri dönebilir. Bu efekt yalnızca, geleneksel Önişlemci ile uyumsuz olan makrolar genişletildiğinde ve bu durum, Boost Önişlemci yuvaları oluşturulurken meydana gelebileceği fark edilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++/** komut > **satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/deneysel: Önişlemci** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
