---
title: Sınıflar, structs ve sendikalar için parantez başlatma
description: Herhangi bir C++ sınıfı, yapı veya birleşim ile ayraç başlatma kullanma
ms.date: 11/19/2019
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 4628ffe8935fc32e86468c631d5d9e9622d63d2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374071"
---
# <a name="brace-initialization"></a>Küme ayracı başlatma

Her zaman bir sınıf için bir oluşturucu tanımlamak için gerekli değildir, özellikle nispeten basit olanlar. Kullanıcılar, aşağıdaki örnekte gösterildiği gibi, tek düzen başlatma kullanarak bir sınıfın veya yapının nesnelerini başlatmayı sağlayabilir:

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

Bir sınıf veya yapı oluşturucu olmadığında, liste öğelerini üyelerin sınıfta beyan edildiği sırada sağladığınıunutmayın. Sınıfın bir oluşturucusu varsa, öğeleri parametreler sırasına göre sağlayın. Bir türde örtülü veya açıkça beyan edilmiş varsayılan bir oluşturucu varsa, varsayılan ayraç başlatma (boş ayraçlarla) kullanabilirsiniz. Örneğin, aşağıdaki sınıf hem varsayılan hem de varsayılan olmayan ayraç başlatma kullanılarak başharflere alınabilir:

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

Bir sınıfın varsayılan olmayan oluşturucuları varsa, sınıf üyelerinin ayraç ilkbenatörde göründüğü sıra, üyelerin (önceki `class_a` örnekte olduğu gibi) bildirilen sıra değil, ilgili parametrelerin oluşturucuda görüntülenme sırasıdır. Aksi takdirde, tür beyan edilen bir oluşturucu yoksa, üyelerin ayraç ilkizerinde görünme sırası, beyan edildikleri sırayla aynıdır; Bu durumda, istediğiniz kadar çok kamu üyesini açabilir, ancak herhangi bir üyeyi atlayamazsınız. Aşağıdaki örnek, bildirilen bir oluşturucu olmadığında ayraç başlatmada kullanılan sırayı gösterir:

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

Varsayılan oluşturucu açıkça beyan edilmiş ancak silinmiş olarak işaretlenmişse, varsayılan ayraç başlatma kullanılamaz:

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

Örneğin, işlev parametresi veya iade değeri veya **yeni** anahtar kelime olarak genellikle başlatma yı yapacağınız her yerde ayraç başlatma yı kullanabilirsiniz:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

**/std:c++17** modunda, boş ayraç başlatma kuralları biraz daha kısıtlayıcıdır. Bkz. [Türemiş oluşturucular ve genişletilmiş toplu başlatma.](constructors-cpp.md#extended_aggregate)

## <a name="initializer_list-constructors"></a>initializer_list yapıcılar

[initializer_list Sınıfı,](../standard-library/initializer-list-class.md) bir oluşturucuve diğer bağlamlarda kullanılabilecek belirli bir türnesnelerin listesini temsil eder. Ayraç başlatmayı kullanarak bir initializer_list oluşturabilirsiniz:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
> Bu sınıfı kullanmak için [ \<initializer_list>](../standard-library/initializer-list.md) üstbilgi eklemeniz gerekir.

Bir `initializer_list` kopyalanabilir. Bu durumda, yeni listenin üyeleri özgün listenin üyelerine başvurur:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

Standart kitaplık kapsayıcı sınıfları `wstring`ve `regex`ayrıca `initializer_list` `string`, , ve , yapıcılar var. Aşağıdaki örnekler, bu oluşturucularla nasıl başlangıç yapılacağını gösterir:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{ 'x', 'y', 'z' };
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Oluşturucular](../cpp/constructors-cpp.md)
