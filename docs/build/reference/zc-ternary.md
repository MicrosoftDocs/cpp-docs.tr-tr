---
title: "/ZC:ternary (koşullu işleç kuralları zorla) | Microsoft Docs"
ms.date: 3/06/2018
ms.technology:
- cpp-tools
ms.topic: article
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
manager: ghogen
ms.openlocfilehash: 198da679e9d0d7bd58e034ca9c04c3102748af20
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/ZC:ternary (koşullu işleç kuralları zorla)

Uygulama türleri için C++ standart kurallar ve bir koşullu işleç ifadesinde ikinci ve üçüncü işlenenler const veya volatile (MS) nitelikleri etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>Açıklamalar

Visual Studio sürümü 15.3 tanır C++ Standart koşullu (veya Üçlü) işleç için derleyici desteği (**?:**) davranışı. C++ Standart aynı türde ve MS-niteliğe veya aynı türde ve MS-nitelik halinde diğer belirsizliğe dönüştürülebilir olması yalnızca bir işlenen için veya bir throw deyimi olması bir veya iki işlenenler için iki işlenen gerekiyor. Visual Studio sürüm 15,5 önce sürümlerde, derleyici standardına göre belirsiz olarak kabul edilir dönüşümleri izin. Zaman **/Zc:ternary** seçeneği belirtildiğinde, derleyici standardına uygun ve eşleşen türleri ve MS-nitelikleri ikinci ve üçüncü işlenenler için kuralları karşılamadığı kod reddeder.

**/Zc:ternary** seçeneği varsayılan olarak kapalıdır. Kullanım **/Zc:ternary** uyumlu davranışını etkinleştirmek için veya **/Zc:ternary-** önceki uyumsuz derleyici davranışı açıkça belirtmek için. [/ İzin veren-](permissive-standards-conformance.md) seçenek, bu seçenek örtük olarak etkinleştirir, ancak kullanarak kılınabilir **/Zc:ternary-**.

### <a name="examples"></a>Örnekler

Bu örnekte, her iki açık olmayan başlatma türü ve bir türe dönüştürme sağlayan bir sınıf belirsiz dönüşümler nasıl açabilir gösterilmektedir. Bu kod derleyici tarafından varsayılan olarak kabul edilir, ancak ne zaman reddedilen **/Zc:ternary** veya **/ izin veren-** belirtilir.

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

Gerekli düzeltme, açık bir atama için tercih edilen ortak türü olun ya da bir tür eşlemesi için derleyici arama katılım dönüştürme yönünü dönüştürme açık hale getirerek engellemek için bulunur.

İşlenen türü null ile sonlandırılmış dize türlerinden birini gibi yaygın olarak kullanılan bu deseni önemli bir özel durum olduğunda `const char*`, `const char16_t*`ve benzeri. Siz de bu dizi türleri ve bunlar için decay işaretçi türleri ile yeniden oluşturabilirsiniz. Davranışı zaman gerçek ikinci ya da üçüncü işleneni?: olan bir dize hazır değer karşılık gelen türünde kullanılan dil standart bağlıdır. C ++ 17 bu durumda anlamları C ++ 14'değişti. Sonuç olarak, aşağıdaki örnek kodda altında kabul **/Std: c ++ 14** (derleyici) ancak varsayılandır ne zaman reddedilen **/Std: c ++ 17** belirtilir.

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

Bu kod düzeltmek için açıkça işlenen birini dönüştürün.

Altında **/Zc:ternary**, bağımsız değişkenlerden biri olduğu, derleyici reddeder Koşullu işleçler void yazın ve diğer bir throw ifadesi değil. ASSERT benzeri makroları bu yaygın bir kullanımdır.:

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

Tipik çözüm, void() ile void olmayan bağımsız değişken yalnızca değiştirmektir.

Bu örnek, her ikisi de altında bir hata oluşturur kodu göstermektedir **/Zc:ternary** ve **/Zc:ternary-**:

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

İle **/Zc:ternary** başarısızlık nedeni daha anlaşılır hale; burada herhangi bir uygulama tanımlı birkaç çağırma kurallarını kullanılabilirdi her lambda oluşturmak için mimarileri üzerinde derleyici aralarında tercih ifade eder. Bu olası lambda imzaları belirsizliğini ortadan kaldırmak. Yeni çıktı şu şekildedir:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Ortak bir kaynaktan sorunları benimsenmesi için ilgili **/Zc:ternary** sonuç türlerinden bazıları bu anahtarı altındaki değiştikçe şablon meta programlama koşullu işlecinde kullanımını alanından gelir. Aşağıdaki örnek, iki durumda gösterir nerede **/Zc:ternary** bir koşullu ifade 's sonuç türü meta programlama bağlamda değiştirir:

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

Bu gibi durumlarda tipik çözümleme uygulamaktır bir `std::remove_reference` ayırdedici nitelik sonucu üzerinde eski davranışı korumak için gerektiğinde yazın.

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:ternary** veya **/Zc:ternary-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)  
