---
title: Değer Sınıfları ve Yapıları (C++/CX)
ms.date: 12/30/2016
helpviewer_keywords:
- value struct
- value class
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
ms.openlocfilehash: 15d54d139f086ce5bb025aaeab145c71d33903c0
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381603"
---
# <a name="value-classes-and-structs-ccx"></a>Değer Sınıfları ve Yapıları (C++/CX)

*Değer yapısı* veya *değer sınıfı* , Windows çalışma zamanı uyumlu bir pod ("düz eski veri yapısı"). Sabit boyuta sahiptir ve yalnızca alanlardan oluşur; bir başvuru sınıfının aksine, özelliği yoktur.

Aşağıdaki örneklerde değer yapıların nasıl bildirilemeyeceğini ve başlatılacağını gösterilmektedir.

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

Değer türünde bir değişken başka bir değişkene atandığında, bu değer kopyalanır, böylece iki değişkenin her biri kendi verilerinin kopyasına sahip olur. *Değer yapısı* , yalnızca ortak veri alanları içeren ve anahtar sözcüğü kullanılarak bildirildiği sabit boyutlu bir yapıdır **`value struct`** .

*Değer sınıfı* , **`value struct`** alanları açıkça ortak erişilebilirlik olarak verilmelidir. **`value class`** Anahtar sözcüğü kullanılarak bildirilmiştir.

Değer yapısı veya değer sınıfı, alan olarak yalnızca temel sayısal türler, Enum sınıfları, `Platform::String^` veya [Platform:: \<T> ^ ibox](../cppcx/platform-ibox-interface.md) olarak bulunabilir; burada T, bir sayısal tür veya sabit listesi sınıfı ya da değer sınıfı ya da struct. Bir `IBox<T>^` alan bir değere sahip olabilir **`nullptr`** ; Bu, C++ ' ın *null yapılabilir değer türleri* kavramını uyguladığı bir değerdir.

Üye olarak bir veya türü içeren bir değer sınıfı veya değer yapısı `Platform::String^` `IBox<T>^` `memcpy` mümkün değildir.

Tüm üyeleri bir **`value class`** veya ortak olduğundan **`value struct`** ve meta veriye yayıldığından, standart C++ türlerine üye olarak izin verilmez. Bu, **`private`** ya da standart C++ türlerini içerebilen başvuru sınıflarından farklıdır **`internal`** .

Aşağıdaki kod parçası, `Coordinates` ve `City` türlerini değer yapıları olarak bildirir. `City`Veri üyelerinden birinin bir tür olduğuna dikkat edin `GeoCoordinates` . **`value struct`** , Diğer değer yapılarını üye olarak içerebilir.

[!code-cpp[cx_classes#07](../cppcx/codesnippet/CPP/classesstructs/class1.h#07)]

## <a name="parameter-passing-for-value-types"></a>Değer türleri için parametre geçirme

Bir işlev veya yöntem parametresi olarak bir değer türüne sahipseniz, normalde değere göre geçirilir. Daha büyük nesneler için bu bir performans sorununa neden olabilir. Visual Studio 2013 ve önceki sürümlerde, C++/CX içindeki değer türleri her zaman değere göre geçirilir. Visual Studio 2015 ve üzeri sürümlerde, değer türlerini başvuruya veya değere göre geçirebilirsiniz.

Değer türü değere göre geçen bir parametre bildirmek için, aşağıdaki gibi bir kod kullanın:

```cpp
void Method1(MyValueType obj);
```

Başvuruya göre bir değer türü geçiren bir parametre bildirmek için, başvuru sembolünü (&) aşağıdaki gibi kullanın:

```cpp
void Method2(MyValueType& obj);
```

Method2 içindeki tür MyValueType öğesine başvurudur ve standart C++ ' da başvuru türüyle aynı şekilde çalışıyor.

C# gibi başka bir dilden Method1 çağırdığınızda, `ref` veya `out` anahtar sözcüğünü kullanmanız gerekmez. Method2 öğesini çağırdığınızda `ref` anahtar sözcüğünü kullanın.

```
Method2(ref obj);
```

Bir değer türünü başvuruya göre geçirmek için bir işaretçi simgesi (*) de kullanabilirsiniz. Diğer dillerdeki çağıranlara yönelik davranış aynı (C# ' deki çağıranlar `ref` anahtar sözcüğünü kullanır), ancak yönteminde tür, değer türüne yönelik bir işaretçidir.

## <a name="nullable-value-types"></a>Boş değer atanabilen değer türleri

Daha önce belirtildiği gibi, bir Value sınıfı veya value yapısı, [Platform:: \<T> ^ ibox](../cppcx/platform-ibox-interface.md)türünde bir alana sahip olabilir; Örneğin, `IBox<int>^` . Böyle bir alan, türü için geçerli olan herhangi bir sayısal değere sahip olabilir **`int`** veya değeri olabilir **`nullptr`** . Parametre isteğe bağlı olarak bildirildiği bir yönteme veya bir değer türünün bir değere sahip olması gerekmediği başka herhangi bir yerde bağımsız değişken olarak null olabilen bir alan geçirebilirsiniz.

Aşağıdaki örnek, null olabilen bir alanı olan bir yapının nasıl başlatılacağını göstermektedir.

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

Değer yapısının kendisi, burada gösterildiği gibi aynı şekilde null yapılabilir hale getirilebilir:

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
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)<br/>
[Başvuru Sınıfları ve Yapıları (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md)
