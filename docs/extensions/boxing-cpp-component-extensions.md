---
description: 'Daha fazla bilgi edinin: kutulama (C++/CLı ve C++/CX)'
title: Kutulama (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- boxing, C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
ms.openlocfilehash: b3bdc87d9dea2a5a70344ee032655712af221d59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333749"
---
# <a name="boxing--ccli-and-ccx"></a>Kutulama (C++/CLI ve C++/CX)

Değer türlerinin nesnelerine dönüştürülmesine *kutulama* denir ve nesnelerin değer türlerine dönüştürülmesi, *kutudan* çıkarma olarak adlandırılır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

C++/CX, kutulama değer türleri ve kutudan çıkarma başvuru türleri için bir toplu sözdizimi destekler. Bir değer türü, türünde bir değişkene atandığında paketlenmelidir `Object` . Bir `Object` değişken, bir değer türü değişkenine atandığında ve kutulanmış tür parantez içinde belirtildiğinde (nesne değişkeni bir değer türüne yayınlandığınızda) bir değişken kutulanır.

```cpp
  Platform::Object^
  object_variable  = value_variable;
value_variable = (value_type) object_variable;
```

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örnek kutuları ve bir `DateTime` değeri kaldırır. İlk olarak, örnek `DateTime` geçerli tarih ve saati temsil eden bir değer alır ve onu bir `DateTime` değişkene atar. Ardından, `DateTime` bir değişkenine atayarak kutulanmış olur `Object` . Son olarak, kutulanmış değer başka bir değişkene atanarak kutulanabilir `DateTime` .

Örneği test etmek için bir proje oluşturun `BlankApplication` , `BlankPage::OnNavigatedTo()` yöntemini değiştirin ve sonra sağ köşeli kesme noktaları ve değişkene atama ' yı belirtin `str1` . Örnek, kapanış ayracına ulaştığında, öğesini inceleyin `str1` .

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

Daha fazla bilgi için bkz. [paketleme (C++/CX)](../cppcx/boxing-c-cx.md).

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Derleyici kutularında değer türleri <xref:System.Object> . Bu, değer türlerini dönüştürmek için derleyici tarafından tanımlanan bir dönüştürme nedeniyle mümkündür <xref:System.Object> .

Kutulama ve kutudan çıkarma, değer türlerinin nesne olarak değerlendirilmesini sağlar. Yapı türleri ve int gibi yerleşik türler dahil olmak üzere değer türleri, türüne ve türünden dönüştürülebilir <xref:System.Object> .

Daha fazla bilgi için bkz:

- [Nasıl yapılır: açıkça paketleme Isteği](../dotnet/how-to-explicitly-request-boxing.md)

- [Nasıl yapılır: değer türleri oluşturmak için gcnew kullanma ve örtük kutulamayı kullanma](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)

- [Nasıl yapılır: Kutudan çıkarma](../dotnet/how-to-unbox.md)

- [Standart dönüştürmeler ve Örtük kutulama](../dotnet/standard-conversions-and-implicit-boxing.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, örtük kutulamayı nasıl çalıştığını gösterir.

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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
