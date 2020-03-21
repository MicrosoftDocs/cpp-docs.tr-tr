---
title: Sınıflar, yapılar ve birleşimler için küme ayracı başlatma
description: Herhangi bir C++ sınıf, yapı veya birleşim ile ayraç başlatma kullanın
ms.date: 11/19/2019
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 2f04401c7fca417baec09fa3023e14b9b85ea63c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075874"
---
# <a name="brace-initialization"></a>Küme ayracı başlatma

Özellikle görece basit olan bir sınıf için bir Oluşturucu tanımlanması her zaman gerekli değildir. Kullanıcılar, aşağıdaki örnekte gösterildiği gibi Tekdüzen başlatma kullanarak bir sınıfın veya yapının nesnelerini başlatabilir:

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

Bir sınıf veya yapının hiçbir Oluşturucusu yoksa, liste öğelerini üyelerin sınıfta bildirildiği sırada sağlayabileceğinizi unutmayın. Sınıfta bir Oluşturucu varsa, parametreleri parametreler sırasıyla belirtin. Bir türün örtük olarak veya açıkça bildirildiği bir varsayılan Oluşturucusu varsa, varsayılan ayraç başlatma (boş küme ayraçları ile) kullanabilirsiniz. Örneğin, aşağıdaki sınıf hem varsayılan hem de varsayılan olmayan ayraç başlatma kullanılarak başlatılabilir:

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

Bir sınıfta varsayılan olmayan oluşturucular varsa, sınıf üyelerinin küme ayracı içinde görünme sırası, üyelerin bildirildiği sıra (önceki örnekte `class_a` gibi) değil, ilgili parametrelerin oluşturucuda göründüğü sıradır. Aksi halde, türün tanımlı bir Oluşturucusu yoksa, üyelerin küme ayracı başlatıcısında görünme sırası, bildirildiği sırayla aynıdır; Bu durumda, istediğiniz sayıda ortak üyenin başlatılmasını sağlayabilirsiniz, ancak hiçbir üyeyi atlayamazsınız. Aşağıdaki örnek, tanımlı bir Oluşturucu olmadığında küme ayracı başlatma içinde kullanılan sırayı gösterir:

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5{ "string", 'c', 2.0 }; // compiler error
}
```

Varsayılan Oluşturucu açık olarak bildirilirse ancak silinmiş olarak işaretlenmişse, varsayılan küme ayracı başlatma kullanılamaz:

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

Genellikle başlatma yaptığınız her yerde (örneğin, bir işlev parametresi veya dönüş değeri olarak veya **New** anahtar sözcüğü) küme ayracı başlatma kullanabilirsiniz:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

**/Std: c++ 17** modunda, boş küme ayracı başlatması kuralları biraz daha kısıtlayıcıdır. Bkz. [türetilmiş oluşturucular ve genişletilmiş toplu başlatma](constructors-cpp.md#extended_aggregate).

## <a name="initializer_list-constructors"></a>initializer_list oluşturucular

[Initializer_list sınıfı](../standard-library/initializer-list-class.md) , bir oluşturucuda ve diğer bağlamlarda kullanılabilen, belirtilen bir türün nesne listesini temsil eder. Küme ayracı başlatma kullanarak bir initializer_list oluşturabilirsiniz:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  Bu sınıfı kullanmak için, [\<initializer_list >](../standard-library/initializer-list.md) üst bilgisini dahil etmeniz gerekir.

Bir `initializer_list` kopyalanabilir. Bu durumda, yeni listenin üyeleri özgün listenin üyelerine başvurulardır:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Standart Kitaplık kapsayıcı sınıfları ve ayrıca `string`, `wstring`ve `regex`, `initializer_list` oluşturuculara sahiptir. Aşağıdaki örneklerde, bu oluşturucularla küme ayracı başlatmanın nasıl yapılacağı gösterilmektedir:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{ 'x', 'y', 'z' };
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Oluşturucular](../cpp/constructors-cpp.md)
