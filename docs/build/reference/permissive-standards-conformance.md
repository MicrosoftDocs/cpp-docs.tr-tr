---
title: /permissive- (Standartlara uyumluluk)
description: Microsoft C++/Permissive-(standartlar uygunluğu) derleyici seçeneği için başvuru kılavuzu.
ms.date: 10/28/2020
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: c8d654540deb492a5bebff304ef01ca4c71f044a
ms.sourcegitcommit: 74e58bee5cffb30b66e17be6dbfde2544369638e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2021
ms.locfileid: "98763829"
---
# <a name="permissive--standards-conformance"></a>/permissive- (Standartlara uyumluluk)

Derleyiciye standartlar uygunluk modunu belirtin. Kodunuzda uyumluluk sorunlarını belirleyip düzeltmenize yardımcı olması için bu seçeneği kullanın. böylece, hem daha doğru hem de daha fazla taşınabilir hale getirebilirsiniz.

## <a name="syntax"></a>Syntax

> **`/permissive-`**\
> **`/permissive`**

## <a name="remarks"></a>Açıklamalar

Bu **`/permissive-`** seçenek, Visual Studio 2017 ve üzeri sürümlerde desteklenir. **`/permissive`** Visual Studio 2019 sürüm 16,8 ve sonraki sürümlerde desteklenir.

**`/permissive-`** Standartlara uygun derleyici davranışını belirtmek için derleyici seçeneğini kullanabilirsiniz. Bu seçenek, izin veren davranışları devre dışı bırakır ve [`/Zc`](zc-conformance.md) derleme seçeneklerini katı uyumluluk için ayarlar. IDE 'de, bu seçenek IntelliSense altyapısının duyarlı olmayan kodun altını çizerken de olmasını sağlar.

**`/permissive-`** Seçeneği, hangi dil yapılarının uyumsuz olduğunu anlamak için geçerli derleyici sürümündeki uygunluk desteğini kullanır. Bu seçenek, kodunuzun C++ standardının belirli bir sürümüne uyup uymadığını belirleyemez. En son taslak standardı için uygulanan tüm derleyici desteğini etkinleştirmek için [`/std:c++latest`](std-specify-language-standard-version.md) seçeneğini kullanın. Derleyici desteğini Şu anda uygulanmış olan C++ 17 standardına göre kısıtlamak için [`/std:c++17`](std-specify-language-standard-version.md) seçeneğini kullanın. Derleyici desteğini C++ 14 standardına daha yakından eşleşecek şekilde kısıtlamak için, [`/std:c++14`](std-specify-language-standard-version.md) varsayılan olan seçeneğini kullanın.

Visual Studio 2019 sürüm 16,8 ' den başlayarak, **`/std:c++latest`** seçeneği seçeneği örtülü olarak ayarlar **`/permissive-`** . C++ 20 modülleri desteği için gereklidir. Kodunuzda modül desteği gerekmez, ancak altında etkinleştirilmiş diğer özellikler gerekir **`/std:c++latest`** . Son tire olmadan seçeneğini kullanarak Microsoft uzantı desteğini açık bir şekilde etkinleştirebilirsiniz **`/permissive`** .

Varsayılan olarak, bu **`/permissive-`** seçenek Visual Studio 2017 sürüm 15,5 ve sonraki sürümleri tarafından oluşturulan yeni projelerde ayarlanır. Bu, önceki sürümlerde varsayılan olarak ayarlanmamış. Seçenek ayarlandığında, kodunuzda standart olmayan dil yapıları algılandığında derleyici tanılama hataları veya uyarılar üretir. Bu yapılar, pre-C + + 11 kodundaki bazı yaygın hataları içerir.

