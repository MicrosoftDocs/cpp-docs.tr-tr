---
title: -izin veren - (standartları uyumluluğu) | Microsoft Docs
ms.date: 06/21/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
dev_langs:
- C++
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1a9c407779b6bf441ea1375026af6ac04bb8c8
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322270"
---
# <a name="permissive--standards-conformance"></a>/ izin veren-(standartları uyumluluğu)

Derleyici standartları uyumluluğu modu belirtin. Tanımlamak ve daha doğru ve daha kolay taşınabilir yapmak için kodunuzda, uyumluluk sorunları gidermenize yardımcı olması için bu seçeneği kullanın.

## <a name="syntax"></a>Sözdizimi

> **/ izin veren-**

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz **/ izin veren-** derleyici seçeneği standartları uyumsuz derleyici davranışı belirtin. Bu seçenek, izin veren davranışları devre dışı bırakır ve ayarlar [/Zc](../../build/reference/zc-conformance.md) katı uyumluluk derleyici seçenekleri. IDE içinde bu seçenek ayrıca IntelliSense altyapısı altı çizili uyumsuz kod kılar.

Varsayılan olarak, **/ izin veren-** seçeneği, Visual Studio 2017 sürüm 15,5 ve sonraki sürümler tarafından oluşturulan yeni projeler ayarlanır. Önceki sürümlerde varsayılan olarak ayarlı değil. Seçeneğini belirleyerek, tanılama hataları derleyici oluşturur ya da standart olmayan dil yapılandırdığında uyarıları, kodunuzda algılanır bazı yaygın hatalar öncesi dahil olmak üzere-C ++ 11 kodu.

