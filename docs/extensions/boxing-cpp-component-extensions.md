---
title: Kutulama (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- boxing, C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
ms.openlocfilehash: c37d9e67424e8ef5082ac7129956f8577d9c745e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787734"
---
# <a name="boxing--ccli-and-ccx"></a>Kutulama (C + +/ CLI ve C + +/ CX)

Değer türlerinin nesneleri dönüştürme çağrılır *kutulama*, ve değer türleri nesnelerin dönüştürme çağrılır *kutudan çıkarma*.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

C + +/ CX değer türleri kutulama ve kutudan çıkarma başvuru türleri için toplu değer sözdizimi destekler. Türünde bir değişkene atandığında bir değer türü kutulanmaz `Object`. Bir `Object` değişkendir kutulanmamış ne zaman bir değer türü değişkenine atanır ve kutulanmamış türü, parantez içinde belirtilir; diğer bir deyişle, nesne değişkeni için bir değer türü olduğunda cast.

```cpp
  Platform::Object^
  object_variable  = value_variable;
value_variable = (value_type) object_variable;
```

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği kutuları ve sarmadan çıkarır bir `DateTime` değeri. İlk olarak, örnek alır bir `DateTime` değeri geçerli tarih ve saati temsil eder ve buna atayan bir `DateTime` değişkeni. Ardından `DateTime` atayarak o Kutulu bir `Object` değişkeni. Paketlenmiş değer diğerine atayarak son olarak, kutudan `DateTime` değişkeni.

Örnek test etmek için oluşturma bir `BlankApplication` değiştirin, proje `BlankPage::OnNavigatedTo()` yöntemi ve ardından sağ köşeli ayraç ve atama değişkeni için kesme noktaları belirtin `str1`. Örnek sağ köşeli ayraç ulaştığında inceleyin `str1`.

```cpp
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)
{
    using namespace Windows::Globalization::DateTimeFormatting;

    Windows::Foundation::DateTime dt, dtAnother;
    Platform::Object^ obj1;

    Windows::Globalization::Calendar^ c =
        ref new Windows::Globalization::Calendar;
    c->SetToNow();
    dt = c->GetDateTime();
    auto dtf = ref new DateTimeFormatter(
                           YearFormat::Full,
                           MonthFormat::Numeric,
                           DayFormat::Default,
                           DayOfWeekFormat::None);
    String^ str1 = dtf->Format(dt);
    OutputDebugString(str1->Data());
    OutputDebugString(L"\r\n");

    // Box the value type and assign to a reference type.
    obj1 = dt;
    // Unbox the reference type and assign to a value type.
    dtAnother = (Windows::Foundation::DateTime) obj1;

    // Format the DateTime for display.
    String^ str2 = dtf->Format(dtAnother);
    OutputDebugString(str2->Data());
}
```

Daha fazla bilgi için [kutulama (C + +/ CX)](https://msdn.microsoft.com/library/windows/apps/hh969554.aspx).

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Değer türleri için derleyici kutuları <xref:System.Object>. Değer türlerine dönüştürmek için derleyici tarafından tanımlanan bir dönüştürme nedeniyle olası <xref:System.Object>.

Nesne olarak kabul edilmesi için kutulama ve kutudan çıkarma etkinleştir değer türleri. Hem yapı türleri hem de Int gibi yerleşik türler dahil olmak üzere, değer türleri için ve türünden dönüştürülebilir <xref:System.Object>.

Daha fazla bilgi için bkz.:

- [Nasıl yapılır: Açık Şekilde İstek Paketleme](../dotnet/how-to-explicitly-request-boxing.md)

- [Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)

- [Nasıl yapılır: Kutudan Çıkarma](../dotnet/how-to-unbox.md)

- [Standart Dönüştürmeler ve Örtük Kutulama](../dotnet/standard-conversions-and-implicit-boxing.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek gösterildiği nasıl örtük kutulama çalışır.

```cpp
// vcmcppv2_explicit_boxing2.cpp
// compile with: /clr
using namespace System;

ref class A {
public:
   void func(System::Object^ o){Console::WriteLine("in A");}
};

value class V {};

interface struct IFace {
   void func();
};

value class V1 : public IFace {
public:
   virtual void func() {
      Console::WriteLine("Interface function");
   }
};

value struct V2 {
   // conversion operator to System::Object
   static operator System::Object^(V2 v2) {
      Console::WriteLine("operator System::Object^");
      return (V2^)v2;
   }
};

void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}
void func1(V2^){Console::WriteLine("in func1(V2^)");}

void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}

int main() {
   // example 1 simple implicit boxing
   Int32^ bi = 1;
   Console::WriteLine(bi);

   // example 2 calling a member with implicit boxing
   Int32 n = 10;
   Console::WriteLine("xx = {0}", n.ToString());

   // example 3 implicit boxing for function calls
   A^ a = gcnew A;
   a->func(n);

   // example 4 implicit boxing for WriteLine function call
   V v;
   Console::WriteLine("Class {0} passed using implicit boxing", v);
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing

   // example 5 casting to a base with implicit boxing
   V1 v1;
   IFace ^ iface = v1;
   iface->func();

   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching
   V2 v2;
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing
                // Will call void func1(System::Object^);

   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)
}
```

```Output
1

xx = 10

in A

Class V passed using implicit boxing

Class V passed with forced boxing

Interface function

in func1(V2^)

in func2(System::ValueType^)

in func2(System::ValueType^)
```

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)