**`/permissive-`** Bu seçenek, Windows Fall CREATORS SDK (10.0.16299.0) ' den başlayarak, yazılım geliştirme seti (SDK) veya Windows Sürücü Seti (WDK) gibi en son Windows setlerinden tüm üstbilgi dosyalarının neredeyse tümüyle uyumludur. Diğer kaynak kodu uyumluluk nedenleriyle, SDK 'nın daha eski sürümleri tarafından derlenmesi başarısız olabilir **`/permissive-`** . Derleyici ve SDK 'lar farklı sürüm zaman çizelgeleriyle birlikte bulunduğundan bazı sorunlar daha vardır. Belirli üstbilgi dosyası sorunları için aşağıdaki [Windows üst bilgi sorunları](#windows-header-issues) bölümüne bakın.

**`/permissive-`** Seçeneği [`/Zc:referenceBinding`](zc-referencebinding-enforce-reference-binding-rules.md) ,, [`/Zc:strictStrings`](zc-strictstrings-disable-string-literal-type-conversion.md) ve [`/Zc:rvalueCast`](zc-rvaluecast-enforce-type-conversion-rules.md) seçeneklerini uyumlu davranış olarak ayarlar. Bu seçenekler varsayılan olarak duyarlı olmayan davranışa sahiptir. **`/Zc`** **`/permissive-`** Bu davranışı geçersiz kılmak için komut satırından sonra belirli seçenekleri geçirebilirsiniz.

Derleyicinin Visual Studio 2017 sürüm 15,3 ' den başlayarak sürümünde seçeneği, seçeneğini **`/permissive-`** Ayarlar [`/Zc:ternary`](zc-ternary.md) . Derleyici Ayrıca iki aşamalı ad araması için gereksinimlerin daha fazlasını uygular. **`/permissive-`** Seçenek ayarlandığında, derleyici işlev ve sınıf şablonu tanımlarını ayrıştırır ve şablonlarda kullanılan bağımlı ve bağımlı olmayan adları tanımlar. Bu sürümde, yalnızca ad bağımlılığı Analizi gerçekleştirilir.

Standart uygulamaya kaydolan ortama özgü uzantılar ve dil alanı tarafından etkilenmemektedir **`/permissive-`** . Örneğin, Microsoft 'a özgü **`__declspec`** , çağırma kuralı ve yapılandırılmış özel durum işleme anahtar sözcükleri ve derleyiciye özgü pragma yönergeleri ya da öznitelikleri, derleyici tarafından mod 'da bayraklamaz **`/permissive-`** .

Tüm C++ 11, C++ 14 ve C++ 17 standartlarına uygun kod, Visual Studio 2017 ' nin tüm sürümlerinde MSVC derleyicisi tarafından desteklenmez. Visual Studio sürümüne bağlı olarak, bu **`/permissive-`** seçenek iki aşamalı ad aramasının bazı yönlerinde sorunları tespit edebilir, const olmayan bir başvuruyu geçici olarak bağlayarak, başlangıç olarak doğrudan başlatma olarak, başlatma sırasında birden fazla Kullanıcı tanımlı dönüştürmeye izin verir, veya mantıksal işleçler için alternatif belirteçler ve desteklenmeyen diğer uygunluk alanları. Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md). En iyi şekilde yararlanmak için **`/permissive-`** Visual Studio 'yu en son sürüme güncelleştirin.

### <a name="how-to-fix-your-code"></a>Kodunuzu çözme

İşte **`/permissive-`** , sorunları çözmek için önerilen yollarla birlikte, kullanırken uyumsuz olarak algılanan kod örnekleri aşağıda verilmiştir.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Yerel kodda tanımlayıcı olarak Varsayılanı kullan

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Bağımlı tabandaki üyeleri ara

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Üye bildirimlerinde nitelenmiş adların kullanımı

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Üye başlatıcısında birden çok birleşim üyesini başlatma

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

Gizli arkadaş adı arama kurallarını kullanarak öğesinden bağımsız olarak etkinleştirebilirsiniz **`/permissive`** [`/Zc:hiddenFriend`](./zc-hiddenfriend.md) . Gizli arkadaş adı araması için eski davranışı isterseniz, aksi takdirde **`/permissive-`** davranışı istiyorsanız **`/Zc:hiddenFriend-`** seçeneğini kullanın.

