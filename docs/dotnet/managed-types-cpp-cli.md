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
ms.openlocfilehash: c542151bda780e5306db35049d988e6514fffd62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225611"
---
# <a name="managed-types-ccli"></a>Yönetilen Türler (C++/CLI)

Visual C++, ortak dil çalışma zamanının özelliklerine yönelik destek sağlayan ve çalışma zamanının avantajları ve kısıtlamalarına tabi olan yönetilen türler aracılığıyla .NET özelliklerine erişim sağlar.

## <a name="managed-types-and-the-main-function"></a><a name="main_functions"></a>Yönetilen türler ve Main Işlevi

Kullanarak bir uygulama yazarken **`/clr`** , **Main ()** işlevinin bağımsız değişkenleri yönetilen bir tür olamaz.

Doğru imzaya bir örnek:

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="net-framework-equivalents-to-c-native-types"></a><a name="dotnet"></a>C++ yerel türlerine .NET Framework eşdeğerleri

Aşağıdaki tabloda, **sistem** ad alanında önceden tanımlanmış türlerin diğer adları olan yerleşik Visual C++ türleri için anahtar sözcükler gösterilmektedir.

|Visual C++ türü|.NET Framework türü|
|-----------------------|-------------------------|
|**`void`**|<xref:System.Void?displayProperty=nameWithType>|
|**`bool`**|<xref:System.Boolean?displayProperty=nameWithType>|
|**`signed char`** |<xref:System.SByte?displayProperty=nameWithType>|
|**`unsigned char`**|<xref:System.Byte?displayProperty=nameWithType>|
|**`wchar_t`**|<xref:System.Char?displayProperty=nameWithType>|
|**`short`**'**`signed short`**|<xref:System.Int16?displayProperty=nameWithType>|
|**`unsigned short`**|<xref:System.UInt16?displayProperty=nameWithType>|
|**`int`**, **`signed int`** , **`long`** ve**`signed long`**|<xref:System.Int32?displayProperty=nameWithType>|
|**`unsigned int`**'**`unsigned long`**|<xref:System.UInt32?displayProperty=nameWithType>|
|**`__int64`**'**`signed __int64`**|<xref:System.Int64?displayProperty=nameWithType>|
|**`unsigned __int64`**|<xref:System.UInt64?displayProperty=nameWithType>|
|**`float`**|<xref:System.Single?displayProperty=nameWithType>|
|**`double`**'**`long double`**|<xref:System.Double?displayProperty=nameWithType>|

Veya için varsayılan olarak derleyici seçeneği hakkında daha fazla bilgi **`signed char`** için **`unsigned char`** , bkz. [ `/J` (varsayılan **`char`** tür: **`unsigned`** )](../build/reference/j-default-char-type-is-unsigned.md).

## <a name="version-issues-for-value-types-nested-in-native-types"></a><a name="version_issues"></a>Yerel türlerde Iç Içe geçmiş değer türleri için sürüm sorunları

İstemci derlemesi oluşturmak için kullanılan imzalanmış (tanımlayıcı ad) bir derleme bileşeni düşünün. Bileşen, bir yerel birleşim, sınıf veya dizi üyesinin türü olarak istemcisinde kullanılan bir değer türü içerir. Bileşenin gelecek bir sürümü değer türünün boyutunu veya yerleşimini değiştirirse, istemcinin yeniden derlenmesi gerekir.

[sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) () ile bir keyfile oluşturun `sn -k mykey.snk` .

### <a name="example"></a>Örnek

Aşağıdaki örnek bileşen örneğidir.

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

Bu örnek istemcdir:

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

### <a name="output"></a>Çıktı

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>Yorumlar

Ancak, `struct S` nested_value_types. cpp içine başka bir üye eklerseniz (örneğin, `double d;` ) ve istemciyi yeniden derlemeden bileşeni yeniden derliyorsanız, sonuç işlenmeyen bir özel durumdur (türünde <xref:System.IO.FileLoadException?displayProperty=fullName> ).

## <a name="how-to-test-for-equality"></a><a name="test_equality"></a>Nasıl yapılır: eşitlik için test etme

