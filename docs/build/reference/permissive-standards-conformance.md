---
title: /permissive- (Standartlara uyumluluk)
description: Microsoft C++ /izin- (Standartlara uygunluk) derleyici seçeneğine işbaşvuru rehberi.
ms.date: 04/14/2020
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 695f84e64f07128ac7744dc99e736f2a71ab3e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337409"
---
# <a name="permissive--standards-conformance"></a>/permissive- (Standartlara uyumluluk)

Derleyiciye standartlara uygunluk modunu belirtin. Kodunuzdaki uyumluluk sorunlarını belirlemenize ve düzeltmenize yardımcı olmak ve kodu daha doğru ve daha taşınabilir hale getirmek için bu seçeneği kullanın.

## <a name="syntax"></a>Sözdizimi

> **/izin verilen-**

## <a name="remarks"></a>Açıklamalar

Bu seçenek Visual Studio 2017 ve sonraki yıllarda desteklenir.

Standartlara uygun derleyici davranışını belirtmek için **/izin veren** derleyici seçeneğini kullanabilirsiniz. Bu seçenek izin verici davranışları devre dışı kayırır ve sıkı uyumluluk için [/Zc](zc-conformance.md) derleyici seçeneklerini ayarlar. IDE'de bu seçenek, IntelliSense altyapısının uyumsuz kodun altını çizmesini de sağlar.

Varsayılan olarak, **/izin-** seçeneği Visual Studio 2017 sürüm 15.5 ve sonraki sürümleri tarafından oluşturulan yeni projelerde ayarlanır. Önceki sürümlerde varsayılan olarak ayarlanmaz. Seçenek ayarlandığında, derleyici, c++11 öncesi koddaki bazı yaygın hatalar da dahil olmak üzere, standart olmayan dil yapıları kodunuzda algılandığında tanılama hataları veya uyarılar oluşturur.

