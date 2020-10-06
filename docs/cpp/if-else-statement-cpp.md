---
title: if-else deyimleri (C++)
description: Koşullu dallanmayı denetlemek için If-Else, If-Else ve If-constexpr deyimlerini kullanın.
ms.date: 10/02/2020
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 20d828bf00a79687fe0a9fffbeb1a9cc56fae08c
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765303"
---
# <a name="if-else-statement-c"></a>if-else deyimleri (C++)

İf-else deyimleri koşullu dallanmayı denetler. İçindeki deyimler *`if-branch`* yalnızca *`condition`* sıfır olmayan bir değer (veya) olarak değerlendirilirse yürütülür **`true`** . Değeri *`condition`* sıfır değilse, aşağıdaki ifade yürütülür ve isteğe bağlı olarak aşağıdaki ifade **`else`** atlanır. Aksi takdirde, aşağıdaki ifade atlanır ve **`else`** sonra, bir sonraki ifadesinin **`else`** yürütülmesi durumunda yürütülür.

*`condition`* sıfır olmayan olarak değerlendiren ifadeler şunlardır:

- **`true`**
- null olmayan bir işaretçi,
- sıfır olmayan aritmetik değer veya
- aritmetik, Boole veya işaretçi türüne belirsiz bir dönüştürme tanımlayan bir sınıf türü. (Dönüşümler hakkında bilgi için bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md).)

## <a name="syntax"></a>Sözdizimi

*`init-statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`simple-declaration`*

*`condition`*:\
&emsp; *`expression`*\
&emsp;*`attribute-specifier-seq`* <sub>*opt*</sub> *`decl-specifier-seq`* opt *`declarator`**`brace-or-equal-initializer`*

*`statement`*:\
&emsp; *`expression-statement`*\
&emsp; *`compound-statement`*

*`expression-statement`*:\
&emsp;*`expression`* <sub>*opt*</sub>**`;`**

*`compound-statement`*:\
&emsp;**`{`** *`statement-seq`* <sub>*opt*</sub>**`}`**

*`statement-seq`*:\
&emsp; *`statement`*\
&emsp; *`statement-seq`* *`statement`*

*`if-branch`*:\
&emsp; *`statement`*

*`else-branch`*:\
&emsp; *`statement`*

*`selection-statement`*:\
&emsp;**`if`** **`constexpr`** <sub>*opt*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`***`if-branch`*\
&emsp;**`if`** **`constexpr`** <sub>*opt*</sub><sup>17</sup> **`(`** *`init-statement`* <sub>*opt*</sub><sup>17</sup> 17 *`condition`* **`)`** *`if-branch`* **`else`***`else-branch`*

<sup>17</sup> bu isteğe bağlı öğe, c++ 17 ' den başlayarak kullanılabilir.

## <a name="if-else-statements"></a>if-else deyimleri

Tüm **`if`** *`condition`* yan etkileri de dahil olmak üzere bir yapı dışında herhangi bir değere sahip olabilen tüm deyimin tüm formlarında değerlendirilir. Denetim, **`if`** yürütülene *`if-branch`* veya *`else-branch`* bir [`break`](../cpp/break-statement-cpp.md) , veya içermiyorsa, ' [`continue`](../cpp/continue-statement-cpp.md) den programdaki sonraki deyime geçer [`goto`](../cpp/goto-statement-cpp.md) .

**`else`** Bir deyimin yan tümcesi, `if...else` **`if`** karşılık gelen bir bildirime sahip olmayan aynı kapsamdaki en yakın Previous ifadesiyle ilişkilendirilir **`else`** .

### <a name="example"></a>Örnek

Bu örnek kod **`if`** , birlikte ve olmadan kullanılan çeşitli deyimleri gösterir **`else`** :

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

## <a name="if-statement-with-an-initializer"></a><a name="if_with_init"></a> Başlatıcı ile IF deyimleri

C++ 17 ' den başlayarak bir **`if`** deyim, *`init-statement`* adlandırılmış bir değişkeni bildiren ve Başlatan bir ifade içerebilir. Değişken yalnızca if-deyimin kapsamında gerektiğinde If-ifadesinin bu biçimini kullanın. **Microsoft 'a özgü**: Bu form, Visual Studio 2017 sürüm 15,3 ' den başlayarak kullanılabilir ve en azından [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği gerektirir.

### <a name="example"></a>Örnek

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

## <a name="a-nameif_constexpr-if-constexpr-statements"></a><a name="if_constexpr"> Eğer constexpr deyimleri

C++ 17 ' den başlayarak, **`if constexpr`** birden fazla işlev aşırı yüküne gerek duymadan derleme zamanı dallanma kararları almak için işlev şablonlarındaki bir ifadeyi kullanabilirsiniz. **Microsoft 'a özgü**: Bu form, Visual Studio 2017 sürüm 15,3 ' den başlayarak kullanılabilir ve en azından [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği gerektirir.

### <a name="example"></a>Örnek

Bu örnek, parametre açma işlemi gerçekleştiren tek bir işlevi nasıl yazacağınızı gösterir. Sıfır parametre aşırı yüklemesi gerekli değildir:

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

[Seçim deyimleri](../cpp/selection-statements-cpp.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[`switch` İfade (C++)](../cpp/switch-statement-cpp.md)
