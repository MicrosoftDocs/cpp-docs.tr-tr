---
title: "STL/CLR kapsayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1b8aa8ef5b1425d4aa41b1811dca5ec5d56acd1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-containers"></a>STL/CLR Kapsayıcıları
STL/CLR kitaplığı için C++ Standart Kitaplığı'nda bulunan aynı kapsayıcıları olsa da, .NET Framework yönetilen ortamında çalışır. C++ Standart kitaplığı ile bilginiz varsa, STL/CLR hedef ortak dil çalışma zamanı (CLR) kodunuzu yükseltirken zaten geliştirdik becerileri kullanmaya devam etmek için en iyi yoludur.  
  
 Bu belge kapsayıcıları STL/CLR kapsayıcı öğeleri, kapsayıcılarına ekleyebilir ve sahipliği kapsayıcılarında öğeleri sorunlar öğelerinin türleri için gereksinimler gibi genel bir bakış sağlar. Uygun olan yerlerde, yerel C++ Standart Kitaplığı ve STL/CLR arasındaki farklar anlatılmaktadır.  
  
## <a name="requirements-for-container-elements"></a>Kapsayıcı öğeleri için gereksinimler  
 C++ Standart Kitaplığı kapsayıcılarına eklenen tüm öğeleri belirli yönergeleri uyma gerekir. Daha fazla bilgi için bkz: [STL/CLR kapsayıcı öğeleri için gereksinimler](../dotnet/requirements-for-stl-clr-container-elements.md).  
  
## <a name="valid-container-elements"></a>Geçerli kapsayıcı öğeler  
 STL/CLR kapsayıcı öğeleri iki tür birini içerebilir:  
  
-   Başvuru türleri için işler.  
  
-   Başvuru türleri.  
  
-   Sarmalanmamış değer türleri.  
  
 Paketlenmiş değer türleri STL/CLR kapsayıcıları hiçbirine ekleyemiyor.  
  
### <a name="handles-to-reference-types"></a>Başvuru türleri tanıtıcıları  
 STL/CLR kapsayıcısına bir başvuru türü için bir tanıtıcı ekleyebilirsiniz. Bir tanıtıcı CLR'yi hedefleyen C++'ta, yerel C++'ta bir işaretçi benzerdir. Daha fazla bilgi için bkz: [işlemek nesne işleci (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
#### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir çalışan nesnesine işleyici eklemek gösterilmiştir bir [cliext::set](../dotnet/set-stl-clr.md).  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
 STL/CLR kapsayıcısına bir başvuru türü (bir başvuru türü için bir tanıtıcı yerine) eklemek mümkündür. Ana burada yıkıcı bir kapsayıcı başvurusu türlerinin silindiğinde, bu kapsayıcı içindeki tüm öğeler için çağrıldığından emin farktır. Başvuru türleri işleyicilerine kapsayıcısında bu öğeler için Yıkıcılar çağrılması değil.  
  
#### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir çalışan nesnesine eklemek gösterilmiştir bir `cliext::set`.  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
  
### <a name="unboxed-value-types"></a>Sarmalanmamış değer türleri  
 STL/CLR kapsayıcısına sarmalanmamış değer türü de ekleyebilirsiniz. Sarmalanmamış değer türü değiştirilmediğinden bir değer türüdür *Kutulu* içine bir başvuru türü.  
  
 Değer türü öğesini standart değer türleri gibi biri olabilir bir `int`, veya bir kullanıcı tanımlı bir değer türü gibi bir `value class`. Daha fazla bilgi için bkz: [sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir değer türü sınıf çalışan yaparak ilk örnek değiştirir. Bu değer türü sonra içine eklenen bir `cliext::set` yalnızca ilk örnekte olduğu gibi.  
  
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
  
 Bir kapsayıcıya bir değer türü için bir tanıtıcı eklemeye çalışırsanız [derleyici hatası C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) oluşturulur.  
  
### <a name="performance-and-memory-implications"></a>Performans ve bellek etkileri  
 Tanıtıcıları türleri veya değer türleri kapsayıcı öğeler olarak başvurmak için kullanılıp kullanılmayacağını belirlerken pek çok etken dikkate almanız gerekir. Değer türleri kullanmaya karar verirseniz, öğenin kapsayıcıya eklenen her zaman öğenin bir kopyasını yapıldığını unutmayın. Küçük nesneleri için bu bir sorun olmamalıdır, ancak eklenen nesneleri büyükse, performans düşebilir. Ayrıca, değer türleri kullanıyorsanız, her kapsayıcı öğenin kendi kopyasını gerekir çünkü bir öğe aynı anda birden çok kapsayıcı depolamak mümkün değildir.  
  
 Türleri yerine başvurmak için tanıtıcıları kullanmaya karar verirseniz kapsayıcısında eklendiğinde, öğenin bir kopyasını oluşturmak için gerekli olmadığından performansı artırabilir. Ayrıca, farklı değer türleriyle aynı öğesi birden çok kapsayıcı bulunabilir. Ancak, tanıtıcıları kullanmaya karar verirseniz, tanıtıcı geçerli değil ve başvurduğu nesne başka bir programda silinmediğinden emin olmak için dikkatli olun gerekir.  
  
## <a name="ownership-issues-with-containers"></a>Kapsayıcıları sahipliği sorunları  
 STL/CLR kapsayıcıları değeri semantiği üzerinde çalışır. Bir kapsayıcıya bir öğe eklemek her zaman, o öğenin bir kopyasını eklenir. Başvuru benzeri semantiği almak istiyorsanız, nesnenin kendisini yerine bir nesne için bir tanıtıcı ekleyebilirsiniz.  
  
 Açık bir çağrı ya da erase tanıtıcı nesnelerin kapsayıcı yöntemi işleyiciler başvurmak nesneleri bellekten serbest bırakılmaz. Açıkça nesneyi silmek, veya, çünkü bu nesneler yönetilen yığında bulunurlar nesne artık kullanılmakta olduğunu belirledikten sonra belleği boşaltmak atık toplayıcı izin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)