#### <a name="use-scoped-enums-in-array-bounds"></a>Dizi sınırlarda kapsamlı numaralandırmalar kullanma

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Her bir yerel kod için kullanın

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

#### <a name="use-of-atl-attributes"></a>ATL özniteliklerinin kullanımı

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

Derleyicinin Visual Studio 2017 sürüm 15,3 ' den önceki sürümlerinde, derleyici bağımsız değişkenleri `?:` Standart tarafından belirsiz olarak kabul edilen koşullu işlece (veya üçlü operatör) kabul etti. **`/permissive-`** Modda, derleyici artık önceki sürümlerde tanılama olmadan derlenen durumlarda bir veya daha fazla tanılamayı yayınlar.

Bu değişikliğin neden olabileceği yaygın hatalar şunlardır:

- `error C2593: 'operator ?' is ambiguous`

- `error C2679: binary '?': no operator found which takes a right-hand operand of type 'B' (or there is no acceptable conversion)`

- `error C2678: binary '?': no operator found which takes a left-hand operand of type 'A' (or there is no acceptable conversion)`

- `error C2446: ':': no conversion from 'B' to 'A'`

Bu soruna neden olabilecek tipik bir kod deseninin bir sınıf C, başka bir tür T 'den açık olmayan bir Oluşturucu ve tür T olarak açık olmayan bir dönüştürme işlecinden sunmaktır. Bu durumda, ikinci bağımsız değişkeni üçüncü bağımsız değişkenin türüne dönüştürme ve üçüncü bağımsız değişkeni ikinci bağımsız değişkenin türüne dönüştürme geçerli dönüştürmelerdir. Her ikisi de geçerli olduğundan, standart öğesine göre belirsizdir.

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

T, null ile sonlandırılmış dize türlerinden birini temsil ettiğinde (örneğin,, vb `const char *` `const char16_t *` .) ve gerçek bağımsız değişkeni `?:` karşılık gelen türdeki bir dize sabit değeri olduğunda bu ortak düzende önemli bir özel durum vardır. C++ 17, C++ 14 ' ten semantiğini değiştirdi. Sonuç olarak, örnek 2 ' deki kod, **`/std:c++14`** veya kullanıldığında altında kabul edilir ve **`/std:c++17`** reddedilir **`/Zc:ternary`** **`/permissive-`** .

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

Hataların bir bağımsız değişkeni olan koşullu işleçte hata görebileceğiniz başka bir durum **`void`** . Bu durum, onay benzeri makrolarla ortak olabilir.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Ayrıca, koşullu işleç sonuç türlerinin ve altında değiştirebildiği şablon meta programlamada hatalar da görebilirsiniz **`/Zc:ternary`** **`/permissive-`** . Bu sorunu çözmek için bir yol, [`std::remove_reference`](../../standard-library/remove-reference-class.md) elde edilen tür üzerinde kullanmaktır.

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

**`/permissive-`** Seçenek ayarlandığında, derleyici, iki aşamalı ad araması için gereken şekilde şablonlarda kullanılan bağımlı ve bağımlı olmayan adları tanımlayarak işlev ve sınıf şablonu tanımlarını ayrıştırır. Visual Studio 2017 sürüm 15,3 ' de, ad bağımlılığı Analizi gerçekleştirilir. Özellikle, bir şablon tanımı bağlamında bildirilmeyen, bağımlı olmayan adlar, ISO C++ standartları için gereken bir tanılama iletisine neden olur. Visual Studio 2017 sürüm 15,7 ' de, tanım bağlamında bağımsız değişkene bağlı arama gerektiren bağımlı olmayan adların bağlanması da yapılır.

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

İki aşamalı arama için eski davranışı isterseniz, ancak davranışını istemiyorsanız, **`/permissive-`** **`/Zc:twoPhase-`** seçeneğini ekleyin.

### <a name="windows-header-issues"></a>Windows üst bilgisi sorunları

