---
title: "Değer sınıflar ve yapılar (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 15fd185e085af9ffe58976b6c2859e905cccff6c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="value-classes-and-structs-ccx"></a>Değer sınıflar ve yapılar (C + +/ CX)
A *değer yapısı* veya *değer sınıfının* Windows çalışma zamanı uyumlu POD ("düz eski veri yapısı"). Sabit bir boyutu vardır ve yalnızca alandan oluşur; ref sınıfın aksine özelliği yok.  
  
 Aşağıdaki örnekler, değer yapılar bildirilip gösterilmektedir.  
  
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
  
 Başka bir değişkene bir değer türünde bir değişken atandığında, böylece her iki değişken veri kendi kopyasına sahip değer kopyalanır. A *değer yapısı* yalnızca ortak veri alanları içeren ve kullanarak bildirilmiş bir sabit boyutlu yapısıdır `value struct` anahtar sözcüğü.  
  
 A *değer sınıfının* tıpkı olan bir `value struct` alanlarını ortak erişilebilirlik açıkça verilmelidir dışında. Kullanarak bildirilmiş `value class` anahtar sözcüğü.  
  
 Bir değer yapı ya da değer sınıfı yalnızca temel sayısal türler, numaralandırma sınıfları alanlar içerebilir `Platform::String^`, veya [Platform::IBox \<T > ^](../cppcx/platform-ibox-interface.md) sayısal ya da enum türü sınıfı veya değer sınıfta veya yapı T olduğu. Bir `IBox<T>^` alan değerine sahip `nullptr`— C++ kavramı nasıl uyguladığını budur *boş değer atanabilen değer türleri*.  
  
 Değer sınıfı ya da içeren değer yapı bir `Platform::String^` veya `IBox<T>^` yazın üyesi olmadığından `memcpy`-kullanabilirsiniz.  
  
 İçin tüm üyeleri bir `value class` veya `value struct` ortak olan ve bu meta verileri yayılan, standart C++ türleri üye olarak izin verilmez. Bu içerebilir ref sınıflardan farklıdır `private` veya `internal` standart C++ türleri...  
  
 Aşağıdaki kod parçası bildirir `Coordinates` ve `City` türleri değer yapılar olarak. Duyuru bir `City` veri üyeleri olan bir `GeoCoordinates` türü. A `value struct` diğer değeri yapılar üye olarak içerebilir.  
  
 [!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]  
  
## <a name="parameter-passing-for-value-types"></a>Parametre için değer türleri geçirme  
 Tür bir işlev veya yöntem parametresi bir değer varsa, normalde değeriyle geçirilir. Büyük nesneler için bu performans sorunu neden olabilir. Visual Studio2013 ve önceki sürümlerinde, değer türleri C + +/ CX değeri her zaman geçirildi. Visual Studio 2015 ve sonraki sürümlerinde, değer türleri başvuruya veya değere göre geçirebilirsiniz.  
  
 Değer türü değeri geçirir bir parametre bildirmek için aşağıdaki gibi bir kod kullanın:  
  
```  
void Method1(MyValueType obj);  
```  
  
 Değer türüne başvuru ile geçirir bir parametre bildirmek için başvuru simgesi kullan (&) aşağıdaki gibi:  
  
```  
void Method2(MyValueType& obj);  
```  
  
 Method2 içinde türü MyValueType başvurusudur ve standart C++'da bir başvuru türü aynı şekilde çalışır.  
  
 C# gibi başka bir dilden Method1 çağırdığınızda kullanmak gerekmez `ref` veya `out` anahtar sözcüğü. Method2 çağırdığınızda, kullanabilirsiniz `ref` anahtar sözcüğü.  
  
```  
Method2(ref obj);  
```  
  
 Başvuruya göre bir değer türü geçirmek için bir işaretçi simge (*) de kullanabilirsiniz. Diğer dillerde arayanlar göre aynı davranıştır (C# kullanımda arayanlar `ref` anahtar sözcüğü), ancak yönteminde tür değer türü için bir işaretçi.  
  
## <a name="nullable-value-types"></a>boş değer atanabilen değer türleri  
 Daha önce belirtildiği gibi bir değer sınıfı ya da değer yapı türünde bir alan olabilir [Platform::IBox\<T > ^](../cppcx/platform-ibox-interface.md)— Örneğin, `IBox<int>^`. Böyle bir alan için geçerli olan herhangi bir sayısal değer sağlayabilirsiniz `int` türü veya değerine sahip olabilir `nullptr`. Parametresi isteğe bağlı olarak bildirilmiş bir yöntemi için bağımsız değişken olarak bir boş değer atanabilir alan geçirebilir veya her yerden başka bir değer türü olmayan bir değer olması gerekiyor.  
  
 Aşağıdaki örnek, boş değer atanabilir bir alana sahip bir yapı başlatılamıyor gösterilmektedir.  
  
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
  
 Değer yapısı aşağıda gösterildiği gibi aynı şekilde, null yapılabilir:  
  
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
 [Sistem türü (C + +/ CX)](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)   
 [Ref sınıflar ve yapılar (C + +/ CX)](../cppcx/ref-classes-and-structs-c-cx.md)