---
title: /Zc:ternary (Koşullu işleç kurallarını zorla)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 5c38a09b92b4173ca962412a413abc283db590ff
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927503"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (Koşullu işleç kurallarını zorla)

Bir koşullu operatör C++ ifadesinde ikinci ve üçüncü işlenenlerinin türleri ve const veya volatile (CV) niteliği için standart kuralların uygulanmasını etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **/Zc: Üçlü** [ **-** ]

## <a name="remarks"></a>Açıklamalar

Visual Studio 2017 ' den başlayarak, derleyici standart C++ *koşullu işleç* ( **?:** ) davranışını destekler. *Üçlü işleç*olarak da bilinir. C++ Standart üçlü işlenenleri üç koşuldan birini karşılayacak şekilde gerektirir: İşlenenler aynı türde ve **const** ya da **volatile** (MF-nitelik) türünde olmalıdır ya da yalnızca bir işlenen, diğeri ile aynı türe ve CV niteliğine kesin bir şekilde dönüştürülebilir olmalıdır. Ya da, bir veya her iki işlenen de bir throw ifadesi olmalıdır. Visual Studio 2017 sürüm 15,5 ' den önceki sürümlerde, derleyici standart tarafından belirsiz olarak kabul edilen Dönüştürmelere izin verilir.

**/Zc: Üçlü** seçeneği belirtildiğinde, derleyici standarda uygun olur. Bu, eşleşen türler ve ikinci ve üçüncü işlenenlerde CV niteliği için kuralları karşılamayan kodu reddeder.

**/Zc: Üçlü** seçenek, Visual Studio 2017 ' de varsayılan olarak kapalıdır. Uygun davranışı etkinleştirmek için **/Zc: Üçlü** ve önceki bir uyumsuz derleyici davranışını açıkça belirtmek için **/ZC** : Üçlü öğeli kullanın. [/Permissive-](permissive-standards-conformance.md) seçeneği bu seçeneği örtülü olarak sunar, ancak **/Zc: Üçlü-** kullanılarak geçersiz kılınabilir.

### <a name="examples"></a>Örnekler

Bu örnek, bir türden hem açık olmayan başlatma hem de türe dönüştürme sağlayan bir sınıfın, belirsiz Dönüştürmelere neden olabileceği gösterilmektedir. Bu kod, varsayılan olarak derleyici tarafından kabul edilir, ancak **/Zc: Üçlü** veya **/Permissive-** belirtildiğinde reddedilir.

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

Bu ortak model için önemli bir özel durum, işlenen türünün, ve gibi null sonlandırılmış dize türlerinden `const char*` `const char16_t*`biri olduğu durumdur. Ayrıca, dizi türleri ve işaret ettikleri işaretçi türleri ile efekti yeniden oluşturabilirsiniz. ' Ye `?:` gerçek ikinci veya üçüncü işlenen, karşılık gelen türden bir dize sabit değeri olduğunda, kullanılan dil standardına göre değişir. C++ 17, C++ 14 ' ten bu durum için semantiğini değiştirdi. Sonuç olarak, derleyici varsayılan **/std: c++ 14**altında aşağıdaki örnekteki kodu kabul eder, ancak **/std: c++ 17**' i belirttiğinizde bunu reddeder.

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

**/Zc: Üçlü**altında, derleyici bağımsız değişkenlerden birinin **void**türünde olduğu ve diğeri bir throw ifadesi olmadığı koşullu işleçleri reddeder. Bu düzenin yaygın kullanımı, onay benzeri makrolardır:

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

Tipik çözüm, void olmayan bağımsız değişkenini ile `void()`değiştirmek.

Bu örnek, hem **/Zc: Üçlü** hem de **/Zc: Üçlü-** : şeklinde bir hata üreten kodu gösterir.

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

**/Zc: Üçlü**, hatanın nedeni daha açık hale gelir. Her bir Lambda oluşturmak için uygulama tanımlı birkaç çağırma kuralı kullanılabilir. Ancak, derleyicinin olası lambda imzalarını belirsizliğini ortadan kaldırmak için tercih kuralı yoktur. Yeni çıktı şöyle görünür:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

**/Zc: Üçlü** tarafından bulunan yaygın bir sorun kaynağı, şablon meta programlamada kullanılan koşullu işleçlerden gelir. Sonuç türlerinden bazıları bu anahtar altında değişir. Aşağıdaki örnek, **/Zc: Üçlü** olarak bir koşullu ifadenin sonuç türünü meta programlama bağlamında değiştiren iki durumu göstermektedir:

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

Tipik düzeltmeler, sonuç türü üzerinde, `std::remove_reference` eski davranışı korumak için gereken bir nitelik uygulamaktır.

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++/** komut > **satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: Üçlü** veya **/Zc: Üçlü** olarak içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
