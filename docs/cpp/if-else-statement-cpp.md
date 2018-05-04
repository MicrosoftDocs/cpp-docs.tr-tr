---
title: if-else deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else_cpp
- if_cpp
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8de2511096766cc4852c1c612eccb7dc65713218
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="if-else-statement-c"></a>if-else Deyimi (C++)
Koşullu dallanmayı denetler. Deyimlerinde *IF blok* yalnızca yürütülen *if ifadesi* sıfır olmayan bir değer olarak değerlendirilir (veya `true`). Varsa değerini *ifade* sıfır olmayan, olan *statement1* ve diğer ifadeleri blok içinde yürütülür ve başka blok, varsa, atlanır. Varsa değerini *ifade* sıfır sonra IF blok atlanır ve başka blok, varsa, yürütülür. Sıfır olmayan olarak değerlendirmek ifadeler
- `true`
- bir null olmayan işaretçi
- Tüm sıfır aritmetik değeri veya 
- bir aritmetik, Boole veya işaretçi anlaşılır bir dönüştürme tanımlayan bir sınıf adı yazın. (Dönüştürme hakkında daha fazla bilgi için bkz: [standart dönüşümler](../cpp/standard-conversions.md).)   
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
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
```  
// if_else_statement.cpp  
#include <iostream>

using namespace std;

class C
{
    public:
    void do_somthing(){}
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
## <a name="if-statement-with-an-initializer"></a>varsa bir başlatıcı with deyimi
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir **varsa** deyimi bildirir ve adlandırılmış bir değişkenini ifade da içerebilir. Eğer blok kapsamında değişken yalnızca gerektiğinde if deyimi, bu formu kullanın. 

```cpp
## Example  
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

 Tüm formlarda **varsa** deyimi, *ifade*, bir yapı dışındaki herhangi bir değer olan değerlendirildiği, tüm yan etkileri dahil olmak üzere. Denetim geçirir **varsa** program sonraki deyiminde ifadesine sürece birini *deyimi*s içeren bir [sonu](../cpp/break-statement-cpp.md), [Devam](../cpp/continue-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md).  
  
 **Başka** yan tümcesinde bir `if...else` deyimi, en yakın ile ilişkilendirilmiş önceki **varsa** karşılık gelen sahip değil aynı kapsamda deyimi **başka** deyimi.   

## <a name="constexpr-if-statements"></a>constexpr varsa deyimleri
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işlevi şablonlarında kullanabileceğiniz bir **constexpr varsa** olmadan derleme zamanı dallanma kararlar almak için deyimi için birden fazla işlev aşırı yüklemelerinin çözümlemelere zorunda. Örneğin, tek bir işlevi bu tanıtıcıları parametre (hiçbir sıfır parametresi aşırı yüklemesi gerekli değildir) paketi açılırken yazabilirsiniz: 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   constexpr if (sizeof...(r)) 
   {
      
      f(r...); 
   }
   else
   {
       g(r...);
   }
}
```

  
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [switch Deyimi (C++)](../cpp/switch-statement-cpp.md)