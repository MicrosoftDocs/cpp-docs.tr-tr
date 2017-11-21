---
title: "Kutulama (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: boxing, Visual C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f8d597466204aa17475ee732b77f321464ccc010
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="boxing--c-component-extensions"></a>Kutulama (C++ Bileşen Uzantıları)
Visual C++ derleyicisi değer türleri adlı bir işlem nesneleri dönüştürebilir *kutulama*ve Dönüştür nesneleri değer türleri olarak adlandırılan bir işlemde *kutudan çıkarma*.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 C + +/ CX değer türleri kutulama ve kutudan çıkarma başvuru türleri için toplu değer sözdizimi destekler. Türündeki bir değişkene atandığında bir değer türü Kutulu `Object`. Bir `Object` değişkenidir sarmalanmamış ne zaman bir değer türü değişkene atanır ve parantez içinde belirtilen sarmalanmamış türü; diğer bir deyişle, nesne değişkeni için bir değer türü zaman dönüştürün.  
  
```  
  
  Platform::Object^  
  object_variable  = value_variable;  
value_variable = (value_type) object_variable;  
  
```  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneği kutuları ve sarmadan çıkarır bir `DateTime` değeri. İlk olarak, örnek bir DateTime değişkenine atar ve geçerli tarih ve saati temsil eden bir DateTime değeri alır. Ardından DateTime bir nesne değişkeni atayarak Kutulu. Son olarak, paketlenmiş değer başka bir DateTime değişkene atayarak sarmalanmamış.  
  
 Örneği test etmek için bir BlankApplication projesi oluşturun, BlankPage::OnNavigatedTo() yöntemini değiştirin ve kapanış ayracı ve değişken str1 atamayı kesme noktaları belirtin. Örnek kapanış ayracı ulaştığında str1 inceleyin.  
  
```  
  
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
  
 Daha fazla bilgi için bkz: [kutulama (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh969554.aspx).  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 Visual C++ Derleyici kutuları türleri için değer şimdi <xref:System.Object>.  Değer türleri için dönüştürmek için derleyici tanımlı bir dönüştürme nedeniyle olası <xref:System.Object>.  
  
 Nesneler olarak kabul edilmesi için kutulama ve kutudan çıkarma etkinleştir değer türleri. Struct türleri ve int gibi yerleşik türleri dahil olmak üzere, değer türleri için ve türünden dönüştürülebilir <xref:System.Object>.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Nasıl yapılır: açık şekilde istek paketleme](../dotnet/how-to-explicitly-request-boxing.md)  
  
-   [Nasıl yapılır: değer türleri oluşturmak ve örtük kutulamayı için gcnew kullanma](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)  
  
-   [Nasıl yapılır: Unbox](../dotnet/how-to-unbox.md)  
  
-   [Standart dönüştürmeler ve örtük kutulama](../dotnet/standard-conversions-and-implicit-boxing.md)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek gösterilmektedir nasıl örtük kutulama çalışır.  
  
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
  
 **Çıktı**  
  
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
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)