Bu **`/permissive-`** seçenek Windows Fall Creators Update SDK (10.0.16299.0) veya Windows Sürücü Seti (WDK) sürüm 1709 ' den önceki Windows setlerinin sürümleri için çok katı. Windows veya aygıt sürücü kodunuzda kullanmak üzere Windows setlerinin en son sürümlerine güncelleştirmenizi öneririz **`/permissive-`** .

Windows Nisan 2018 güncelleştirme SDK 'sindeki belirli üst bilgi dosyaları (10.0.17134.0), Windows Fall Creators Update SDK (10.0.16299.0) veya Windows Sürücü Seti (WDK) 1709, ile uyumlu olmayan sorunları yaşamaya devam etmektedir **`/permissive-`** . Bu sorunları geçici olarak çözmek için, bu üstbilgilerin kullanımını yalnızca bunları gerektiren kaynak kodu dosyalarıyla kısıtlayıp **`/permissive-`** Bu özel kaynak kodu dosyalarını derlerken seçeneğini kaldıraöneririz.

Windows Nisan 2018 güncelleştirme SDK 'sında (10.0.17134.0) yayınlanan bu WinRT WRL üstbilgileri ile temizmemektedir **`/permissive-`** . Bu sorunları geçici olarak çözmek için kullanmayın **`/permissive-`** veya **`/permissive-`** **`/Zc:twoPhase-`** Bu üst bilgilerle çalışırken ile kullanın:

- WinRT/WRL/Async. h içindeki sorunlar

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- WinRT/WRL/Implements. h 'de sorun

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Windows Nisan 2018 güncelleştirme SDK 'sında (10.0.17134.0) yayınlanan bu kullanıcı modu başlıkları ile temizmemektedir **`/permissive-`** . Bu sorunları geçici olarak çözmek için **`/permissive-`** Şu üst bilgilerle çalışırken kullanmayın:

- Um/ayar. h içindeki sorunlar

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Um/spddkhlp. h 'de sorun

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco. h içindeki sorunlar

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Bu sorunlar, Windows Fall Creators Update SDK 'daki (10.0.16299.0) Kullanıcı modu üst bilgilerine özgüdür:

- Um/sorgu. h 'de sorun

   **`/permissive-`** Derleyici anahtarını kullanırken, `tagRESTRICTION` ' veya ' Case (rtor) üyesi nedeniyle yapı derlenmez.

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

   Bu sorunu gidermek için, seçeneği olmadan Query. h içeren dosyaları derleyin **`/permissive-`** .

- Um/cellularapi_oem. h 'de sorun

   **`/permissive-`** Derleyici anahtarı kullanılırken, iletme bildirimi `enum UICCDATASTOREACCESSMODE` bir uyarıya neden olur:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Kapsamlı olmayan numaralandırmanın ileri bildirim bir Microsoft uzantısıdır. Bu sorunu gidermek için, seçeneği olmadan cellularapi_oem. h içeren dosyaları derleyin **`/permissive-`** veya [`/wd`](compiler-option-warning-level.md) C4471 uyarı seçeneğini kullanın.

- Um/omscript. h 'de sorun

   C++ 03 ' de, bir dize sabit değerinden BSTR 'ye (' wchar_t * ' için bir typedef) dönüştürme kullanım dışıdır ancak izin verilir. C++ 11 ' de dönüştürmeye artık izin verilmez.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Bu sorunu gidermek için, seçeneği olmadan omscript. h içeren dosyaları derleyin **`/permissive-`** veya **`/Zc:strictStrings-`** bunun yerine kullanın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

Visual Studio 2017 sürüm 15,5 ve sonraki sürümlerinde şu yordamı kullanın:

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** özellik sayfasını seçin.

1. **Uyumluluk modu** özellik değerini **Evet (/Permissive-)** olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

Visual Studio 2017 sürüm 15,5 ' den önceki sürümlerde şu yordamı kullanın:

1. Projenizin **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/Permissive-** derleyici seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
