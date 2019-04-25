---
title: Yönetilen Türler (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], managed
- managed data types [C++]
- .NET Framework [C++], managed types
- data types [C++], .NET feature access
- main function, in managed applications
- managed code, main() function
- .NET Framework [C++], C++ equivalents
- __nogc type declarations
- __value keyword, issues when nesting
- equality, testing for
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 679b8ed3-d966-4a0c-b627-2a3f3ec96b74
ms.openlocfilehash: b91918d526d83d4cf47436d02b7c67038576bafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152786"
---
# <a name="managed-types-ccli"></a>Yönetilen Türler (C++/CLI)

Visual C++, .NET özellikleri desteklemek için ortak dil çalışma zamanı özellikleri ve avantajları ve kısıtlamaları çalışma zamanının tabidir yönetilen türleri aracılığıyla erişmesini sağlar.

## <a name="main_functions"></a> Yönetilen türler ve main işlevi

Kullanarak bir uygulamayı yazarken **/CLR**, bağımsız değişkenleri **ana()** işlevi, bir yönetilen türü olamaz.

Uygun bir imza örneğidir:

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="dotnet"></a> C++ yerel türlerinin .NET framework eşdeğerleri

Aşağıdaki tabloda diğer adlar önceden tanımlanmış türler yerleşik Visual C++ türler için anahtar sözcükler gösterir, **sistem** ad alanı.

|Visual C++ tür|.NET Framework türü|
|-----------------------|-------------------------|
|**void**|<xref:System.Void?displayProperty=nameWithType>|
|**bool**|<xref:System.Boolean?displayProperty=nameWithType>|
|**İmzalı char** |<xref:System.SByte?displayProperty=nameWithType>|
|**İmzasız char**|<xref:System.Byte?displayProperty=nameWithType>|
|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|
|**kısa** ve **kısa imzalı**|<xref:System.Int16?displayProperty=nameWithType>|
|**İmzasız short**|<xref:System.UInt16?displayProperty=nameWithType>|
|**int**, **signed int**, **uzun**, ve **signed long**|<xref:System.Int32?displayProperty=nameWithType>|
|**işaretsiz int** ve **işaretsiz uzun**|<xref:System.UInt32?displayProperty=nameWithType>|
|**__int64** ve **__int64 imzalı**|<xref:System.Int64?displayProperty=nameWithType>|
|**imzalanmamış __int64**|<xref:System.UInt64?displayProperty=nameWithType>|
|**float**|<xref:System.Single?displayProperty=nameWithType>|
|**çift** ve **uzun çift**|<xref:System.Double?displayProperty=nameWithType>|

İmzalı veya imzasız varsayılan olarak derleyici seçeneği hakkında daha fazla bilgi için **char**, bkz: [/J (varsayılan karakter türü imzasız)](../build/reference/j-default-char-type-is-unsigned.md).

## <a name="version_issues"></a> Yerel türlerin içinde bulunan değer türleri için sürüm sorunları

Bir istemci derlemesi oluşturmak için kullanılan imzalı (tanımlayıcı ad) derleme bileşeni göz önünde bulundurun. Bileşen istemci türü olarak yerel bir birleşim, bir sınıf veya bir dizi üyesi için kullanılan bir değer türü içerir. Bileşenin gelecek bir sürümünde boyutunu veya değer türünün düzeni değişirse istemcinin derlenmelidir.

İle bir keyfile oluşturma [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).

### <a name="example"></a>Örnek

Aşağıdaki örnek bileşendir.

```cpp
// nested_value_types.cpp
// compile with: /clr /LD
using namespace System::Reflection;
[assembly:AssemblyVersion("1.0.0.*"),
assembly:AssemblyKeyFile("mykey.snk")];

public value struct S {
   int i;
   void Test() {
      System::Console::WriteLine("S.i = {0}", i);
   }
};
```

### <a name="example"></a>Örnek

İstemci örnektir:

```cpp
// nested_value_types_2.cpp
// compile with: /clr
#using <nested_value_types.dll>

struct S2 {
   S MyS1, MyS2;
};

int main() {
   S2 MyS2a, MyS2b;
   MyS2a.MyS1.i = 5;
   MyS2a.MyS2.i = 6;
   MyS2b.MyS1.i = 10;
   MyS2b.MyS2.i = 11;

   MyS2a.MyS1.Test();
   MyS2a.MyS2.Test();
   MyS2b.MyS1.Test();
   MyS2b.MyS2.Test();
}
```

### <a name="output"></a>Çıkış

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>Açıklamalar

Ancak, başka bir üyesine eklerseniz `struct S` e içinde (örneğin, `double d;`) ve bileşen, istemci yeniden derlemeye gerek kalmadan yeniden derleyin, işlenmeyen bir özel durum oluşur (tür <xref:System.IO.FileLoadException?displayProperty=fullName>).

## <a name="test_equality"></a> Nasıl Yapılır: Eşitlik için test yapma

Aşağıdaki örnekte, bir eşitlik için test C++ için Yönetilen Uzantılar kullanan ne işleyicilerin başvurduğu temel alır.

### <a name="example"></a>Örnek

