---
title: if-else Deyimi (C++)
ms.date: 07/20/2019
description: Koşullu dallanmayı denetlemek için içinde C++ If-Else deyimlerini kullanın.
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 0e9de2d39e09e148c7e4f3ea82c3dadb173c2d0c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418470"
---
# <a name="if-else-statement-c"></a>if-else Deyimi (C++)

Koşullu dallanmayı denetler. *IF-Block* içindeki deyimler yalnızca *If-expression* sıfır olmayan BIR değer (veya true) olarak değerlendirilirse yürütülür. *İfadenin* değeri sıfır değilse, *Deyim1* ve bloktaki diğer deyimler yürütülür ve varsa Else-Block atlanır. *İfadenin* değeri sıfırsa, IF-Block atlanır ve varsa Else bloğu yürütülür. Sıfır olmayan şekilde değerlendiren ifadeler

- TRUE
- null olmayan bir işaretçi,
- sıfır olmayan aritmetik değer veya
- aritmetik, Boole veya işaretçi türüne belirsiz bir dönüştürme tanımlayan bir sınıf türü. (Dönüşümler hakkında bilgi için bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md).)

## <a name="syntax"></a>Sözdizimi

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// C++17 - Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>Örnek

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if_with_init"></a>Başlatıcı ile IF deyimleri

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)Ile kullanılabilir): bir **IF** deyimi, adlandırılmış bir değişkeni bildiren ve Başlatan bir ifade de içerebilir. Değişken yalnızca If-Block kapsamında gerektiğinde If-ifadesinin bu formunu kullanın.

## <a name="example"></a>Örnek

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

**IF** deyiminin tüm formlarında, bir yapı dışında herhangi bir değere sahip olabilen *ifade*, tüm yan etkiler dahil değerlendirilir. Denetim, **IF** ifadesinden bir [Break](../cpp/break-statement-cpp.md), [Continue](../cpp/continue-statement-cpp.md)veya [goto](../cpp/goto-statement-cpp.md)içermiyorsa, programdaki Next ifadesine geçer.

Bir `if...else` deyimin **Else** yan tümcesi, aynı kapsamda karşılık gelen bir **Else** deyimi olmayan en yakın önceki **if** deyimi ile ilişkilendirilir.

## <a name="a-nameif_constexpr-if-constexpr-statements"></a>constexpr deyimleri <a name="if_constexpr">

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): işlev şablonlarında, birden fazla işlev aşırı yüküne gerek duymadan derleme zamanı dallanma kararları almak için bir **IF constexpr** ifadesini kullanabilirsiniz. Örneğin, parametre açma işlemi gerçekleştiren tek bir işlev yazabilirsiniz (sıfır parametre aşırı yüklemesi gerekmez):

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[switch Deyimi (C++)](../cpp/switch-statement-cpp.md)