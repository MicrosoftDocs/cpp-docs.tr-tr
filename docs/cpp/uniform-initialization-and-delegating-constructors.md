---
title: "Başlatma ve oluşturucuları temsilci olarak görevlendirme Tekdüzen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68d8f9724ba7f26ac9df9b81c1e4c3f6213f76a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="uniform-initialization-and-delegating-constructors"></a>Tek Düzen Başlatma ve Oluşturucuları Temsilci Olarak Görevlendirme
Modern C++'da, kullandığınız *başlatma ayracı* eşittir işareti olmadan herhangi bir türü için. Ayrıca, benzer iş gerçekleştirmek birden çok oluşturucuları varsa, kodunuzu basitleştirmek için temsilci seçme oluşturucular kullanabilirsiniz.  
  
## <a name="brace-initialization"></a>Küme parantezi başlatma  
 Küme parantezi başlatma herhangi sınıf, yapı veya birleşim için kullanabilirsiniz. Türü örtük veya açık olarak bildirilen, varsayılan bir oluşturucu, varsa varsayılan parantezi başlatma (ile boş ayraçlar) kullanabilirsiniz. Örneğin, aşağıdaki sınıf hem varsayılan hem de varsayılan olmayan parantezi başlatma kullanarak başlatılmamış olabilir:  
  
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
  
 Bir sınıf varsayılan olmayan oluşturucuları varsa, hangi sınıfında üyeler görünür parantezi Başlatıcı sıradır ilgili parametreleri oluşturucuda görünme sırasını, üyeler bildirildiğinde sırasını değil (olduğu gibi `class_a` içinde Önceki örnekte). Bildirilen bir oluşturucu yok türündeyse Aksi halde, üyeler parantezi Başlatıcı görünme sırasını bildirilen sipariş aynıdır; Bu durumda, istediğiniz, ancak herhangi bir üyenin atlayamazsınız gibi birçok ortak üyeleri başlatabilirsiniz. Bildirilen bir oluşturucu yok olduğunda aşağıdaki örnekte kullanılan sırayı parantezi başlatma gösterir:  
  
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
    class_d d5("string", 'c', 2.0 }; // compiler error  
}   
```  
  
 Varsayılan Oluşturucu açıkça bildirilen ancak silinmiş olarak işaretlenmiş, varsayılan parantezi başlatma kullanılamaz:  
  
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
  
 Küme parantezi başlatma kullanabilirsiniz başlatma herhangi bir yere genellikle yaptığınız — Örneğin, bir işlev parametresi veya dönüş değeri olarak ya da sahip `new` anahtar sözcüğü:  
  
```cpp  
class_d* cf = new class_d{4.5};  
kr->add_d({ 4.5 });  
return { 4.5 };  
  
```  
  
## <a name="initializerlist-constructors"></a>initializer_list oluşturucular  
 [İnitializer_list sınıfı](../standard-library/initializer-list-class.md) bir oluşturucu ve diğer bağlamlarda kullanılabilir belirtilen bir türün nesnelerin listesini temsil eder. Küme parantezi başlatma kullanarak bir initializer_list oluşturabileceğiniz:  
  
```cpp  
initializer_list<int> int_list{5, 6, 7};  
```  
  
> [!IMPORTANT]
>  Bu sınıf kullanmak için eklemelisiniz [< initializer_list >](../standard-library/initializer-list.md) üstbilgi.  
  
 Bir `initializer_list` kopyalanabilir. Bu durumda, yeni liste üyeleri özgün listesi üyeleri için başvurular şunlardır:  
  
```cpp  
initializer_list<int> ilist1{ 5, 6, 7 };  
initializer_list<int> ilist2( ilist1 );  
if (ilist1.begin() == ilist2.begin())  
    cout << "yes" << endl; // expect "yes"  
  
```  
  
 Standart Kitaplığı kapsayıcı sınıfları ve ayrıca `string`, `wstring`, ve `regex`, sahip `initializer_list` oluşturucular. Aşağıdaki örneklerde, bu oluşturucular ile başlatma ayracı gösterilmektedir:  
  
```cpp  
vector<int> v1{ 9, 10, 11 };   
map<int, string> m1{ {1, "a"}, {2, "b"} };  
string s{ 'a', 'b', 'c' };   
regex rgx{'x', 'y', 'z'};   
```  
  
## <a name="delegating-constructors"></a>Oluşturucuların Temsili  
 Pek çok sınıf benzer şeyler birden çok oluşturucular sahip — Örneğin, parametreleri doğrulayın:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c() {}  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) {   
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) {  
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
    }  
};  
```  
  
 Tüm doğrulama ancak kodunu yapan bir işlev ekleyerek yinelenen kod azaltabilir `class_c` anlamak ve bir oluşturucusu bazı başka bir işin temsilci seçebilecek durumunda sürdürmek daha kolay olacaktır. Temsilci oluşturucular eklemek için kullanın `constructor (. . .) : constructor (. . .)` sözdizimi:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) : class_c(my_max) {   
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
}  
};  
int main() {  
  
    class_c c1{ 1, 3, 2 };  
}  
  
```  
  
 Önceki örnekte adım olarak dikkat Oluşturucusu `class_c(int, int, int)` ilk oluşturucuyu çağırır `class_c(int, int)`, sırayla çağıran `class_c(int)`. Her Oluşturucular, yalnızca diğer oluşturucular tarafından gerçekleştirilmez çalışma gerçekleştirir.  
  
 Böylece tüm üyeleri bu noktada başlatılmış çağrılan ilk Oluşturucusu nesnesini başlatır. Aşağıda gösterildiği gibi başka bir oluşturucuya temsilciler oluşturucuda üye başlatma yapamazsınız:  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    // member initialization here, no delegate  
    class_a(string str) : m_string{ str } {}  
  
    //can’t do member initialization here  
    // error C3511: a call to a delegating constructor shall be the only member-initializer  
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}  
  
    // only member assignment  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string;  
};  
  
```  
  
 Sonraki örnek statik olmayan veri üyesi başlatıcıları kullanımını göstermektedir. Verilen veri üyesi aynı zamanda bir oluşturucu başlatır, üye başlatıcıdan kılınmadığı dikkat edin:  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };  
};  
  
int main() {  
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"  
    int y = 4;  
}  
```  
  
 Oluşturucu temsilci sözdizimi Oluşturucusu özyineleme yanlışlıkla oluşturulmasını engellemez — Constructor1 çağırır Constructor1 çağıran Constructor2 — ve bir yığın taşması kadar hata atılmaz. Bu döngüleri önlemek için sorumluluğundadır.  
  
```cpp  
class class_f{  
public:  
    int max;  
    int min;  
  
    // don't do this  
    class_f() : class_f(6, 3){ }  
    class_f(int my_max, int my_min) : class_f() { }  
};  
```