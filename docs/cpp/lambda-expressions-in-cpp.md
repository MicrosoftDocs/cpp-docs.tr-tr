---
title: C++'deki lambda ifadeleri | Microsoft Docs
ms.custom: ''
ms.date: 07/19/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc8457371ef266c5628e225eff8f05328190e52d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941973"
---
# <a name="lambda-expressions-in-c"></a>C++'deki Lambda İfadeleri
C ++ 11 ve sonraki sürümlerinde, bir lambda ifadesi — genellikle olarak adlandırılan bir *lambda*— bir anonim işlev nesnesi tanımlamanın bir yoludur (bir *kapanış*) konumunda Burada, çağrılan veya bağımsız değişken olarak geçirilen sağ bir işlev. Genellikle lambda ifadeleri, algoritmalar veya zaman uyumsuz yöntemler için geçen birkaç satır kod kapsüllemek için kullanılır. Bu makale lambdaların ne olduğunu tanımlar, bunları diğer programlama teknikleri ile karşılaştırır, faydalarını anlatır ve temel bir örnek verir.  

## <a name="related-topics"></a>İlgili Konular
- [İşlev nesneleri ve lambda ifadeleri](lambda-expression-syntax.md)
- [Lambda ifadeleri ile çalışma](examples-of-lambda-expressions.md)
- [constexpr lambda ifadeleri](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>Bir Lambda ifadesinin bölümleri  
 Üçüncü bağımsız değişkeni olarak geçirilen basit bir lambda ISO C++ standardı gösteren `std::sort()` işlevi:  
  
```cpp  
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
  
```  
  
 Bu örnekte, bir lambda bölümlerini gösterilmiştir:  
  
 ![Bir lambda ifadesinin yapısal öğelerini](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *Yakalama yan tümcesi* (diğer adıyla *lambda-introducer* C++ belirtimindeki.)  
  
2.  *parametre listesi* isteğe bağlı. (Diğer adıyla *lambda declarator*)  
  
3.  *değişebilir belirtim* isteğe bağlı.  
  
4.  *özel durum belirtimi* isteğe bağlı.  
  
5.  *trailing-return-type* isteğe bağlı.  
  
6.  *Lambda gövdesi*)  
  
### <a name="capture-clause"></a>Yakalama Yan Tümcesi  
 Bir lambda gövdesinde yeni değişkenleri çıkarabilir (içinde **C ++ 14**) ve bu erişim, ayrıca veya *yakalama*, çevreleyen kapsama değişkenleri. Bir lambda yakalama yan tümcesi ile başlar (*lambda-introducer* standart söz diziminde), hangi değişkenler yakalanır ve yakalama değere veya başvuruya göre olup olmadığını belirtir. Önekine sahip değişkenler (`&`) sahip olmayan değişkenleri değer tarafından erişilen ve ön ek, başvuru tarafından erişilir.  
  
 Bir boş yakalama yan tümcesi `[ ]`, lambda ifadesinin gövdesinin kapsayan kapsam içinde değişkenlere erişmediğini belirtir.  
  
 Varsayılan yakalama modu kullanabilirsiniz (*yakalama varsayılan* standart söz diziminde) herhangi bir dış lambda içinde başvurulan değişkenleri yakalama belirtmek için: `[&]` başvurmanız tüm değişkenleri tarafından yakalanır anlamına gelir Başvuru ve `[=]` değere göre yakalanan oldukları anlamına gelir. Varsayılan yakalama modunu kullanın ve ardından belirli değişkenler için açıkça karşı modu belirtin. Örneğin, bir lambda gövdesi dış değişkenine erişiyorsa `total` dış değişkenine ve başvuru tarafından `factor` değere göre ardından aşağıdaki yakalama ifadeleri eşdeğerdir:  
  
```cpp  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 Yakalama varsayılan kullanıldığında yalnızca lambdada değişkenler yakalanır.  
  
 Yakalama yan tümcesi bir yakalama varsayılan içeriyorsa `&`, ardından hiçbir `identifier` içinde bir `capture` söz konusu yakalama yan tümcesi form olabilir `& identifier`. Benzer şekilde, yakalama yan tümcesi bir yakalama varsayılan içeriyorsa `=`, ardından hiçbir `capture` söz konusu yakalama yan tümcesi form olabilir `= identifier`. Bir tanımlayıcı veya **bu** yakalama yan tümcesinde birden çok kez yer alamaz. Aşağıdaki kod parçacığı bazı örnekler göstermektedir.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};      // OK  
    [&, &i]{};     // ERROR: i preceded by & when & is the default  
    [=, this]{};   // ERROR: this when = is the default  
    [=, *this]{ }; // OK: captures this by value. See below.
    [i, i]{};      // ERROR: i repeated  
}  
```  
  
 Bu konuda gösterildiği gibi üç nokta ve ardından bir yakalama bir paket genişletmesi olan [variadic şablon](../cpp/ellipses-and-variadic-templates.md) örneği:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 Bir sınıf yönteminin gövdesinde lambda ifadeleri kullanmak için geçirin `this` işaretçisini yakalama yan tümcesi, kapsayan sınıfın yöntemlerini ve veri üyelerine erişim sağlamak için. 
 
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **bu** işaretçi yakalanıp değerle belirterek `*this` yakalama yan tümcesi içinde. Değere göre yakalama anlamına tüm *kapanış*, lambda ifadesi bu encapulates anonim bir işlev nesnesidir, lambda burada çağrıldığında her çağrı sitesine kopyalanır. Değere göre yakalama, özellikle mimarilerde belirli donanım NUMA gibi paralel veya zaman uyumsuz işlem olarak lambda yürütülür gerektiğinde faydalıdır. 

Lambda ifadelerini sınıf yöntemleriyle kullanmaya kullanmayı gösteren bir örnek için bkz: "Örnek: kullanarak bir Lambda ifadesi, bir yöntemi" [Examples of Lambda Expressions](../cpp/examples-of-lambda-expressions.md).  
  
 Yakalama yan tümcesi kullanırken, özellikle lambdaları ile kullandığınızda aşağıdaki noktaları göz önünde bulundurun öneririz çoklu iş parçacığı kullanımı:  
  
-   Başvuru yakalamaları dışarıdaki değişkenlere değiştirmek için kullanılabilir, ancak değer yakalamaları olamaz. (**değişebilir** değiştirilecek kopyalar ancak değil de sağlar.)  
  
-   Başvuru yakalamaları güncelleştirmeleri dışarıdaki değişkenlere yansıtacaktır yansıtır, ancak değer yakalamaları yapın.  
  
-   Başvuru yakalamalarında ömür bağımlılık sunar, ancak değer yakalamaları hiçbir ömrü bağımlılıklara sahip. Bu, zaman uyumsuz olarak lambda çalıştırdığında, özellikle önemlidir. Yerel bir zaman uyumsuz lambda başvuruya göre yakalama, bu yerel çok büyük bir olasılıkla lambda çalıştığında, tarafından çalışma zamanında bir erişim ihlali výsledek silinecekler.  
  
### <a name="generalized-capture-c-14"></a>Genelleştirilmiş yakalama (C++ 14)  
  
 C ++ 14, ortaya çıkarabilir ve lambda işlev kapsayan kapsamda değişkenlere gerek olmadan yakalama yan tümcesinde yeni değişkenleri başlatma yok. Başlatma rastgele herhangi bir ifade belirtilebilir; Yeni değişken türü ifade tarafından üretilen türünden çıkarılır. C ++ 14'te yalnızca taşınabilir değişkenlerinden (std::unique_ptr gibi) çevreleyen kapsama yakalayabilir ve bunları bir lambda içinde kullanın, bu özelliğin bir avantajdır.  
  
```cpp  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### <a name="parameter-list"></a>Parametre Listesi  
 Değişkenleri yakalama ek olarak, bir lambda parametrelerini kabul edebilir. Parametre listesi (*lambda declarator* standart sözdiziminde) isteğe bağlıdır ve birçok yönden bir işlevin parametre listesine benzer.  
  
```cpp  
auto y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 İçinde **C++ 14**, parametre türü genelse, auto anahtar kelimesini tür belirticisi kullanabilirsiniz. Bu işlev çağrısı işleci bir şablon olarak oluşturmak için derleyicinin bildirir. Otomatik parametre listesindeki her bir örneğini bir benzersiz tür parametresine eşdeğerdir.  
  
```cpp  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 Bir lambda ifadesi, kendi bağımsız değişkeni olarak başka bir lambda ifadesini alabilir. Daha fazla bilgi için "Yüksek sıralı Lambda Expressions" bölümüne bakın. [Examples of Lambda Expressions](../cpp/examples-of-lambda-expressions.md).  
  
 Parametre listesi isteğe bağlı olduğundan, lambda ifadesine bağımsız değişkenler geçmez ve kendi lambda-declarator içermiyor, boş ayraçları atlayabilirsiniz *özel durum belirtimi*,  *trailing-return-type*, veya **değişebilir**.  
  
### <a name="mutable-specification"></a>Değişebilir Belirtim  
 Genellikle, sabit değerli bir lambdanın işlev çağrısı işleci, ancak kullanım **değişebilir** anahtar sözcüğü ortadan bu kaldırır. Değişebilir veri üyeleri oluşturmaz. Değişebilir belirtim, bir lambda ifadesinin gövdesinin değere göre yakalanan değişkenleri değiştirmesini sağlar. Bu makalenin ilerleyen bölümlerinde verilen örneklerde bazıları nasıl kullanabileceğinizi gösteren **değişebilir**.  
  
### <a name="exception-specification"></a>Özel Durum Belirtimi  
 Kullanabileceğiniz `noexcept` lambda ifadesi bir özel durum oluşturmadığını belirtmek için özel durum belirtimi. Normal işlevlerde olduğu Visual C++ derleyicisi uyarısını üretir [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) bir lambda ifadesi bildirir, `noexcept` özel durum belirtimi ve lambda gövdesi burada gösterildiği gibi bir özel durum oluşturur:  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() noexcept { throw 5; }();  
}  
```  
  
 Daha fazla bilgi için [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).  
  
### <a name="return-type"></a>Dönüş Türü  
 Bir lambda ifadesinin dönüş türü otomatik olarak çıkarılır. Kullanmak zorunda değilsiniz [otomatik](../cpp/auto-cpp.md) anahtar sözcüğü, belirtmediğiniz sürece bir *trailing-return-type*. *Trailing-return-type* dönüş türü bölümü sıradan bir yöntem veya işlev benzer. Ancak, dönüş türü parametre listesini izlemelisiniz ve trailing-return-type anahtar sözcüğünü içermelidir `->` dönüş türünden önce.  
  
 Lambda gövdesi yalnızca bir dönüş deyimi içeriyorsa veya ifade bir değer döndürmeyen bir lambda ifadesinin dönüş türü bölümü atlayabilirsiniz. Lambda gövdesi bir dönüş deyimi içeriyorsa, derleyici dönüş türünü dönüş ifadesinin türünden çıkarır. Aksi halde derleyici dönüş türü olacak şekilde çıkarır **void**. Bu ilkeyi gösteren aşağıdaki kod parçacıkları örneğini inceleyin.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
```  
  
 Lambda ifadesi, kendi dönüş değeri olarak başka bir lambda ifadesi üretebilir. Daha fazla bilgi için bkz: "Yüksek sıralı Lambda Expressions" [Examples of Lambda Expressions](../cpp/examples-of-lambda-expressions.md).  
  
### <a name="lambda-body"></a>Lambda Gövdesi  
 Lambda gövdesi (*compound-statement* standart söz diziminde) bir lambda ifadesi, sıradan bir yöntem veya işlev gövdesinin içerebilen her şeyi içerebilir. Sıradan bir işlev hem lambda ifadesinin gövdesinin değişkenleri bu tür erişebilirsiniz:  
  
-   Daha önce açıklandığı gibi değişkenleri kapsayan kapsamın yakalanan.  
  
-   Parametreler  
  
-   Yerel olarak bildirilen değişkenler  
  
-   Sınıf veri üyeleri, bir sınıf içinde bildirildiğinde ve **bu** yakalanır  
  
-   Statik depolama süresine sahip herhangi bir değişken — Örneğin, genel değişkenler  
  
 Aşağıdaki örnek, açıkça değişken yakalayan bir lambda ifadesi içerir `n` değere ve örtük olarak değişkenini `m` başvuruya göre:  
  
```cpp  
// captures_lambda_expression.cpp  
// compile with: /W4 /EHsc   
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int m = 0;  
   int n = 0;  
   [&, n] (int a) mutable { m = ++n + a; }(4);  
   cout << m << endl << n << endl;  
}  
```  
  
```Output  
5  
0  
```  
  
 Çünkü değişken `n` kendi değeri kalır değere göre yakalanan `0` lambda ifadesine yönelik çağrı sonra. **Değişebilir** belirtimlerinden `n` lambda içinde değiştirilecek.  
  
 Lambda ifadesi yalnızca otomatik depolama süresine sahip değişkenleri yakalayabilse de, bir lambda ifadesinin gövdesindeki statik depolama süresine sahip değişkenleri kullanabilirsiniz. Aşağıdaki örnekte `generate` işlevi ve her öğe için bir değer atamak için bir lambda ifadesi bir `vector` nesne. Lambda ifadesi sonraki öğenin değerini oluşturmak için statik değişkeni değiştirir.  
  
```cpp  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });   
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
```  
  
 Daha fazla bilgi için [oluşturmak](../standard-library/algorithm-functions.md#generate).  
  
 Aşağıdaki kod örneği, önceki örnekten gelen işlevi kullanır ve C++ Standart Kitaplığı algoritmasını kullanan bir lambda ifadesi örneği ekler `generate_n`. Bir öğenin bu lambda ifadesi atar bir `vector` önceki iki öğenin toplamına nesne. **Değişebilir** anahtar sözcüğü kullanılır, böylece lambda ifadesinin gövdesinin harici değişkenlerinin bulunan kopyalarını değiştirebilir `x` ve `y`, lambda ifadesi değere göre yakalar. Lambda ifadesi özgün değişkenlerini yakaladığından `x` ve `y` değere göre bunların değerleri kalır `1` lambda yürütüldükten sonra.  
  
```cpp  
// compile with: /W4 /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });  
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
  
