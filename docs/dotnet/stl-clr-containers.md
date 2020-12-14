---
description: 'Daha fazla bilgi edinin: STL/CLR kapsayıcıları'
title: STL/CLR Kapsayıcıları
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
ms.openlocfilehash: 945533f616abe37763d9963d46d87f02a3c077fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335341"
---
# <a name="stlclr-containers"></a>STL/CLR Kapsayıcıları

STL/CLR kitaplığı, C++ standart kitaplığı 'nda bulunanlarla benzer kapsayıcılardan oluşur, ancak .NET Framework yönetilen ortamında çalışır. Gerçek C++ standart kitaplığı ile güncel tutulmamaktadır ve eski destek için korunur.

Bu belge, STL/CLR 'de kapsayıcı öğelerine yönelik gereksinimler, kapsayıcılara ekleyebileceğiniz öğe türleri ve kapsayıcılardaki öğelerle birlikte sahiplik sorunları gibi kapsayıcılara genel bir bakış sağlar. Uygun olduğunda, yerel C++ standart kitaplığı ve STL/CLR arasındaki farklılıklar bahsedilir.

## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler

STL/CLR kapsayıcılarına yerleştirilen tüm öğelerin belirli kurallara uyması gerekir. Daha fazla bilgi için bkz. [STL/CLR kapsayıcı öğeleri Için gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md).

## <a name="valid-container-elements"></a>Geçerli kapsayıcı öğeleri

STL/CLR kapsayıcıları, iki tür öğeden birini tutabilir:

- Başvuru türlerine yönelik tutamaçlar.

- Başvuru türleri.

- Kutulanmamış değer türleri.

STL/CLR kapsayıcılarından herhangi birine paketlenmiş değer türleri ekleyemezsiniz.

### <a name="handles-to-reference-types"></a>Başvuru türlerine yönelik işleyiciler

Bir STL/CLR kapsayıcısına başvuru türüne bir tanıtıcı ekleyebilirsiniz. C++ ' da CLR 'yi hedefleyen bir tanıtıcı yerel C++ ' daki bir işaretçiye benzer. Daha fazla bilgi için, bkz. [nesne işleci (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md).

#### <a name="example"></a>Örnek

Aşağıdaki örnek, bir çalışan nesnesine bir [clienext:: set](../dotnet/set-stl-clr.md)içine nasıl bir tanıtıcı ekleneceğini gösterir.

```cpp
// cliext_container_valid_reference_handle.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee^ empl1419 = gcnew Employee();
    empl1419->Name = L"Darin Lockert";
    empl1419->EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee^>^ emplSet = gcnew set<Employee^>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="reference-types"></a>Başvuru Türleri

Bir STL/CLR kapsayıcısına bir başvuru türü (başvuru türüne yönelik bir tanıtıcı yerine) eklemek de mümkündür. Buradaki ana fark, bir başvuru türü kapsayıcısı silindiğinde, bu kapsayıcıdaki tüm öğeler için yok edicinin çağırılır. Başvuru türlerine yönelik tanıtıcıların kapsayıcısında, bu öğelerin yıkıcıları çağrılmaz.

#### <a name="example"></a>Örnek

Aşağıdaki örnek, bir çalışan nesnesinin ' a nasıl ekleneceğini gösterir `cliext::set` .

```cpp
// cliext_container_valid_reference.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="unboxed-value-types"></a>Kutulanmamış değer türleri

Bir STL/CLR kapsayıcısına Kutulanmamış değer türü de ekleyebilirsiniz. Kutulanmamış değer türü, başvuru türünde *kutulanmamış* bir değer türüdür.

Bir değer türü öğesi, gibi standart değer türlerinden biri olabilir **`int`** veya gibi Kullanıcı tanımlı bir değer türü olabilir **`value class`** . Daha fazla bilgi için bkz. [sınıflar ve yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)

#### <a name="example"></a>Örnek

Aşağıdaki örnek, çalışan sınıfını bir değer türü yaparak ilk örneği değiştirir. Bu değer türü daha sonra `cliext::set` ilk örnekte olduğu gibi öğesine eklenir.

```cpp
// cliext_container_valid_valuetype.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

value class Employee
{
public:
    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl.EmployeeNumber, empl.Name);
    }

    return 0;
}
```

Bir kapsayıcıya değer türüne bir tanıtıcı eklemeye çalışırsanız, [derleyici hatası C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) oluşturulur.

### <a name="performance-and-memory-implications"></a>Performans ve bellek etkileri

Türlerin veya değer türlerine kapsayıcı öğesi olarak başvurmak için tanıtıcıların kullanılıp kullanılmayacağını belirlerken çeşitli faktörleri göz önünde bulundurmanız gerekir. Değer türlerini kullanmaya karar verirseniz, kapsayıcının bir öğesi her eklendiğinde öğenin bir kopyasının yapıldığını unutmayın. Küçük nesneler için bu bir sorun olmamalıdır, ancak eklenmekte olan nesneler büyükse, performans düşebilir. Ayrıca, değer türlerini kullanıyorsanız, her kapsayıcının kendine ait bir kopyası olduğundan, aynı anda birden fazla kapsayıcıda bir öğe depolamak olanaksızdır.

Bunun yerine, türlere başvuru için işleyiciler kullanmaya karar verirseniz, kapsayıcıya eklendiğinde öğenin bir kopyasını oluşturmak gerekli olmadığından, performans artabilir. Ayrıca, değer türleriyle farklı olarak, birden fazla kapsayıcıda aynı öğe bulunabilir. Ancak, tutamaçları kullanmaya karar verirseniz, tanıtıcının geçerli olduğundan ve başvurduğu nesnenin programın başka bir yerinde silinmediğinden emin olmak için dikkatli olmanız gerekir.

## <a name="ownership-issues-with-containers"></a>Kapsayıcılarla sahiplik sorunları

STL/CLR içindeki kapsayıcılar değer semantiğinin üzerinde çalışır. Bir kapsayıcıya her öğe eklediğinizde, bu öğenin bir kopyası eklenir. Başvuruya benzer anlambilim sağlamak istiyorsanız, nesnenin kendisi yerine bir tanıtıcı ekleyebilirsiniz.

Bir tutamaç nesneleri kapsayıcısının Temizleme veya silme yöntemini çağırdığınızda, tanıtıcıların başvurduğu nesneler bellekten serbest bırakılmaz. Nesneyi açıkça silmeniz gerekir ya da bu nesneler yönetilen yığında bulunduğundan, nesnenin artık kullanılmadığını belirledikten sonra çöp toplayıcısının belleği serbest bırakmaya izin verin.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
