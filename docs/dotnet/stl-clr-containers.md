---
title: STL/CLR kapsayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 09/18/2018
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b11cb96e02adbf4b145794d570fde34dbed48ff7
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494341"
---
# <a name="stlclr-containers"></a>STL/CLR Kapsayıcıları

STL/CLR kitaplığı, C++ Standart Kitaplığı'nda benzer bulunur, ancak .NET Framework yönetilen ortamında çalışan kapsayıcılar oluşur. Gerçek C++ Standart kitaplığı ile güncel tutulmasını değil ve eski desteği korunur.

Bu belge kapsayıcılarda STL/CLR kapsayıcı öğeleri, kapsayıcılara ekleyebilirsiniz ve kapsayıcılarında öğeleri sahiplik sorunlarını öğe türleri için gereksinimler gibi genel bir bakış sağlar. Yerel C++ Standart Kitaplığı ve STL/CLR arasındaki farklılıklar uygun yerlerde belirtilmiştir.

## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler

STL/CLR kapsayıcılarına eklenen tüm öğeleri belirli yönergeleri uyulmadığı gerekir. Daha fazla bilgi için [STL/CLR kapsayıcı öğeleri için gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md).

## <a name="valid-container-elements"></a>Geçerli kapsayıcı öğeler

STL/CLR kapsayıcı öğeleri iki türlerinden birini içerebilir:

- Başvuru türleri için işler.

- Başvuru türleri.

- Kutulanmamış değer türleri.

Paketlenmiş değer türleri herhangi bir STL/CLR kapsayıcıları INSERT yapılamıyor.

### <a name="handles-to-reference-types"></a>Başvuru türleri tanıtıcıları

Bir STL/CLR kapsayıcısına bir başvuru türü için bir tanıtıcı ekleyebilirsiniz. Yerel C++'ta bir işaretçi için bir tanıtıcı CLR'yi hedefleyen c++ benzerdir. Daha fazla bilgi için [işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).

#### <a name="example"></a>Örnek

Aşağıdaki örnek bir çalışan nesnesine yönelik bir tanıtıcı nasıl ekleneceğini gösterir. bir [cliext::set](../dotnet/set-stl-clr.md).

```
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

STL/CLR kapsayıcısına bir başvuru türü (bir başvuru türü için bir tanıtıcı yerine) eklemek mümkündür. Burada ana fark başvuru türlerinin bir kapsayıcı silindiğinde, yok edici bu kapsayıcı içindeki tüm öğeler için çağrı yapılmasıdır. Başvuru türleri tanıtıcıları kapsayıcıda bu öğeler için Yıkıcılar çağırılan değil.

#### <a name="example"></a>Örnek

Aşağıdaki örnek bir çalışan nesnesine nasıl ekleneceğini gösterir. bir `cliext::set`.

```
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

Kutulanmamış değer türü bir STL/CLR kapsayıcısına da ekleyebilirsiniz. Kutulanmamış değer türü değişmediğinden bir değer türüdür *Kutulu* içine bir başvuru türü.

Bir değer türü öğesi standart türlerin biri gibi olabilir bir `int`, veya bir kullanıcı tanımlı değer türü gibi olabilir bir `value class`. Daha fazla bilgi için [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)

#### <a name="example"></a>Örnek

Aşağıdaki örnek, bir değer türü sınıf çalışan yaparak ilk örnek değiştirir. Bu değer türü ardından eklendiği bir `cliext::set` ilk örnekte olduğu gibi.

```
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

Bir kapsayıcının içine bir değer türü için bir tanıtıcı eklemeyi denerseniz [derleyici hatası C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) oluşturulur.

### <a name="performance-and-memory-implications"></a>Performans ve bellek etkileri

Tanıtıcıları türleri veya değer türleri kapsayıcı öğesi olarak başvurmak için kullanılıp kullanılmayacağını belirleme konusunda birkaç faktör dikkate almanız gerekir. Değer türleri kullanmaya karar verirseniz, her zaman bir öğeyi bir kapsayıcıya eklenir, öğenin kopyasını yapılan unutmayın. Küçük nesneleri için bu bir sorun olmamalıdır, ancak eklenmiş nesneler büyükse, performans düşebilir. Ayrıca, değer türleri kullanıyorsanız, her kapsayıcı öğenin kendi kopyasını yeterli olacağından bir öğe aynı anda birden çok kapsayıcıda depolamak mümkün değildir.

Bunun yerine, başvuru türleri için tutamaçları kullanmaya karar verirseniz, kapsayıcıda eklendiğinde, öğenin bir kopyasını oluşturmak için gerekli olmadığından performansı artırabilir. Ayrıca, farklı değer türleri ile birden çok kapsayıcıda aynı öğesi var olabilir. Ancak, tanıtıcıları kullanmaya karar verirseniz, tanıtıcı geçerli olduğunu ve başvurduğu nesneyi başka bir programda silinmediğinden emin olmak için ilgileniriz gerekir.

## <a name="ownership-issues-with-containers"></a>Kapsayıcıları sahipliği sorunları

STL/CLR kapsayıcıları değeri semantiği çalışır. Her seferinde bir kapsayıcının içine bir öğe eklemek, o öğenin bir kopyasını eklenir. Başvuru benzeri semantiği almak istiyorsanız, bir tanıtıcı nesnesi yerine bir nesne ekleyebilirsiniz.

Açık bir çağrı ya da yöntemi tanıtıcı nesnelerin bir kapsayıcısını silme tanıtıcıları başvuran nesnelerin bellekten serbest bırakılmaz. Açıkça nesneyi silmek, veya gerekir, çünkü bu nesneler yönetilen yığında bulunurlar atık toplayıcı nesne artık kullanılmakta olduğunu belirledikten sonra belleği boşaltmak izin verin.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