Aşağıdaki örnekte, C++ için Yönetilen Uzantılar kullanan bir eşitlik testi, tutamaçların neye başvurabileceği üzerine dayalıdır.

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

Bu programın Il değeri, dönüş değerinin op_Equality çağrısı kullanılarak uygulandığını gösterir.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="how-to-diagnose-and-fix-assembly-compatibility-problems"></a><a name="diagnose_fix"></a>Nasıl yapılır: derleme uyumluluk sorunlarını tanılama ve çözme

Bu konuda, derleme zamanında başvurulan bir derlemenin sürümü çalışma zamanında başvurulan derlemenin sürümü ile eşleşmediği ve bu sorundan kaçınmak için neler gerçekleşebileceği açıklanmaktadır.

Bir derleme derlendiğinde, diğer derlemelere `#using` söz dizimi ile başvurulabilir. Derleme sırasında, bu derlemelere derleyici tarafından erişilir. Bu derlemelerdeki bilgiler en iyi duruma getirme kararları almak için kullanılır.

Ancak, başvurulan derleme değiştirilirse ve yeniden derlenir ve buna bağımlı olan başvuran derlemeyi yeniden derlemeseniz, derlemeler hala uyumlu olmayabilir. İlk başta geçerli olan iyileştirme kararları, yeni derleme sürümüne göre doğru olmayabilir. Bu uyumsuzluklar nedeniyle çeşitli çalışma zamanı hataları oluşabilir. Böyle durumlarda üretilecek özel bir özel durum yoktur. Çalışma zamanında hatanın bildirilme yöntemi, soruna neden olan kod değişikliğinin yapısına bağlıdır.

Bu hatalar, ürününüzün yayınlanan sürümü için tüm uygulamanın yeniden oluşturulması koşuluyla, son üretim kodunuzda bir sorun olmaması gerekir. Herkese açık olan derlemeler resmi sürüm numarasıyla işaretlenmelidir, bu da bu sorunların önlendiğinden emin olur. Daha fazla bilgi için bkz. [derleme sürümü oluşturma](/dotnet/framework/app-domains/assembly-versioning).

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Uyumsuzluk hatasını tanılama ve düzeltme

1. Çalışma zamanı özel durumları ya da başka bir derlemeye başvuran kodda oluşan diğer hata koşullarıyla karşılaşırsanız ve başka bir nedenle, bir güncel derleme ile ilgilenmiş olabilirsiniz.

1. İlk olarak, özel durumu veya diğer hata koşulunu yalıtın ve yeniden oluşturun. Eski bir özel durum nedeniyle oluşan bir sorun tekrarlanabilir olmalıdır.

1. Uygulamanızda başvurulan derlemelerin zaman damgasını denetleyin.

1. Başvurulan derlemelerin herhangi bir zaman damgası, uygulamanızın son derleme zaman damgasından daha sonra ise, uygulamanız güncel değildir. Bu durumda, uygulamanızı en son derlemeden yeniden derleyin ve tüm kod değişikliklerini gerekli yapın.

1. Uygulamayı yeniden çalıştırın, sorunu yeniden oluşturmak için gereken adımları gerçekleştirin ve özel durumun gerçekleşmediğinden emin olun.

### <a name="example"></a>Örnek

Aşağıdaki program, bir yöntemin erişilebilirliğini azaltarak ve başka bir derlemede bu yönteme yeniden derleme olmadan erişmeye çalışırken sorunu gösterir. Önce derlemeyi deneyin `changeaccess.cpp` . Bu, değiştirilecek olan Başvurulmuş derlemedir. Ardından derleyin `referencing.cpp` . Derleme başarılı oldu. Şimdi çağrılan metodun erişilebilirliğini azaltın. Bayrağıyla yeniden derleyin `changeaccess.cpp` `/DCHANGE_ACCESS` . Bu, yöntemi özel yerine korumalı hale getirir, böylece daha uzun bir şekilde çağrılabilir. Yeniden derleme yapmadan `referencing.exe` uygulamayı yeniden çalıştırın. Bir özel durum <xref:System.MethodAccessException> ortaya kalır.

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
