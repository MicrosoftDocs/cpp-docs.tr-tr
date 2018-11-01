---
title: / permissive-(standartlara uyumluluk)
ms.date: 06/21/2018
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 85439598ae4c3e0f9ef923f21e701e0399aefa70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619303"
---
# <a name="permissive--standards-conformance"></a>/ permissive-(standartlara uyumluluk)

Derleyici standartlara uyumluluk modu belirtin. Tanımlamak ve kodunuza daha doğru ve daha taşınabilir yapmak için uyumluluk sorunları gidermenize yardımcı olması için bu seçeneği kullanın.

## <a name="syntax"></a>Sözdizimi

> **/ permissive-**

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017 ve sonraki sürümlerde desteklenir.

Kullanabileceğiniz **/ permissive-** standartlara uyan derleyici davranışını belirtmek için derleyici seçeneği. Bu seçenek, İhtiyari davranışları devre dışı bırakır ve ayarlar [/Zc](../../build/reference/zc-conformance.md) katı uyumluluk derleyici seçenekleri. IDE'de, bu seçenek ayrıca IntelliSense altyapısı altı çizili DSCP kod yapar.

Varsayılan olarak, **/ permissive-** seçeneği, Visual Studio 2017 sürüm 15.5 ve sonraki sürümler tarafından oluşturulan yeni projeler ayarlanır. Önceki sürümlerde varsayılan olarak ayarlanmadı. Seçeneğini ayarlamak, derleyici tanılama hatası veriyorsa ya da standart olmayan dil yapılandırdığında uyarıları kodunuzda algılandı bazı yaygın hatalar öncesi dahil olmak üzere-C ++ 11 kod.

**/ Permissive-** seçeneği, neredeyse tüm son Windows Setleri, Yazılım Geliştirme Seti (SDK) veya Windows Sürücü Seti'nin (WDK), Windows Fall Creators SDK (10.0.16299.0) başlatma gibi üstbilgi dosyalarından ile uyumludur. Altında derlemek SDK'sının daha eski sürümleri kaydedemeyebilir **/ permissive-** çeşitli kod uyumluluk nedeniyle kaynağı için. Derleyici ve SDK'ları sevk üzerinde farklı yayın zaman çizelgelerini, bu nedenle kalan bazı sorunlar vardır. Özel üst bilgi dosyası sorunları için bkz: [Windows üst bilgi sorunları](#windows-header-issues) aşağıda.

**/ Permissive-** seçenek kümeleri [/ZC: strictstrings](../../build/reference/zc-conformance.md) ve [/ZC: rvaluecast](../../build/reference/zc-conformance.md) uyumlu davranışı seçenekleri. Bunlar varsayılan DSCP davranışı için. Belirli geçirebilirsiniz **/Zc** sonra seçenekleri **/ permissive-** bu davranışı geçersiz kılmak için komut satırında.

Visual Studio 2017 sürüm 15.3, derleyici başlangıçta sürümlerinde **/ permissive-** seçenek kümeleri [/ZC: ternary](../../build/reference/zc-ternary.md) seçeneği. Derleyici daha iki aşamalı ad arama gereksinimlerini uygular. Zaman **/ permissive-** seçeneği ayarlanır, derleme şablonlarında kullanılan bağımlı ve bağımlı olmayan adları tanımlama, işlevi ve sınıf şablonu tanımlarını ayrıştırır. Bu sürümde, yalnızca ad bağımlılık analizi gerçekleştirilir.

Ortama özgü Uzantılar ve standart uygulama en fazla bırakır dil alanları etkilenmez **/ permissive-**. Örneğin, Microsoft'a özgü `__declspec`, çağırma kuralı ve yapılandırılmış özel durum işleme anahtar sözcükler ve derleyiciye özgü pragma yönergeleri veya öznitelikleri değil işaretlenir derleyici tarafından **/ permissive-** modu.

**/ Permissive-** seçeneği DSCP hangi dil yapıları belirlemek üzere geçerli derleyici sürümünde uyumluluk desteği kullanır. Seçeneği, kodu belirli bir C++ standart sürümü için uygun olup olmadığı. En son taslak standardı için tüm uygulanan derleyici desteği etkinleştirmek için [/std:latest](../../build/reference/std-specify-language-standard-version.md) seçeneği. Şu anda uygulanan C ++ 17'ye standart derleyici desteği kısıtlamak için [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) seçeneği. Derleyici desteği, C ++ 14 standardı daha yakından eşleşecek şekilde kısıtlamak için [/Std: c ++ 14](../../build/reference/std-specify-language-standard-version.md) seçeneği, varsayılan değerdir.

