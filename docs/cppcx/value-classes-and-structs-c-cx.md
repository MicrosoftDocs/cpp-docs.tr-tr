---
title: Değer sınıfları ve yapıları (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 226198c35dc0b7e7e1c7fab4ce81fc4782b5ca38
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764208"
---
# <a name="value-classes-and-structs-ccx"></a>Değer sınıfları ve yapıları (C + +/ CX)
A *değeri yapı* veya *değer sınıfının* olduğu bir Windows çalışma zamanı ile uyumlu POD ("düz eski veri yapısı"). Sabit bir boyutu vardır ve yalnızca alanlardan oluşur; başvuru sınıfı, bu özelliğe sahip değil.  
  
 Aşağıdaki örnekler, bildirmek ve değer yapıları başlatmak gösterilmektedir.  
  
```  
  
// in mainpage.xaml.h:  
    value struct TestStruct  
    {  
        Platform::String^ str;  
        int i;  
    };  
  
    value struct TestStruct2  
    {  
        TestStruct ts;  
        Platform::String^ str;  
        int i;  
    };  
  
// in mainpage.cpp:  
    // Initialize a value struct with an int and String  
    TestStruct ts = {"I am a TestStruct", 1};  
  
    // Initialize a value struct that contains  
    // another value struct, an int and a String  
    TestStruct2 ts2 = {{"I am a TestStruct", 1}, "I am a TestStruct2", 2};  
  
    // Initialize value struct members individually.  
    TestStruct ts3;   
    ts3.i = 108;  
    ts3.str = "Another way to init a value struct.";  
  
```  
  
 Başka bir değişkene bir değer türü bir değişkene atandığında, her iki değişkenin kendi veri kopyasını sahip olacak şekilde değeri kopyalanır. A *değeri yapı* , yalnızca genel veri alanları içerir ve kullanılarak bildirilen bir sabit boyutlu yapısıdır `value struct` anahtar sözcüğü.  
  
 A *değer sınıfının* olduğu gibi bir `value struct` dışında kendi alanlarına ortak erişilebilirlik açıkça verilmelidir. Kullanılarak bildirilen `value class` anahtar sözcüğü.  
  
 Değer yapısı veya değer sınıfı yalnızca temel sayısal türler, enum sınıfları, alanlar içerebilir `Platform::String^`, veya [Platform::ıbox \<T > ^](../cppcx/platform-ibox-interface.md) Burada T, bir sayısal tür veya numaralandırmaya sınıfı veya değer sınıfı veya yapı birimi. Bir `IBox<T>^` alan değerine sahip `nullptr`— nasıl kavramı C++'ı uygulayan budur *boş değer atanabilen değer türleri*.  
  
 Bir değer sınıfı veya içeren değeri yapı bir `Platform::String^` veya `IBox<T>^` tür üyesi olmadığından `memcpy`-kullanabilirsiniz.  
  
 Çünkü tüm üyelerinin bir `value class` veya `value struct` ortak olan ve bu meta verilere yayılır, standart C++ türler üyeleri olarak izin verilmez. Bu içerebilir ref sınıflarından farklıdır `private` veya `internal` standart C++ türleri...  
  
 Aşağıdaki kod parçası bildirir `Coordinates` ve `City` türleri olarak değer yapılar. Bildirim, bir `City` veri üyeleri olan bir `GeoCoordinates` türü. A `value struct` diğer değeri Yapı üyeleri olarak içerebilir.  
  
 [!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]  
  
## <a name="parameter-passing-for-value-types"></a>Parametre için değer türleri geçirme  
 Tür bir işlev veya yöntem parametresi bir değer varsa, normalde değere göre geçirilir. Büyük nesneler için bu performans sorunu neden olabilir. Görsel Studio2013 ve önceki sürümlerinde, değer türleri C + +/ CX değer tarafından her zaman geçirildi. Visual Studio 2015 ve sonraki sürümlerinde, değer türleri, başvuru veya değer geçirebilirsiniz.  
  
 Bir değer türü değere göre geçen bir parametre bildirmek için aşağıdaki gibi bir kod kullanın:  
  
```  
void Method1(MyValueType obj);  
```  
  
 Bir değer türü başvuruya göre geçiren bir parametre bildirmek için başvuru simgesini kullanın. (&) aşağıdaki gibi:  
  
```  
void Method2(MyValueType& obj);  
```  
  
 Türü içinde Method2 MyValueType bir başvurudur ve standard C++ içinde bir başvuru türü aynı şekilde çalışır.  
  
 C# gibi başka bir dilden Method1 çağırdığınızda kullanın gerekmez `ref` veya `out` anahtar sözcüğü. Method2 çağırdığınızda kullanabilirsiniz `ref` anahtar sözcüğü.  
  
```  
Method2(ref obj);  
```  
  
 Başvuruya göre bir değer türü geçirmek için bir işaretçi simge (*) de kullanabilirsiniz. Çağıranlar diğer dillerdeki göre davranışı aynıdır (çağıranlar, C# kullanımı `ref` anahtar sözcüğü), ancak yönteminde değer türü işaretçisi türdür.  
  
## <a name="nullable-value-types"></a>Boş değer atanabilen değer türleri  
 Daha önce bahsedildiği gibi bir değer sınıfı veya değer yapı türünde bir alan olabilir [Platform::ıbox\<T > ^](../cppcx/platform-ibox-interface.md)— Örneğin, `IBox<int>^`. Böyle bir alan için geçerli olan herhangi bir sayısal değer olabilir `int` türünü veya değerini olabilir `nullptr`. Parametresi olarak isteğe bağlı olarak bildirilen bir yöntemi için bağımsız değişken olarak boş değer atanabilir bir alan geçirebilir veya başka bir yerde bir değer türü olmayan bir değer olması gerekiyor.  
  
 Aşağıdaki örnek, boş değer atanabilir bir alana sahip bir yapı başlatmaya gösterilmektedir.  
  
```  
public value struct Student  
{  
    Platform::String^ Name;  
    int EnrollmentYear;  
    Platform::IBox<int>^ GraduationYear; // Null if not yet graduated.   
};  
//To create a Student struct, one must populate the nullable type.   
MainPage::MainPage()  
{  
    InitializeComponent();  
  
    Student A;  
    A.Name = "Alice";  
    A.EnrollmentYear = 2008;  
    A.GraduationYear = ref new Platform::Box<int>(2012);  
  
    Student B;  
    B.Name = "Bob";  
    B.EnrollmentYear = 2011;  
    B.GraduationYear = nullptr;  
  
    IsCurrentlyEnrolled(A);  
    IsCurrentlyEnrolled(B);  
}  
bool MainPage::IsCurrentlyEnrolled(Student s)  
{  
    if (s.GraduationYear == nullptr)  
    {  
        return true;  
    }  
    return false;  
}  
  
```  
  
 Değer yapısı burada gösterildiği gibi aynı şekilde, null yapılabilir duruma:  
  
```  
  
public value struct MyStruct  
{  
public:  
    int i;  
    Platform::String^ s;  
};  
  
public ref class MyClass sealed  
{  
public:  
    property Platform::IBox<MyStruct>^ myNullableStruct;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)   
 [Başvuru Sınıfları ve Yapıları (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md)