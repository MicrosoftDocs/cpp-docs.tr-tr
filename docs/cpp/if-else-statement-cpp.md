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
ms.openlocfilehash: 15748249a39813edc4446fa25511d20361b0706c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405116"
---
# <a name="if-else-statement-c"></a>if-else Deyimi (C++)
Koşullu dallanmayı denetler. Deyimlerinde *If Bloğu* yalnızca yürütülen *IF ifadesi* bir sıfır olmayan bir değer (veya TRUE) değerlendirir. Varsa değerini *ifade* sıfır değilse, *Deyim1* bloğundaki herhangi bir deyim yürütülür ve else-bloğu, varsa atlanır. Varsa değerini *ifade* sıfırsa, ardından If Bloğu atlanır ve else-bloğu, varsa yürütülür. Sıfır olmayan için değerlendirme ifadeler
- TRUE
- bir null olmayan işaretçi
- sıfır olmayan aritmetik değerdeki, veya 
- bir aritmetik, mantıksal değer veya işaretçi belirsiz bir dönüştürmesini tanımlayan bir sınıf adı yazın. (Dönüştürmeler hakkında daha fazla bilgi için bkz. [standart dönüştürmeler](../cpp/standard-conversions.md).)   
  
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

```cpp  
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
## <a name="if-statement-with-an-initializer"></a>bir başlatıcı with deyimi
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir **varsa** ifadesi bildirir ve adlandırılmış bir değişken başlatır bir ifade içerebilir. If Bloğu kapsamında değişken yalnızca gerektiğinde bu tür bir IF deyimi kullanın. 

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

 İçindeki tüm biçimlerinin **varsa** deyimi *ifade*, bir yapı dışında herhangi bir değer olan değerlendirilir, tüm yan etkileri de dahil olmak üzere. Denetim geçer **varsa** deyimi programdaki sonraki deyime sürece birini *deyimi*s içeren bir [sonu](../cpp/break-statement-cpp.md), [Devam](../cpp/continue-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md).  
  
 **Başka** yan tümcesi bir `if...else` deyimi en yakın ilişkili önceki **varsa** deyimi karşılık gelen sahip değil aynı kapsamda **başka** deyimi.   

## <a name="constexpr-if-statements"></a>constexpr varsa deyimleri
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işlev şablonlarında kullanabilirsiniz bir `constexpr if` derleme zamanı dallanma birden çok başvurmadan gerek kalmadan kararları vermek için deyimi işlev aşırı yüklemelerinin. Örneğin, tek bir işlev, (hiçbir sıfır parametresi aşırı yüklemesi gerekli değildir) bu tanıtıcıları parametresi açmak yazabilirsiniz: 

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

## <a name="see-also"></a>Ayrıca bkz.  
 [Seçim deyimleri](../cpp/selection-statements-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [switch Deyimi (C++)](../cpp/switch-statement-cpp.md)