Değil tüm C ++ 11, C ++ 14 ve C ++ 17 standartlarına uygun kod, Visual Studio 2017 için Visual C++ derleyicisi tarafından desteklenir. Visual Studio sürümüne bağlı olarak **/ permissive-** seçeneği ile ilgili bazı yönleri iki aşamalı ad aramayı, geçici bir const olmayan başvuruya bağlanıyor, kopya başlatma doğrudan init davranılması, izin sorunları algılama birden çok kullanıcı tanımlı dönüşümler başlatma veya alternatif belirteçler için mantıksal işleçler ve diğer desteklenmeyen uygunluk alanları. Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md). En iyi şekilde faydalanmaya yönelik **/ permissive-**, Visual Studio'nun en son sürüme güncelleştirin.

### <a name="how-to-fix-your-code"></a>Kodunuzu düzeltmenin nasıl

İşte bazı örnekler kullandığınız zaman uyumsuz olarak algılanan kod **/ permissive-**, sorunları gidermek için önerilen yol yanı sıra.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Yerel kodda bir tanımlayıcı olarak Varsayılanı kullan

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>Bağımlı tabanında arama üyeleri

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Üyesi bildiriminde nitelenmiş adlar kullanımı

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Birleşim birden çok üye Başlatıcı üyelerinde Başlat

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
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>Kapsamlı numaralandırmalar dizi sınırları kullanın

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Her yerel kodda kullanın

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

#### <a name="use-of-atl-attributes"></a>ATL öznitelikleri kullanım

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Belirsiz koşullu işlecin bağımsız değişkenleri

Visual Studio 2017 sürüm 15.3 önce derleyici sürümlerinde, derleyici bağımsız değişkenleri koşullu işleç (veya Üçlü işleci) kabul edilen `?:` , değerlendirilir belirsiz standardına göre. İçinde **/ permissive-** modu, derleyici artık önceki sürümlerde tanılama olmadan derlenmiş durumlarda bir veya daha fazla tanılama verir.

Bu değişiklik sonuçlanabilir Commmon hataları şunlardır:

- hatası C2593: 'işlecini'? belirsiz

- hatası C2679: ikili '?': 'B' türünde bir sağ taraf işleneni alan hiçbir işleç bulunamadı (veya hiç kabul edilebilir dönüştürme yok)

- hatası C2678: ikili '?': 'A' türünde bir sol taraf işleneni alan hiçbir işleç bulunamadı (veya hiç kabul edilebilir dönüştürme yok)

- hatası C2446: ':': hiçbir 'A'-'B' dönüşümü

Bazı C sınıfı türüne t T başka bir türden bir açık olmayan Oluşturucu hem bir açık olmayan bir dönüşüm işleci sağladığında bu soruna neden olabilecek bir tipik kod modelidir Bu durumda, hem 2 bağımsız değişkenin 3 tür dönüştürme ve 3 bağımsız değişkenin 2 tür dönüştürme geçerli dönüşümler standardına göre belirsiz'dır.

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

T null ile sonlandırılmış dize türlerinden birini temsil eder, bu yaygın bir düzen için önemli bir özel olan (örneğin, `const char *`, `const char16_t *`, vb.) ve gerçek bağımsız değişkeni `?:` bir dizedir karşılık gelen tür sabit değeri. C ++ 17 semantiği C ++ 14'olarak değişti. Sonuç olarak, örnek 2 kodda altında kabul **/Std: c ++ 14** ve reddedilen altında **/Std: c ++ 17** olduğunda **/ZC: ternary** veya **/permissive-** kullanılır.

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

Koşullu işleçler argumentem typu hataları karşılaşabileceğiniz başka bir örneği yer `void`. Bu durumda onay benzeri makrolarda ortak olabilir.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Burada koşullu işleç sonuç türleri değişebilir altında şablon meta, hatalar da görebilirsiniz **/ZC: ternary** ve **/ permissive-**. Bu sorunu kullanmaktır çözmek için tek yönlü [std::remove_reference](../../standard-library/remove-reference-class.md) sonuç türü.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>İki aşamalı ad arama

Zaman **/ permissive-** seçeneği ayarlanır, derleyici bağımlı ve bağımlı olmayan adları şablonlarında gerektiği gibi iki aşamalı ad arama için kullanılan tanımlama, işlevi ve sınıf şablonu tanımlarını ayrıştırır. Visual Studio 2017 sürüm 15.3, adı bağımlılık analizi gerçekleştirilir. Özellikle, bir tanılama iletisi ISO C++ standartlarına gerektirdiği gibi bir şablon tanımı bağlamda bildirilmemiş olan bağımlı olmayan adları neden. Visual Studio 2017 sürüm 15.7, bağımsız değişken bağımlı Ara tanımı bağlamda gerektirir bağımlı olmayan adları bağlama da gerçekleştirilir.

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