**/ İzin veren-** seçeneği, neredeyse tüm Yazılım Geliştirme Seti (SDK) veya Windows sonbaharda oluşturucuları SDK (10.0.16299.0) başlayarak Windows Sürücü Seti (WDK) gibi en son Windows Setleri başlık dosyalarından ile uyumludur. SDK'ın eski sürümleri altında derlemek başarısız olabilir **/ izin veren-** çeşitli kod uygunluk nedenleri kaynağı için. Derleyici ve SDK'ları sevk üzerinde farklı bir sürüm zaman çizelgeleri, bu nedenle kalan bazı sorunlar vardır. Özel üstbilgi dosyası sorunları için bkz: [Windows üstbilgi sorunları](#windows-header-issues) aşağıda.

**/ İzin veren-** seçeneği ayarlar [/ZC: strictstrings](../../build/reference/zc-conformance.md) ve [/Zc:rvalueCast](../../build/reference/zc-conformance.md) uyumlu davranış seçenekleri. Bunlar varsayılan uyumsuz davranışı için. Belirli geçirebilirsiniz **/Zc** sonra seçenekleri **/ izin veren-** bu davranışı geçersiz kılmak için komut satırında.

Visual Studio 2017 sürüm 15.3, derleyici başında sürümlerinde **/ izin veren-** seçeneği ayarlar [/Zc:ternary](../../build/reference/zc-ternary.md) seçeneği. Derleyici iki aşamalı adı araması gereksinimlerini daha fazla uygular. Zaman **/ izin veren-** seçeneği olarak ayarlanmışsa, derleyici şablonlarında kullanılan bağımlı ve bağımlı olmayan adları tanımlayan işlevi ve sınıf şablonu tanımlarını ayrıştırır. Bu sürümde, yalnızca ad Bağımlılık çözümlemesini gerçekleştirilir.

Ortama özgü Uzantılar ve standart kadar uygulama bırakır dil alanları etkilenmez **/ izin veren-**. Örneğin, Microsoft'a özgü `__declspec`, çağırma ve yapılandırılmış özel durum işleme anahtar sözcükler ve derleyici özgü pragma yönergeleri veya öznitelikleri değil bayrağı derleyici tarafından **/ izin veren-** modu.

**/ İzin veren-** seçeneği uyumsuz hangi dil yapıları belirlemek üzere geçerli derleyici sürümde uygunluk destek kullanır. Seçeneği, kodunuzu standart C++ belirli bir sürümünü uyup uymadığını belirlemez. En son taslak standart tüm uygulanan derleyici desteğini etkinleştirmek için kullanın [/std:latest](../../build/reference/std-specify-language-standard-version.md) seçeneği. Derleyici desteği şu anda uygulanan C ++ 17 için standart kısıtlamak için [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) seçeneği. C ++ 14 standart daha yakından eşleşecek şekilde derleyici desteği kısıtlamak için [/Std: c ++ 14](../../build/reference/std-specify-language-standard-version.md) varsayılan seçeneği.

Değil tüm C ++ 11, C ++ 14 veya standartları uyumsuz C ++ 17 kod, Visual Studio 2017'de Visual C++ derleyicisi tarafından desteklenir. Visual Studio sürümüne bağlı olarak **/ izin veren-** seçeneği bazı yönlerini iki aşamalı ad arama ile ilgili, geçici bir const olmayan başvuru bağlama, kopyalama init doğrudan init davranma, izin sorunları algılama birden çok kullanıcı tanımlı dönüştürmeler başlatma veya alternatif belirteçler için mantıksal işleçler ve diğer desteklenmeyen uygunluk alanları. Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md). En dışı almak için **/ izin veren-**, Visual Studio en son sürüme güncelleştirin.

### <a name="how-to-fix-your-code"></a>Kodunuzu düzeltme yapma

İşte bazı örnekler kullandığınız zaman uyumsuz olarak algılanan kod **/ izin veren-**, sorunları gidermek için önerilen yol yanı sıra.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Yerel kodda bir tanımlayıcı olarak Varsayılanı kullan

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>Bağımlı Bankası arama üyeleri

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Nitelikli adlar üye bildirimlerden kullanımı

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Üye başlatıcıdan birden fazla birleşim üyeleri başlatma

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

#### <a name="use-scoped-enums-in-array-bounds"></a>Dizi sınırları kapsamlı kullanım numaralandırmaları

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Her yerel kodda kullanma

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

#### <a name="use-of-atl-attributes"></a>ATL özniteliklerin kullanın

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Belirsiz koşullu işleç bağımsız değişkenler

Visual Studio 2017 sürüm 15.3 önce derleyici sürümlerinde derleyici koşullu işleç (veya Üçlü işleci) bağımsız değişkenleri kabul `?:` , değerlendirilir belirsiz standardına göre. İçinde **/ izin veren-** modu, derleyici şimdi önceki sürümlerde tanılama olmadan derlenen durumlarda bir veya daha fazla tanılama verir.

Bu değişikliği sonuçlanabilir yaygın yönlendirme hataları şunlardır:

- hata C2593: '' işleci? belirsiz

- hata C2679: ikili '?': işleç bulundu 'B' türündeki sağ işleneni aldığı (veya kabul edilebilir bir dönüştürme yok)

- hata C2678: ikili '?': işleç bulundu 'A' türündeki sol işleneni aldığı (veya kabul edilebilir bir dönüştürme yok)

- hata C2446: ':': 'B' dönüştürme yok 'A'

Bu soruna neden olabilir tipik kod düzeni olduğunda bazı sınıfı C t türü için başka bir türden T açık olmayan bir oluşturucu ve açık olmayan bir dönüşüm işleci sağlar Bu durumda, 3 türü 2 bağımsız değişkeni dönüştürülmesi ve 3 bağımsız değişkeni dönüştürme 2 türü için geçerli dönüşümler göre standart belirsiz var.

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

Yapıldığında bu ortak modelinin önemli bir özel durum T null ile sonlandırılmış dize türlerinden birini temsil eder (örneğin, `const char *`, `const char16_t *`, vb.) ve gerçek bağımsız değişkeni `?:` bir dize değişmez değer karşılık gelen türü. C ++ 17 C ++ 14'anlamsallarını değişti. Örnek 2 kodda altında sonucu olarak kabul **/Std: c ++ 14** ve altında reddedilen **/Std: c ++ 17** zaman **/Zc:ternary** veya **/permissive-** kullanılır.

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

Koşullu işleçler türünde bir bağımsız değişken ile hataları karşılaşabileceğiniz başka bir örneği yer `void`. Bu durumda ASSERT benzeri makroları ortak olabilir.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Şablon meta, burada koşullu işleç sonucu türleri değişebilir altında hatalar da görebilirsiniz **/Zc:ternary** ve **/ izin veren-**. Bu sorunu kullanmaktır çözümlemek için tek yönlü [std::remove_reference](../../standard-library/remove-reference-class.md) elde edilen türü.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>İki aşamalı adı Ara

Zaman **/ izin veren-** seçeneği olarak ayarlanmışsa, bağımlı ve bağımlı olmayan adları şablonlarında gerektiği gibi iki aşamalı adı araması için kullanılan tanımlama işlevi ve sınıf şablonu tanımlarını derleyici ayrıştırır. Visual Studio 2017 içinde sürüm 15.3, ad Bağımlılık çözümlemesini gerçekleştirilir. Özellikle, şablon tanımının bağlamda bildirilmemiş bağlı olmayan adları bir tanılama iletisi ISO C++ standartları gerektirdiği neden. Visual Studio 2017 içinde sürüm 15.7, bağlama bağımsız değişkeni bağımlı Ara tanımı bağlamda gerektiren bağlı olmayan adlarını da yapılır.

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

İki aşamalı arama için eski davranışı istiyor ancak Aksi halde istediğiniz varsa **/ izin veren-** davranışı eklemek **/Zc:twoPhase-** seçeneği.

### <a name="windows-header-issues"></a>Windows üstbilgi sorunları

**/ İzin veren-** seçenektir Windows sonbaharda oluşturucuları güncelleştirmenin SDK'sı (10.0.16299.0) önce Windows Setleri sürümlerini ya da Windows Sürücü Seti (WDK) sürüm 1709 için çok sıkı. Kullanmak için en son sürümlerini Windows Setleri güncelleştirme öneririz **/ izin veren-** Windows veya aygıt sürücüsü kodunuzda.

Belirli üstbilgi dosyaları 2018 güncelleştirmenin SDK'sı (10.0.17134.0), Windows sonbaharda oluşturucuları güncelleştirmenin SDK (10.0.16299.0) veya Windows Sürücü Seti (WDK) 1709, Windows Nisan'ın kullanımı ile uyumsuz hale sorunları çözümlenmedi **/permissive-**. Bu sorunların olarak çözmek için bunları gerektiren ve kaldırma yalnızca bu kaynak kodu dosyaları için bu üstbilgileri kullanımını kısıtlamak öneririz **/ izin veren-** seçeneği bu belirli kaynak kodu dosyaları derlediğinizde.

Yayımlanan bu WinRT WRL üstbilgileri Windows Nisan 2018 güncelleştirmenin SDK'sı (10.0.17134.0) olmayan temiz ile **/ izin veren-**. Bu sorunların olarak çözmek için ya da kullanmayın **/ izin veren-**, veya **/ izin veren-** ile **/Zc:twoPhase-** bu üstbilgileri ile çalışırken:

- Winrt/wrl/async.h sorunları

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- İçinde winrt/wrl/implements.h sorun

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Yayımlanan bu kullanıcı modu üstbilgileri Windows Nisan 2018 güncelleştirmenin SDK'sı (10.0.17134.0) olmayan temiz ile **/ izin veren-**. Bu sorunların olarak çözmek için kullanmayın **/ izin veren-** bu üstbilgileri ile çalışırken:

- Um/Tune.h sorunları

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- İçinde um/spddkhlp.h sorun

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco.h sorunları

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Bu sorunlar, Windows sonbaharda oluşturucuları güncelleştirmenin SDK (10.0.16299.0) kullanıcı modu üstbilgilerinde özeldir:

- İçinde um/Query.h sorun

   Kullanırken **/ izin veren-** derleyici anahtar `tagRESTRICTION` yapısı nedeniyle case(RTOr) üye derlenmez 'veya'.

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

   Bu sorunu gidermek için olmadan Query.h dahil dosyalarını derlemek **/ izin veren-** seçeneği.

- İçinde um/cellularapi_oem.h sorun

   Kullanırken **/ izin veren-** derleyici anahtar, ileriye dönük bildirimi `enum UICCDATASTOREACCESSMODE` bir uyarı neden olur:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Dizininden kapsam dışı enum iletme bildirimi bir Microsoft uzantısıdır. Bu sorunu gidermek için olmadan cellularapi_oem.h dahil dosyalarını derlemek **/ izin veren-** seçeneğini veya kullanmak [/wd](../../build/reference/compiler-option-warning-level.md) uyarı C4471 sessiz seçeneği.

- İçinde um/omscript.h sorun

   C ++ 03, bir değişmez dize dönüştürme BSTR için de (bir typedef olduğu ' wchar_t *') kullanım dışı izin değil. C ++ 11'de, dönüştürme artık izin verilir.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Bu sorunu gidermek için olmadan omscript.h dahil dosyalarını derlemek **/ izin veren-** seçeneğini veya kullanmak **/Zc:strictStrings-** yerine.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

Visual Studio 2017 sürüm 15,5 ve sonraki sürümleri, bu yordamı kullanın:

1. Projenizin açmak **özellik sayfaları** iletişim kutusu.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **dil** özellik sayfası.

1. Değişiklik **uyumluluk modu** özellik değerine **Evet (/ izin veren-)**. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.

Visual Studio 2017 sürüm 15,5 önce sürümlerinde, bu yordamı kullanın:

1. Projenizin açmak **özellik sayfaları** iletişim kutusu.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Girin **/ izin veren-** derleyici seçeneği **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
