---
title: if-else Deyimi (C++)
ms.date: 07/17/2017
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 16aa65ab64d9fd855ae3306da88f8eb14eec759c
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330839"
---
# <a name="if-else-statement-c"></a>if-else Deyimi (C++)

Koşullu dallanmayı denetler. Deyimlerinde *If Bloğu* yalnızca yürütülen *IF ifadesi* bir sıfır olmayan bir değer (veya TRUE) değerlendirir. Varsa değerini *ifade* sıfır değilse, *Deyim1* bloğundaki herhangi bir deyim yürütülür ve else-bloğu, varsa atlanır. Varsa değerini *ifade* sıfırsa, ardından If Bloğu atlanır ve else-bloğu, varsa yürütülür. Sıfır olmayan için değerlendirme ifadeler

- TRUE
- bir null olmayan işaretçi
- sıfır olmayan aritmetik değerdeki, veya
- bir aritmetik, mantıksal değer veya işaretçi belirsiz bir dönüştürmesini tanımlayan bir sınıf adı yazın. (Dönüştürmeler hakkında daha fazla bilgi için bkz. [standart dönüştürmeler](../cpp/standard-conversions.md).)

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

// Visual Studio 2017 version 15.3 and later:
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

// Visual Studio 2017 version 15.3 and later:
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

## <a name="if_with_init"></a> bir başlatıcı with deyimi

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir **varsa** ifadesi bildirir ve adlandırılmış bir değişken başlatır bir ifade içerebilir. If Bloğu kapsamında değişken yalnızca gerektiğinde bu tür bir IF deyimi kullanın.

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

İçindeki tüm biçimlerinin **varsa** deyimi *ifade*, bir yapı dışında herhangi bir değer olan değerlendirilir, tüm yan etkileri de dahil olmak üzere. Denetim geçer **varsa** deyimi programdaki sonraki deyime sürece birini *deyimi*s içeren bir [sonu](../cpp/break-statement-cpp.md), [Devam](../cpp/continue-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md).

**Başka** yan tümcesi bir `if...else` deyimi en yakın ilişkili önceki **varsa** deyimi karşılık gelen sahip değil aynı kapsamda **başka** deyimi.

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr"> constexpr deyimleri

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işlev şablonlarında kullanabilirsiniz bir **, constexpr** deyimi olmadan derleme zamanı dallanma kararları vermek için birden çok işlev aşırı yükleme başvurmadan zorunda. Örneğin, tek bir işlev, (hiçbir sıfır parametresi aşırı yüklemesi gerekli değildir) bu tanıtıcıları parametresi açmak yazabilirsiniz:

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