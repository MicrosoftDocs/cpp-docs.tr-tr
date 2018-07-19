---
title: Tekdüzen başlatma ve oluşturucuları temsilci olarak görevlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92174ceefa350b739567ac3e67c2ca023afb6008
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939838"
---
# <a name="uniform-initialization-and-delegating-constructors"></a>Tek Düzen Başlatma ve Oluşturucuları Temsilci Olarak Görevlendirme
Modern C++'ta kullanabileceğiniz *başlatma ayracı* eşittir işareti olmadan herhangi bir tür için. Ayrıca, temsilci oluşturucuları benzer işi gerçekleştiren birden çok oluşturucuları varsa, kodu basitleştirmek için kullanabilirsiniz.  
  
## <a name="brace-initialization"></a>Ayraç başlatma  
 Bir sınıf, yapı veya birleşim ayraç başlatma kullanabilirsiniz. Türü örtük veya açık olarak bildirilen bir varsayılan oluşturucusu varsa, varsayılan ayraç başlatma (boş küme ayraçları ile) kullanabilirsiniz. Örneğin, aşağıdaki sınıf hem varsayılan hem de varsayılan olmayan ayraç başlatma kullanılarak başlatılmamış olabilir:  
  
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
  
 Bir sınıf varsayılan olmayan bir oluşturucu hangi sınıf üyeleri, küme ayracı başlatıcısında görüntülenme sırasını ise karşılık gelen parametreleri oluşturucuda görüntülenme sırasını, üyeleri bildirilen sırasını değil (olduğu gibi `class_a` içinde Önceki örnek). Bildirilen hiçbir oluşturucu türü varsa, aksi takdirde, üyeleri küme ayracı başlatıcısında görünme sırasını içinde bildirildikleri sırasıyla aynıdır; Bu durumda, istediğiniz, ancak herhangi bir üyenin atlayamazsınız birçok ortak üyeleri başlatabilirsiniz. Bildirilen hiçbir oluşturucu olduğunda aşağıdaki örnek küme ayracı başlatmada kullanılan sırayı gösterir:  
  
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
  
 Varsayılan Oluşturucu açıkça bildirildi ancak silindi olarak işaretlendi, varsayılan ayraç başlatma kullanılamaz:  
  
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
  
 Ayraç başlatma kullanabileceğiniz her yerden başlatma genellikle yaptığınız — Örneğin, bir işlev parametre veya dönüş değeri olarak ya da sahip **yeni** anahtar sözcüğü:  
  
```cpp  
class_d* cf = new class_d{4.5};  
kr->add_d({ 4.5 });  
return { 4.5 };  
  
```  
  
## <a name="initializerlist-constructors"></a>initializer_list oluşturucular  
 [İnitializer_list sınıfı](../standard-library/initializer-list-class.md) bir oluşturucu ve diğer bağlamlarda kullanılacak belirtilen türdeki nesneleri listesini temsil eder. Ayraç başlatma kullanılarak bir initializer_list oluşturabilirsiniz:  
  
```cpp  
initializer_list<int> int_list{5, 6, 7};  
```  
  
> [!IMPORTANT]
>  Bu sınıf kullanmak için içermelidir [< initializer_list >](../standard-library/initializer-list.md) başlığı.  
  
 Bir `initializer_list` kopyalanabilir. Bu durumda, asıl liste üyeleri için başvurular yeni liste üyelerini şunlardır:  
  
```cpp  
initializer_list<int> ilist1{ 5, 6, 7 };  
initializer_list<int> ilist2( ilist1 );  
if (ilist1.begin() == ilist2.begin())  
    cout << "yes" << endl; // expect "yes"  
  
```  
  
 Standart kitaplık kapsayıcı sınıfları ve ayrıca `string`, `wstring`, ve `regex`, sahip `initializer_list` oluşturucular. Aşağıdaki örnekler, bu oluşturuculara sahip başlatma ayracı gösterilmektedir:  
  
```cpp  
vector<int> v1{ 9, 10, 11 };   
map<int, string> m1{ {1, "a"}, {2, "b"} };  
string s{ 'a', 'b', 'c' };   
regex rgx{'x', 'y', 'z'};   
```  
  
## <a name="delegating-constructors"></a>Oluşturucuların Temsili  
 Birçok sınıflar benzer bir şey yapmanız birden çok oluşturucular sahiptir — örneğin, parametrelerini doğrular:  
  
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
  
 Tüm doğrulama, ancak kodu yapan bir işlev ekleyerek tekrarlanan kodları azaltabilir `class_c` anlamak ve bir oluşturucu başka bir işin bir kısmını temsilci seçebilecek, düzenlenmesi daha kolay olacaktır. Temsilci oluşturucuları eklemek için `constructor (. . .) : constructor (. . .)` söz dizimi:  
  
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
  
 Önceki örnekte ilerleyerek dikkat Oluşturucu `class_c(int, int, int)` ilk oluşturucuyu çağırır `class_c(int, int)`, sırayla çağıran `class_c(int)`. Her Oluşturucular, yalnızca diğer oluşturucular tarafından gerçekleştirilmeyen çalışma gerçekleştirir.  
  
 Tüm üyeleri bu noktada başlatılır, böylece çağrılan ilk Oluşturucu nesnesini başlatır. Burada gösterildiği gibi başka bir oluşturucu için temsilci bir oluşturucuda, üye başlatma işlemleri yapamaz:  
  
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
  
 Sonraki örnek, statik olmayan veri üyesi başlatıcıları kullanımını gösterir. Bir oluşturucu Ayrıca belirli veri üyesini başlatır, üye Başlatıcısı geçersiz kılınmasını dikkat edin:  
  
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
  
 Temsilci Oluşturucu sözdizimi Oluşturucusu özyineleme yanlışlıkla oluşturulmasını engellemez — Constructor1 çağırır Constructor1 çağıran Constructor2 — ve hatasız oluncaya kadar bir yığın taşması özel. Bunu döngüleri önlemek için sizin sorumluluğunuzdur.  
  
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