int main()  
{  
    // The number of elements in the vector.  
    const int elementCount = 9;  
  
    // Create a vector object with each element set to 1.  
    vector<int> v(elementCount, 1);  
  
    // These variables hold the previous two elements of the vector.  
    int x = 1;  
    int y = 1;  
  
    // Sets each element in the vector to the sum of the   
    // previous two elements.  
    generate_n(v.begin() + 2,  
        elementCount - 2,  
        [=]() mutable throw() -> int { // lambda is the 3rd parameter  
        // Generate current value.  
        int n = x + y;  
        // Update previous two values.  
        x = y;  
        y = n;  
        return n;  
    });  
    print("vector v after call to generate_n() with lambda: ", v);  
  
    // Print the local variables x and y.  
    // The values of x and y hold their initial values because   
    // they are captured by value.  
    cout << "x: " << x << " y: " << y << endl;  
  
    // Fill the vector with a sequence of numbers  
    fillVector(v);  
    print("vector v after 1st call to fillVector(): ", v);  
    // Fill the vector with the next sequence of numbers  
    fillVector(v);  
    print("vector v after 2nd call to fillVector(): ", v);  
}  
```  
  
```Output  
vector v after call to generate_n() with lambda: 1 1 2 3 5 8 13 21 34  
x: 1 y: 1  
vector v after 1st call to fillVector(): 1 2 3 4 5 6 7 8 9  
vector v after 2nd call to fillVector(): 10 11 12 13 14 15 16 17 18  
```  
  
 Daha fazla bilgi için [generate_n](../standard-library/algorithm-functions.md#generate_n).  

## <a name="constexpr-lambda-expressions"></a>constexpr lambda ifadeleri
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir lambda ifadesi olarak bildirilebilir `constexpr` veya sabit bir ifadede kullanılamaz olduğunda her veri üyesinin başlatılması BT'nin yakalar veya tanıtır içinde bir sabit ifadesine izin verilir.  

```cpp
    int y = 32;
    auto answer = [y]() constexpr 
    {
        int x = 10;
        return y + x; 
    };

    constexpr int Increment(int n) 
    {
        return [n] { return n + 1; }();
    }