```cpp
// mcppv2_equality_test.cpp
// compile with: /clr /LD
using namespace System;

bool Test1() {
   String ^ str1 = "test";
   String ^ str2 = "test";
   return (str1 == str2);
}
```

Bu program için IL dönüş değeri op_Equality çağrısı kullanarak uygulandığını gösterir.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="diagnose_fix"></a> Nasıl Yapılır: Tanılama ve derleme uyumluluk sorunlarını düzeltme

Bu konu, derleme zamanında başvurulan bir derleme sürümünü çalışma zamanında, başvurulan derlemenin sürümü eşleşmediğinde neler olabileceğini açıklar ve sorunu önlemek.

Bir derlemeyi derlendiğinde, diğer derlemelere başvurulabilir `#using` söz dizimi. Bu derlemeler, derleme sırasında derleyici tarafından erişilir. Bu derlemeler bilgilerinden en iyileştirme kararları vermek için kullanılır.

Ancak, başvurulan derleme değiştirildi ve yeniden derlenen ve kendisine bağımlı olan bir başvuru derlemesinin derlemeniz değil, derlemeleri görünmeyebilir hala uyumlu olmayabilir. Geçerli en iyileştirme kararları ilk göre yeni derleme sürümü doğru olmayabilir. Çeşitli çalışma zamanı hataları nedeniyle bu uyumsuzluk oluşabilir. Bu gibi durumlarda üretilecek hiçbir belirli bir özel durum söz konusudur. Çalışma zamanında bildirilen hata yolu üzerinde soruna neden olan bir kod değişikliğinin yapısını bağlıdır.

Uygulamanın tamamı, ürün yayımlanan sürümü için yeniden sürece bu hataları son üretim kodunuzu olası bir sorunu olmamalıdır. Ortak yayımlanan derlemeler bu sorunlardan kaçınılması sağlayacak bir resmi sürüm numarası ile işaretlenmelidir. Daha fazla bilgi için [derleme sürümlendirme](/dotnet/framework/app-domains/assembly-versioning).

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Uyumsuzluk hatasını tanılanıp

1. Çalışma zamanı özel durumları veya başka bir derlemeye başvuran kodda gerçekleşen diğer hata koşulları karşılaşmanız ve başka hiçbir tanımlanan nedene sahipse, eski bir derleme ile ilgili.

1. İlk olarak, yalıtmak ve özel durum ya da diğer hata koşulu yeniden oluşturun. Güncel olmayan bir özel durum nedeniyle ortaya çıkan bir sorun tekrarlanabilir olmalıdır.

1. Uygulamanızda başvurulan herhangi bir derleme zaman damgasını denetleyin.

1. Zaman damgaları tüm başvurulan derlemelerin uygulamanızın son derleme zaman damgası sonraki varsa, uygulamanız güncel değil. Bu meydana gelirse, en son derleme ile uygulamanızı yeniden derlemeniz ve gereken kod değişikliklerini yapın.

1. Uygulamayı yeniden çalıştırın, sorunu yeniden oluşturun ve özel durum oluşmaz doğrulama adımları gerçekleştirin.

### <a name="example"></a>Örnek

Aşağıdaki program, bir yöntemin erişilebilirliği azaltarak ve yeniden derlemeye gerek kalmadan bu yöntem başka bir derlemede erişmeye çalışıyor sorunu gösterir. Derlemeyi deneyin `changeaccess.cpp` ilk. Değiştirecek başvurulan bütünleştirilmiş budur. Ardından derleme `referencing.cpp`. Derleme başarılı olur. Şimdi, çağrılan yöntem erişilebilirliğini azaltın. Derlemeniz `changeaccess.cpp` bayrağıyla `/DCHANGE_ACCESS`. Artık de yasal olarak adlandırılan şekilde korumalı yerine özel, bu yöntem sağlar. Derlemeden `referencing.exe`, uygulamayı yeniden çalıştırın. Bir özel durum <xref:System.MethodAccessException> neden olur.

```cpp
// changeaccess.cpp
// compile with: /clr:safe /LD
// After the initial compilation, add /DCHANGE_ACCESS and rerun
// referencing.exe to introduce an error at runtime. To correct
// the problem, recompile referencing.exe

public ref class Test {
#if defined(CHANGE_ACCESS)
protected:
#else
public:
#endif

  int access_me() {
    return 0;
  }

};
```

```cpp
// referencing.cpp
// compile with: /clr:safe
#using <changeaccess.dll>

// Force the function to be inline, to override the compiler's own
// algorithm.
__forceinline
int CallMethod(Test^ t) {
  // The call is allowed only if access_me is declared public
  return t->access_me();
}

int main() {
  Test^ t = gcnew Test();
  try
  {
    CallMethod(t);
    System::Console::WriteLine("No exception.");
  }
  catch (System::Exception ^ e)
  {
    System::Console::WriteLine("Exception!");
  }
  return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Diğer .NET Dilleri ile Birlikte Çalışabilirlik (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)<br/>
[Yönetilen Türler (C++/CLI)](../dotnet/managed-types-cpp-cli.md)<br/>
[#using yönergesi](../preprocessor/hash-using-directive-cpp.md)
