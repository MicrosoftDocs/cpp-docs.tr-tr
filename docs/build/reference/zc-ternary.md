---
title: /Zc:ternary (Koşullu işleç kurallarını zorla)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 7c95f061e195ccf7fef8a6a21d193b257baa5f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335674"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (Koşullu işleç kurallarını zorla)

Koşullu işleç ifadesinde ikinci ve üçüncü operandların türleri ve const veya uçucu (cv) niteliği için C++ Standart kurallarının uygulanmasını etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/Zc:ternary****-**[ ]

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017'den başlayarak derleyici C++ standart *koşullu işleci* **(?:**) davranışını destekler. Üçüncül *işleç*olarak da bilinir. C++ Standardı, üçüncül operandların üç koşuldan birini karşılamasını gerektirir: Operandlar aynı tip ve **const** veya **uçucu** kalifikasyonda (cv-yeterlilik) olmalıdır veya sadece bir operand, diğeri ile aynı tipe ve cv-kalifikasyona açık bir şekilde dönüştürülebilir olmalıdır. Ya da, bir veya her iki operands bir atmak ifade olmalıdır. Visual Studio 2017 sürüm 15.5'ten önceki sürümlerde, derleyici standart tarafından belirsiz kabul edilen dönüşümlere izin verdi.

**/Zc:üçüncül** seçeneği belirtildiğinde, derleyici standarda uygundur. Eşleşen türleri ve ikinci ve üçüncü operands cv-nitelik için kuralları uymayan kodu reddeder.

**/Zc:ternary** seçeneği Visual Studio 2017'de varsayılan olarak kapalıdır. Uygun davranışı etkinleştirmek için **/Zc:ternary'yi** veya önceki uyumsuz derleyici davranışını açıkça belirtmek için **/Zc:ternary'yi** kullanın. [/izin-](permissive-standards-conformance.md) seçeneği dolaylı olarak bu seçeneği sağlar, ancak **/Zc:ternary-**.

### <a name="examples"></a>Örnekler

Bu örnek, hem bir türden açık olmayan başlatma hem de bir türe dönüştürme sağlayan bir sınıfın belirsiz dönüşümlere nasıl yol açabileceğini gösterir. Bu kod varsayılan olarak derleyici tarafından kabul edilir, ancak **/Zc:ternary** veya **/izin-** belirtildiğinde reddedilir.

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

Bu kodu düzeltmek için, tercih edilen ortak türe açık bir döküm yapın veya bir tür dönüştürme yönünü önleyin. Dönüştürmeyi açık hale getirerek derleyicinin tür dönüştürmeyle eşleşmesini engelleyebilirsiniz.

Bu yaygın desen için önemli bir istisna operands türü gibi null-sonlandırılan dize türleri, biri , `const char*`, `const char16_t*`ve benzeri olmasıdır. Ayrıca, dizi türleri ve bozunan işaretçi türleri ile efekti çoğaltabilirsiniz. Gerçek ikinci veya üçüncü operand `?:` karşılık gelen tür bir dize literal olduğunda davranış kullanılan dil standardına bağlıdır. C++17 bu durum için C++14'ten anlamsal olarak değiştirmiştir. Sonuç olarak, derleyici kodu varsayılan **/std:c++14**altında aşağıdaki örnekte kabul eder, ancak **/std:c++17**belirttiğiniz zaman kodu reddeder.

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

Bu kodu düzeltmek için, operands açıkça birini döküm.

**/Zc:ternary**altında, derleyici, bağımsız değişkenlerden birinin tür **geçersiz**olduğu koşullu işleçleri reddeder ve diğeri bir atma ifadesi değildir. Bu desenin ortak kullanımı ASSERT benzeri makrolarda dır:

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

Tipik çözüm, geçersiz olmayan bağımsız değişkeni `void()`.

Bu örnek, hem **/Zc:ternary** hem de **/Zc:ternary altında**hata oluşturan kodu gösterir.

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

Bu kod daha önce bu hatayı verdi:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

**/Zc:ternary**ile, başarısızlığın nedeni daha açık hale gelir. Uygulama tanımlı çağrı kurallarından herhangi biri her lambda oluşturmak için kullanılabilir. Ancak, derleyici olası lambda imzaları ayırt etmek için hiçbir tercih kuralı vardır. Yeni çıktı şu na benzer:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

**/Zc:ternary** tarafından bulunan sorunların yaygın bir kaynağı, şablon meta programlamada kullanılan koşullu işleçlerden gelir. Bu anahtar altında bazı sonuç türleri değişir. Aşağıdaki örnekte, **/Zc:tersiyerin** koşullu ifadenin sonuç türünü meta programlama olmayan bir bağlamda değiştirdiği iki durum gösteriş verilmiştir:

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

Tipik düzeltme, eski `std::remove_reference` davranışı korumak için gereken sonuç türüne bir özellik uygulamaktır.

Visual C++'daki uyumluluk sorunları hakkında daha fazla bilgi için standart [olmayan davranış](../../cpp/nonstandard-behavior.md)konusuna bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **C/C++** > **Komut Satırı** özelliği sayfasını seçin.

1. Ek **Seçenekler** özelliğini **/Zc:ternary** veya **/Zc:ternary-** içerecek şekilde değiştirin ve ardından **Tamam'ı**seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
