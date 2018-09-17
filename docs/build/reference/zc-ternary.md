---
title: '/ ZC: ternary (koşullu işleç kurallarını zorla) | Microsoft Docs'
ms.date: 3/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:ternary
dev_langs:
- C++
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
author: corob-msft
ms.author: corob
ms.openlocfilehash: a8cd0a4034b07d170bc9ca531d60cce508681a2a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717829"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/ ZC: ternary (koşullu işleç kurallarını zorla)

Uygulama türleri için C++ Standart kuralları ve koşullu işleç bir ifadede ikinci ve üçüncü işlenenlerin const veya volatile (MS) niteliği etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: ternary**[**-**]

## <a name="remarks"></a>Açıklamalar

Visual Studio sürüm 15.3, C++ Standart koşullu (veya Üçlü) işleç için derleyici desteği sağlar (**?:**) davranışı. C++ standart ya da işlenenler aynı türde ve cv-nitelik veya aynı türde ve diğer cv nitelik dönüştürmelerle dönüştürülebilir olacak şekilde yalnızca tek bir işlenen veya throw ifadesi olması bir veya iki işlenenin olmasını gerektirir. Visual Studio 15.5 sürümünden önce sürümlerinde, derleyici tarafından standart belirsiz olarak kabul edilen Dönüştürmelere izin. Zaman **/ZC: ternary** seçeneği belirtildiğinde, derleyici standardına uygun ve eşleşen türleri ve cv nitelik ikinci ve üçüncü işlenenlerin kurallarını karşılamayan kodu reddeder.

**/ZC: ternary** seçeneği varsayılan olarak kapalıdır. Kullanım **/ZC: ternary** uyumlu davranışı etkinleştirin veya **/Zc:ternary-** açıkça önceki DSCP derleyici davranışını belirtmek için. [/ Permissive-](permissive-standards-conformance.md) seçenek örtük olarak bu seçeneği etkinleştirir, ancak kullanarak kılınabilir **/Zc:ternary-**.

### <a name="examples"></a>Örnekler

Bu örnek, bir tür ve bir türüne dönüştürme açık olmayan iki başlatma sağlayan bir sınıf için belirsiz dönüşümler nasıl açabilir gösterir. Bu kod, derleyici tarafından varsayılan olarak kabul edilir, ancak ne zaman reddedilen **/ZC: ternary** veya **/ permissive-** belirtilir.

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

Gerekli düzeltme, tercih edilen ortak türe açık bir tür dönüştürme yapmak veya bir dönüştürme katılım türü eşleşmenin derleyici arama yönünü dönüştürme açık hale getirerek önlemek için bulunur.

İşlenen türü null ile sonlandırılmış dize türlerinden birini gibi bu yaygın bir düzen için önemli bir özel durum olduğunda `const char*`, `const char16_t*`ve benzeri. Siz de bu dizi türleri ve bunlar için decay işaretçi türleri ile yeniden oluşturabilirsiniz. Davranışı, gerçek ikinci veya üçüncü işleneni?: olan ilgili türden bir dize sabit değeri, kullanılan dil standart bağlıdır. C ++ 17 semantiği bu durum için C ++ 14'olarak değişti. Sonuç olarak, aşağıdaki örnek kodda altında kabul **/Std: c ++ 14** (derleyici) ancak varsayılandır zaman reddedilen **/Std: c ++ 17** belirtilir.

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

Bu kodu düzeltmek için açıkça biri dönüştürün.

Altında **/ZC: ternary**bağımsız değişkenlerden biri olduğu, derleyici reddeder Koşullu işleçler void türü ve diğer bir throw ifadesi değil. Bir ortak bu onay benzeri makrolarda kullanılır:

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

Tipik yalnızca void olmayan bağımsız değişken ile void() değiştirmek çözümdür.

Bu örnek, her ikisi de altında bir hata oluşturur kod gösterir **/ZC: ternary** ve **/Zc:ternary-**:

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

Bu kod, daha önce bu hata verdi:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

İle **/ZC: ternary** başarısızlık nedeni daha anlaşılır olur; burada herhangi bir uygulama tanımlı çeşitli çağırma kuralları kullanılabilen her lambda oluşturulacak mimarilerde derleyici aralarında tercih yok ifade eder. olası lambda imzaların ayırt etmek. Yeni çıkış şöyle görünür:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Sorunların ortak bir kaynak için benimsenmesini ilgili **/ZC: ternary** sonuç türlerinden bazıları bu anahtarı altındaki değiştirme gibi şablon meta programlama, koşullu işlecin kullanımı gelir. Aşağıdaki örnek, iki durumda gösterir. burada **/ZC: ternary** koşullu ifadenin sonuç türü bir meta programlama bağlamındaki değiştirir:

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

Böyle durumlarda normal çözümleme uygulamaktır bir `std::remove_reference` nitelik sonucunda, eski davranışı korumak için gerektiğinde yazın.

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: ternary** veya **/Zc:ternary-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)