**/izin-** seçeneği, Windows Fall Creators SDK'dan (10.0.16299.0) başlayan Yazılım Geliştirme Kiti (SDK) veya Windows Sürücü Kiti (WDK) gibi en son Windows Kit'lerinin hemen hemen tüm üstbilgi dosyalarıyla uyumludur. SDK'nın eski sürümleri, çeşitli kaynak kodu uygunluk nedenleriyle **/izin altında** derlenebilir. Derleyici ve SDK'lar farklı sürüm zaman çizelgelerinde iletir, bu nedenle kalan bazı sorunlar vardır. Belirli üstbilgi dosyası sorunları için aşağıdaki [Windows üstbilgi sorunlarına](#windows-header-issues) bakın.

**/izin verme seçeneği** [/ Zc:referenceBinding](zc-referencebinding-enforce-reference-binding-rules.md), [/Zc:strictStrings](zc-strictstrings-disable-string-literal-type-conversion.md)ve [/Zc:rvalueCast](zc-rvaluecast-enforce-type-conversion-rules.md) seçeneklerini uygun davranışa ayarlar. Bu seçenekler varsayılan olarak uygun olmayan davranışlara bağlıdır. Bu davranışı geçersiz kılmak için komut satırına **/izin verdikten** sonra belirli **/Zc** seçeneklerini geçirebilirsiniz.

Visual Studio 2017 sürüm 15.3'te başlayan derleyici sürümlerinde **/izin li** seçenek [/Zc:tersiyer](zc-ternary.md) seçeneğini belirler. Derleyici ayrıca iki aşamalı ad araması için daha fazla gereksinimi de uygular. **/izin-** seçeneği ayarlandığında, derleyici işlevi ve sınıf şablontanımlarını ayrıştırır ve şablonlarda kullanılan bağımlı ve bağımlı olmayan adları tanımlar. Bu sürümde, yalnızca ad bağımlılık çözümlemesi gerçekleştirilir.

Standardın uygulamaya bıraktığı ortama özgü uzantılar ve dil alanları **/izin veren-**. Örneğin, Microsoft'a `__declspec`özgü , çağrı kuralı ve yapılandırılmış özel durum işleme anahtar kelimeleri ve derleyiciye özgü pragma yönergeleri veya öznitelikleri derleyici tarafından **/izin modunda** işaretlenmez.

**/izin verme** seçeneği, geçerli derleyici sürümündeki uygunluk desteğini hangi dil yapılarının uygun olmadığını belirlemek için kullanır. Seçenek, kodunuzun C++ standardının belirli bir sürümüne uygun olup olmadığını belirlemez. En son taslak standart için uygulanan tüm derleyici desteğini etkinleştirmek için [/std:latest](std-specify-language-standard-version.md) seçeneğini kullanın. Derleyici desteğini şu anda uygulanan C++17 standardıyla sınırlamak için [/std:c++17](std-specify-language-standard-version.md) seçeneğini kullanın. Derleyici desteğini C++14 standardıyla daha yakından eşleştirmesini kısıtlamak için varsayılan olan [/std:c++14](std-specify-language-standard-version.md) seçeneğini kullanın.

Visual Studio 2017'nin tüm sürümlerinde Tüm C++11, C++14 veya C++17 standartlarına uygun kodLAR MSVC derleyicisi tarafından desteklenmez. Visual Studio sürümüne bağlı olarak, **/izin verme** seçeneği iki aşamalı ad aramasının bazı yönleriyle ilgili sorunları algılayamaz, geçici olmayan bir const başvuruyu bağlamayabilir, kopya nın doğrudan init olarak ele alınarak, başlangıçta birden çok kullanıcı tarafından tanımlanmış dönüşüme veya mantıksal işleçler için alternatif belirteçlere ve diğer desteklenmeyen uygunluk alanlarına izin verebilir. Visual C++'daki uyumluluk sorunları hakkında daha fazla bilgi için standart [olmayan davranış](../../cpp/nonstandard-behavior.md)konusuna bakın. **/izin verici-**, Visual Studio'yu en son sürüme güncellemek için en iyi şekilde öğrenin.

### <a name="how-to-fix-your-code"></a>Kodunuzu düzeltme

Aşağıda, **/izin verilen/** kullandığınızda uygun olmayan olarak algılanan bazı kod örnekleri ve sorunları gidermek için önerilen yollar verilmiştir.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Yerel kodda varsayılan identifier olarak kullanma

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Bağımlı tabandaki üyeleri arama

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>Üye beyannamelerinde nitelikli adların kullanılması

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Üye başlatılmasında birden fazla sendika üyesini başlatma

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>Gizli arkadaş adı arama kuralları

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(p); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>Dizi sınırlarında kapsamlı enums kullanma

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Yerel koddaki her biri için kullanın

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>ATL Özniteliklerinin Kullanımı

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be
// used to automatically obtain a *.idl file for the interfaces with
// annotation. Second, add a midl step to your build system to make
// sure that the C++ interface definitions are outputted.
// Last, adjust your existing code to use ATL directly as shown in
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>Belirsiz koşullu işleç bağımsız değişkenleri

Derleyicinin Visual Studio 2017 sürüm 15.3'ten önceki sürümlerinde, derleyici Standart tarafından belirsiz `?:` kabul edilen koşullu işleç (veya üçüncül işleci) bağımsız değişkenlerini kabul etti. **/izin modunda,** derleyici şimdi önceki sürümlerde tanılama olmadan derlenen durumlarda bir veya daha fazla tanılama sorunları.

Bu değişiklikten kaynaklanabilir yaygın hatalar şunlardır:

- hata C2593: 'operatör ?' belirsizdir

- hata C2679: ikili '?': hiçbir işleç hangi tip 'B' (ya da kabul edilebilir bir dönüşüm var) bir sağ operand alır bulunamadı

- hata C2678: ikili '?': hiçbir işleç 'A' tipi bir sol operand alır bulunamadı (ya da kabul edilebilir bir dönüştürme yoktur)

- hata C2446: ':': 'B'den 'A'ya dönüştürme yok

Bu soruna neden olabilecek tipik bir kod deseni, bazı C sınıfının hem başka bir T türünden açık olmayan bir oluşturucu hem de T türüne açık olmayan bir dönüştürme işleci sağlamasıdır. Bu durumda, hem ikinci bağımsız değişkenin üçüncü bağımsız değişken türüne dönüştürülmesi hem de üçüncü bağımsız değişkenin ikinci bağımsız değişken türüne dönüştürülmesi geçerli dönüşümlerdir. Her ikisi de geçerli olduğundan, standarda göre belirsiz.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

T, null-sonlandırılan dize türlerinden birini (örneğin, `const char *`, `const char16_t *`, vb. vb.) temsil ettiğinde ve `?:` gerçek bağımsız değişken karşılık gelen türün bir dize harfi olduğunda, bu yaygın desenin önemli bir istisnası vardır. C++17 anlambilimi C++14'ten değiştirmiştir. Sonuç olarak, örnek 2'deki kod **/std:c++14** altında kabul edilir ve **/permissive-** **/Std:c++17** altında reddedilir. **/Zc:ternary**

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s;
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

Hataları görebileceğiniz başka bir durum türünden `void`bir bağımsız değişkenile koşullu işleçler. Bu durum ASSERT benzeri makrolarda yaygın olabilir.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Koşullu işleç sonuç türlerinin **/Zc:ternary** ve **/izin altında**değişebileceği şablon metaprogramming'de de hatalar görebilirsiniz. Bu sorunu çözmenin bir yolu [std kullanmaktır::remove_reference](../../standard-library/remove-reference-class.md) elde edilen türde.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>İki aşamalı ad araması

**/izin-** seçeneği ayarlandığında, derleyici işlevi ve sınıf şablon tanımlarını ayrıştırır ve şablonlarda kullanılan bağımlı ve bağımlı olmayan adları iki aşamalı ad araması için gerekli olduğu şekilde tanımlar. Visual Studio 2017 sürüm 15.3'te ad bağımlılığı çözümlemesi gerçekleştirilir. Özellikle, şablon tanımı bağlamında bildirilmeyen bağımlı olmayan adlar, ISO C++ standartlarının gerektirdiği tanılama iletisi oluşturmaz. Visual Studio 2017 sürüm 15.7'de, tanım bağlamında bağımsız lığa bağlı arama gerektiren bağımlı olmayan adların bağlanması da yapılır.

```cpp
// dependent base
struct B {
    void g() {}
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

İki aşamalı arama için eski davranış istiyorsanız, ancak başka bir şekilde **/izin verilen davranış** istiyorsanız, **/Zc:twoPhase-** seçeneğini ekleyin.

### <a name="windows-header-issues"></a>Windows üstbilgi sorunları

**/izin-** seçeneği, Windows Fall Creators Update SDK (10.0.16299.0) veya Windows Driver Kit (WDK) sürüm 1709'dan önceki Windows Kitleri sürümleri için çok katıdır. Windows veya aygıt sürücü kodunuzda **/izin** vermek için Windows Kitlerinin en son sürümlerine güncelleştirmenizi öneririz.

Windows Nisan 2018 Güncelleştirme SDK (10.0.17134.0), Windows Fall Creators Update SDK (10.0.16299.0) veya Windows Sürücü Kiti (WDK) 1709 bazı üstbilgi dosyaları, hala / izin kullanımı ile uyumsuz hale sorunları **var-**. Bu sorunları çözmek için, bu üstbilgilerin kullanımını yalnızca bunları gerektiren kaynak kodu dosyalarıyla sınırlamanızı ve bu belirli kaynak kodu dosyalarını derlediğinizde **/izin verme** seçeneğini kaldırmanızı öneririz.

Windows Nisan 2018 Update SDK 'da (10.0.17134.0) yayımlanan bu WinRT WRL başlıkları **/izin verilen lerle**temiz değildir. Bu sorunları aşmak için, bu üstbilgilerle çalışırken **/Zc:twoPhase** ile **/izin verme-** veya **/izin verme-** kullanmayın:

- Winrt/wrl/async.h'deki sorunlar

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Winrt/wrl/implements.h'deki sorun

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Windows Nisan 2018 Update SDK 'da (10.0.17134.0) yayımlanan bu Kullanıcı Modu başlıkları **/izin li**temiz değildir. Bu sorunları aşmak için, bu üstbilgilerle çalışırken **/izin verme-** kullanmayın:

- Um/Tune.h'deki sorunlar

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Konu um/spddkhlp.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco.h'deki sorunlar

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Bu sorunlar, Windows Fall Creators Update SDK'daki Kullanıcı Modu üstbilgilerine özgüdir (10.0.16299.0):

- um/Query.h'deki sorun

   **/izin verici** derleyici anahtarını kullanırken, `tagRESTRICTION` yapı case (RTOr) üyesi 'veya' nedeniyle derlemez.

   ```cpp
   struct tagRESTRICTION
   {
       ULONG rt;
       ULONG weight;
       /* [switch_is][switch_type] */ union _URes
       {
           /* [case()] */ NODERESTRICTION ar;
           /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
           /* [case()] */ NODERESTRICTION pxr;
           /* [case()] */ VECTORRESTRICTION vr;
           /* [case()] */ NOTRESTRICTION nr;
           /* [case()] */ CONTENTRESTRICTION cr;
           /* [case()] */ NATLANGUAGERESTRICTION nlr;
           /* [case()] */ PROPERTYRESTRICTION pr;
           /* [default] */  /* Empty union arm */
       } res;
   };
   ```

   Bu sorunu gidermek için, **/izin verme** seçeneği olmadan Query.h içeren dosyaları derleyin.

- Um/cellularapi_oem.h'deki sorun

   **/izin veren** derleyici anahtarını kullanırken, ileri `enum UICCDATASTOREACCESSMODE` deklarasyon bir uyarıya neden olur:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Kapsam dışı enumun ileri bildirimi bir Microsoft uzantısıdır. Bu sorunu gidermek için, **/izin verme** seçeneği olmadan cellularapi_oem.h içeren dosyaları derleyin veya C4471 uyarısını susturmak için [/wd](compiler-option-warning-level.md) seçeneğini kullanın.

- Um/omscript.h'deki sorun

   C++03'te, bir dize harfinden BSTR'ye dönüştürme (typedef'ten 'wchar_t *'' olarak) amortismana küçümsenmesine izin verilir. C++11'de dönüştürmeye artık izin verilmez.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Bu sorunu gidermek için, **/izin verme** seçeneği olmadan omscript.h içeren dosyaları derleyin veya **yerine /Zc:strictStrings** kullanın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

Visual Studio 2017 sürüm 15.5 ve sonraki sürümlerinde şu yordamı kullanın:

1. Projenizin **Özellik Sayfaları** iletişim kutusunu açın.

1. Yapılandırma **Özellikleri** > **C/C++** > **Dil** özelliği sayfasını seçin.

1. Uygunluk **modu** özellik değerini **Evet (/izin verme-) olarak değiştirin.** Değişikliklerinizi kaydetmek için **Tamam** veya **Uygula'yı** seçin.

Visual Studio 2017 sürüm 15.5'ten önceki sürümlerde şu yordamı kullanın:

1. Projenizin **Özellik Sayfaları** iletişim kutusunu açın.

1. Yapılandırma **Özellikleri** > **C/C++** > **Komut Satırı** özelliği sayfasını seçin.

1. **Ek Seçenekler** kutusuna **/izin verici-** derleyici seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam** veya **Uygula'yı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyici Seçenekleri](compiler-options.md)\
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