Eski davranışı için iki aşamalı arama istiyor ancak Aksi takdirde istediğiniz varsa **/ permissive-** davranışı eklemek **/Zc:twoPhase-** seçeneği.

### <a name="windows-header-issues"></a>Windows üst bilgi sorunları

**/ Permissive-** seçeneği Windows Fall Creators Update SDK (10.0.16299.0) önce Windows Setleri sürümlerini ya da Windows Sürücü Seti'nin (WDK) sürüm 1709 için çok sıkı. Kullanmak için en son sürümlerini Windows Setleri güncelleştirmeniz önerilir **/ permissive-** Windows veya aygıt sürücüsü kodunuzda.

Belirli Windows Nisan 2018 güncelleştirme SDK (10.0.17134.0), Windows Fall Creators Update SDK (10.0.16299.0) veya Windows Sürücü Seti'nin (WDK) 1709, üstbilgi dosyalarında kullanımıyla uyumlu hale sorunları çözümlenmedi **/permissive-**. Bu sorunların çözüm için şart ve kaldırma yalnızca kaynak kodu dosyaları için bu üstbilgileri kullanımını kısıtlamak öneririz **/ permissive-** seçeneği, bu belirli kaynak kod dosyalarını derlerken.

Yayımlanan bu WinRT WRL üstbilgileri içinde Windows Nisan 2018 güncelleştirme SDK (10.0.17134.0) olmayan temiz ile **/ permissive-**. Bu sorunların çözüm için ya da kullanmayın **/ permissive-**, veya **/ permissive-** ile **/Zc:twoPhase-** bu üst bilgileri ile çalışırken:

- Winrt/wrl/async.h sorunları

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- İçinde winrt/wrl/implements.h sorunu

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Yayımlanan bu kullanıcı modu üstbilgileri içinde Windows Nisan 2018 güncelleştirme SDK (10.0.17134.0) olmayan temiz ile **/ permissive-**. Bu sorunların çözüm için kullanmayın **/ permissive-** bu üst bilgileri ile çalışırken:

- Um/Tune.h sorunları

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- İçinde um/spddkhlp.h sorunu

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco.h sorunları

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Bu sorunlar, Windows Fall Creators Update SDK (10.0.16299.0) kullanıcı modu üstbilgilerinde özgüdür:

- İçinde um/Query.h sorunu

   Kullanırken **/ permissive-** derleyici anahtarı `tagRESTRICTION` yapısı nedeniyle case(RTOr) üye derlenmez 'veya'.

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

   Bu sorunu gidermek için olmadan Query.h içeren dosyaların derleme **/ permissive-** seçeneği.

- İçinde um/cellularapi_oem.h sorunu

   Kullanırken **/ permissive-** derleyici anahtarı, İleri dönük bildiriminin `enum UICCDATASTOREACCESSMODE` bir uyarısına neden olur:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Kapsamsız bir Enum İleri dönük bildirimi bir Microsoft uzantısıdır. Bu sorunu gidermek için olmadan cellularapi_oem.h içeren dosyaların derleme **/ permissive-** seçeneğini veya kullanın [/wd](../../build/reference/compiler-option-warning-level.md) uyarı C4471 sessiz için seçeneği.

- İçinde um/omscript.h sorunu

   C ++ 03, bir dize sabit değerinden dönüştürme BSTR, (tür tanımı olduğu ' wchar_t *') izin verilen ancak kullanım dışı. C ++ 11'de, dönüştürme artık izin verilmez.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Bu sorunu gidermek için olmadan omscript.h içeren dosyaların derleme **/ permissive-** seçeneğini veya kullanın **/Zc:strictStrings-** yerine.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

Visual Studio 2017 sürüm 15.5 ve sonraki sürümlerinde, bu yordamı kullanın:

1. Projenizin açın **özellik sayfaları** iletişim kutusu.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** özellik sayfası.

1. Değişiklik **uyumluluk modu** özellik değerini **Evet (/ permissive-)**. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

Visual Studio 2017 sürüm 15.5 önce sürümlerinde, bu yordamı kullanın:

1. Projenizin açın **özellik sayfaları** iletişim kutusu.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/ permissive-** derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
