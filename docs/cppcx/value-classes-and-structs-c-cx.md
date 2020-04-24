---
title: Değer Sınıfları ve Yapıları (C++/CX)
ms.date: 12/30/2016
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
ms.openlocfilehash: 4a4897f0a3b5c95ffb58e5c9666a2d764d71b3ec
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752901"
---
# <a name="value-classes-and-structs-ccx"></a>Değer Sınıfları ve Yapıları (C++/CX)

*Değer yapısı* veya *değer sınıfı,* Windows Runtime uyumlu bir POD'dur ("düz eski veri yapısı"). Sabit bir büyüklüğe sahiptir ve yalnızca alanlardan oluşur; bir ref sınıfının aksine, hiçbir özelliği vardır.

Aşağıdaki örnekler, değer yapılarını nasıl beyan edip başharflere göre göstereceğimizdir.

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

Değer türünden bir değişken başka bir değişkene atandığında, değer kopyalanır, böylece iki değişkenin her biri kendi veri kopyasına sahip olur. *Değer yapısı,* yalnızca genel veri alanlarını içeren ve `value struct` anahtar sözcük kullanılarak bildirilen sabit boyutlu bir yapıdır.

*Değer sınıfı,* alanlarının `value struct` açıkça ortak erişilebilirlik verilmesi dışında bir değer dir. `value class` Anahtar kelime kullanılarak bildirilir.

Bir değer struct veya değer sınıfı alanlar olarak yalnızca temel sayısal `Platform::String^`türleri, enum sınıfları veya [Platform::IBox \<T>^](../cppcx/platform-ibox-interface.md) T'nin sayısal bir tür veya enum sınıfı veya değer sınıfı veya yapı olduğu durumlarda içerebilir. Bir `IBox<T>^` alanın bir değeri `nullptr`olabilir —bu C++'ın *nullable değer türleri*kavramını nasıl uyguladığıdır.

Üye olarak a veya tür içeren `Platform::String^` `IBox<T>^` bir değer sınıfı `memcpy`veya değer struct mümkün değildir.

A'nın `value class` tüm `value struct` üyeleri veya ortak oldukları ve meta verilere yayıldığı için, standart C++ türlerine üye olarak izin verilmez. Bu, `internal` c++ türleri veya `private` standart c++ türleri içerebilecek ref sınıflarından farklıdır...

Aşağıdaki kod parçası değer `Coordinates` `City` structs olarak bildirir ve türleri. Veri üyelerinden birinin `City` bir `GeoCoordinates` tür olduğuna dikkat edin. A, `value struct` üye olarak diğer değer yapılarını içerebilir.

[!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]

## <a name="parameter-passing-for-value-types"></a>Değer türleri için parametre geçişi

İşlev veya yöntem parametresi olarak bir değer türünüz varsa, normalde değertarafından geçirilir. Daha büyük nesneler için bu bir performans sorununa neden olabilir. Visual Studio2013 ve önceki yıllarda, C++/CX'teki değer türleri her zaman değere göre geçirilmiştir. Visual Studio 2015 ve sonraki durumlarda, değer türlerini referansa veya değere göre geçirebilirsiniz.

Değer türünden geçen bir parametreyi bildirmek için aşağıdaki gibi kod kullanın:

```cpp
void Method1(MyValueType obj);
```

Referans alabilen bir parametreyi bildirmek için, aşağıdaki gibi başvuru simgesini (&) kullanın:

```cpp
void Method2(MyValueType& obj);
```

Method2'nin içindeki tür MyValueType'a bir başvurudur ve standart C++'daki bir başvuru türüyle aynı şekilde çalışır.

Yöntem1'i C# gibi başka bir dilden aradiğinizde, `ref` `out` bu dili veya anahtar sözcüğü kullanmanız gerekmez. Method2'yi aradiğinizde, `ref` anahtar kelimeyi kullanın.

```
Method2(ref obj);
```

Referans alabilen bir değer türünü geçmek için bir işaretçi simgesi (*) de kullanabilirsiniz. Diğer dillerdeki arayanlarla ilgili davranış aynıdır (C# arayanlar `ref` anahtar sözcüğü kullanır), ancak yöntemde, tür değer türüne işaretçidir.

## <a name="nullable-value-types"></a>Boş değer atanabilen değer türleri

Daha önce de belirtildiği gibi, bir değer sınıfı veya değer struct türü Platform bir alan [olabilir::IBox\<T>^](../cppcx/platform-ibox-interface.md)—örneğin, `IBox<int>^`. Böyle bir alan `int` türü için geçerli olan herhangi bir sayısal değere sahip `nullptr`olabilir veya .'nin değeri ne olabilir? Geçersiz bir alanı bağımsız değişken olarak, parametresi isteğe bağlı olarak bildirilen bir yönteme veya değer türünün bir değere sahip olması için gerekli olmadığı başka bir yere geçirebilirsiniz.

Aşağıdaki örnek, boşalan bir alana sahip bir yapının nasıl başlatıldığını gösterir.

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

Bir değer struct kendisi burada gösterildiği gibi, aynı şekilde geçersiz kılınabilir:

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

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)<br/>
[Başvuru Sınıfları ve Yapıları (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md)