``` 
Bir lambda örtülü olarak başvuruluyor `constexpr` sonucunu gereksinimlerini karşılayıp karşılamadığını bir `constexpr` işlevi:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Bir lambda, örtük veya açık ise `constexpr`, bir işlev işaretçisine dönüştürme üreten bir `constexpr` işlevi:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="microsoft-specific"></a>Microsoft'a özgü  
 Lambdalar aşağıdaki ortak dil çalışma zamanı (CLR) yönetilen varlıklar içinde desteklenmiyor: **başvuru sınıfı**, **ref struct**, **değer sınıfının**, veya **değer yapısı** .  
  
 Microsoft'a özgü değiştirici gibi kullanıyorsanız [__declspec](../cpp/declspec.md), bir lambda ifadesi Ekle hemen sonra `parameter-declaration-clause`; örneğin:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Bir değiştirici lambda tarafından desteklenip desteklenmediğini belirlemek için bilgi makaleye bakın [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md) belgelerin bölümü.  
  
 Visual Studio, C ++ 11 standart lambda işlevlere ek olarak durum bilgisiz lambdalar rastgele çağırma kurallarına kullanan işlev işaretçilerine dönüştürülebilir olan destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart kitaplığındaki işlev nesneleri](../standard-library/function-objects-in-the-stl.md)   
 [İşlev çağrısı](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
