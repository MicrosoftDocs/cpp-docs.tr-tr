---
description: 'Daha fazla bilgi edinin: `/Zc:ternary` (koşullu işleç kurallarını zorla)'
title: /Zc:ternary (Koşullu işleç kurallarını zorla)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: ea1cf57aa1633e08095dfd01964a2255cb0b3c70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271323"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>`/Zc:ternary` (Koşullu işleç kurallarını zorla)

Koşullu bir operatör ifadesinde ikinci ve üçüncü işlenenlerinin türleri ve const veya volatile (CV) niteliği için C++ standart kurallarının uygulanmasını etkinleştirin.

## <a name="syntax"></a>Syntax

> **`/Zc:ternary`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017 ' den başlayarak, derleyici C++ standart *koşullu işleci* ( **`?:`** ) davranışını destekler. *Üçlü işleç* olarak da bilinir. C++ standardı Üçlü işlenenlerinin üç koşuldan birini karşılemesini gerektirir: işlenenler aynı türde ve **`const`** veya **`volatile`** niteliğin (CV-nitelik) olmalıdır, ya da yalnızca bir işlenen aynı türe ve CV niteleyicisini diğeri ile kesin bir şekilde dönüştürülebilir olmalıdır. Ya da, bir veya her iki işlenen de bir throw ifadesi olmalıdır. Visual Studio 2017 sürüm 15,5 ' den önceki sürümlerde, derleyici standart tarafından belirsiz olarak kabul edilen Dönüştürmelere izin verilir.

**`/Zc:ternary`** Seçenek belirtildiğinde, derleyici standarda uygun olur. Bu, eşleşen türler ve ikinci ve üçüncü işlenenlerde CV niteliği için kuralları karşılamayan kodu reddeder.

Bu **`/Zc:ternary`** seçenek, Visual Studio 2017 ' de varsayılan olarak kapalıdır. Uygun **`/Zc:ternary`** davranışı etkinleştirmek veya **`/Zc:ternary-`** önceki uyumlu olmayan derleyici davranışını açıkça belirtmek için kullanın. [`/permissive-`](permissive-standards-conformance.md)Seçeneği bu seçeneği örtülü olarak etkinleştirdiğinden, kullanılarak geçersiz kılınabilir **`/Zc:ternary-`** .

### <a name="examples"></a>Örnekler

Bu örnek, bir türden hem açık olmayan başlatma hem de türe dönüştürme sağlayan bir sınıfın, belirsiz Dönüştürmelere neden olabileceği gösterilmektedir. Bu kod, derleyici tarafından varsayılan olarak kabul edilir, ancak **/`Zc:ternary`** veya belirtildiğinde reddedilir **`/permissive-`** .

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

Bu kodu onarmak için, tercih edilen ortak türe açık bir dönüştürme yapın veya tür dönüştürmesinin bir yönünü önleyin. Derleyiciyi açıkça dönüştürmeyi yaparak derleyicinin tür dönüştürmesinin eşleşmesini sağlayabilirsiniz.

Bu ortak model için önemli bir özel durum, işlenen türünün, ve gibi null sonlandırılmış dize türlerinden biri olduğu durumdur `const char*` `const char16_t*` . Ayrıca, dizi türleri ve işaret ettikleri işaretçi türleri ile efekti yeniden oluşturabilirsiniz. ' Ye gerçek ikinci veya üçüncü işlenen, `?:` karşılık gelen türden bir dize sabit değeri olduğunda, kullanılan dil standardına göre değişir. C++ 17, C++ 14 ' ten bu durum için semantiğini değiştirdi. Sonuç olarak, derleyici varsayılan olarak aşağıdaki örnekteki kodu kabul eder **`/std:c++14`** , ancak belirttiğinizde bunu reddeder **`/std:c++17`** .

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

Bu kodu onarmak için işlenenlerinin birini açık olarak atayın.

' In altında, **`/Zc:ternary`** derleyici bağımsız değişkenlerden birinin tür olduğu **`void`** ve diğeri bir ifade olmadığı koşullu işleçleri reddeder **`throw`** . Bu düzenin yaygın kullanımı, onay benzeri makrolardır:

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

Tipik çözüm, void olmayan bağımsız değişkenini ile değiştirmek `void()` .

Bu örnek, hem hem de içinde hata oluşturan kodu **`/Zc:ternary`** gösterir **`/Zc:ternary-`** :

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

Bu kod, daha önce bu hatayı verdi:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

İle **`/Zc:ternary`** hata nedeni daha net hale gelir. Her bir Lambda oluşturmak için uygulama tanımlı birkaç çağırma kuralı kullanılabilir. Ancak, derleyicinin olası lambda imzalarını belirsizliğini ortadan kaldırmak için tercih kuralı yoktur. Yeni çıktı şöyle görünür:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Tarafından bulunan yaygın bir sorun kaynağı, **`/Zc:ternary`** şablon meta programlamada kullanılan koşullu işleçlerden gelir. Sonuç türlerinden bazıları bu anahtar altında değişir. Aşağıdaki örnek, **`/Zc:ternary`** koşullu bir ifadenin sonuç türünü meta programlama bağlamında değiştiren iki durumu gösterir:

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

Tipik düzeltmeler, `std::remove_reference` sonuç türü üzerinde, eski davranışı korumak için gereken bir nitelik uygulamaktır.

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini, veya içerecek şekilde **`/Zc:ternary`** değiştirin **`/Zc:ternary-`** ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc` Uyumsuzlu](zc-conformance.md)
