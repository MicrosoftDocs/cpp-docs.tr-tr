---
title: C++'deki lambda ifadeleri | Microsoft Docs
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 035fe5c222f6de5b3f0d71c0ce9133c1101f2993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lambda-expressions-in-c"></a>C++'deki Lambda İfadeleri
C ++ 11 ve sonraki sürümlerinde, bir lambda ifadesi — adlandırılırlar bir *lambda*— anonim işlevi nesneyi tanımlamanın uygun bir yoludur (bir *kapatma*) konumunda Burada, çağrılan veya bağımsız değişken olarak geçirilen sağ bir işlev. Tipik lambdas algoritmalar veya zaman uyumsuz yöntemleri geçirilen birkaç satır kod kapsüllemek için kullanılır. Bu makale lambdaların ne olduğunu tanımlar, bunları diğer programlama teknikleri ile karşılaştırır, faydalarını anlatır ve temel bir örnek verir.  

## <a name="related-topics"></a>İlgili Konular
- [Lambda ifadeleri işlev nesneleri karşılaştırması](lambda-expression-syntax.md)
- [Lambda ifadeleri ile çalışma](examples-of-lambda-expressions.md)
- [constexpr lambda ifadeleri](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>Lambda ifadesi bölümleri  
 ISO C++ Standart üçüncü bağımsız değişken olarak geçirilen basit bir lambda gösterir `std::sort()` işlevi:  
  
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
  
 Bu grafik bir lambda bölümlerini göstermektedir:  
  
 ![Lambda ifadesi yapısal öğeleri](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *yan tümcesi yakalama* (olarak da bilinen *lambda introducer* C++ belirtiminde.)  
  
2.  *parametre listesi* isteğe bağlı. (Olarak da bilinen *lambda bildirimcisi*)  
  
3.  *değişebilir belirtimi* isteğe bağlı.  
  
4.  *özel durum belirtimi* isteğe bağlı.  
  
5.  *sondaki-dönüş türü* isteğe bağlı.  
  
6.  *Lambda gövde*)  
  
### <a name="capture-clause"></a>Yakalama Yan Tümcesi  
 Bir lambda kendi gövdesindeki yeni değişkenleri getirebilir (içinde **C ++ 14**) ve ayrıca erişimi olabilir veya *yakalama*, çevresindeki kapsamdan değişkenleri. Bir lambda yakalama yan tümcesi ile başlar (*lambda introducer* standart sözdiziminde), hangi değişkenleri yakalanır ve yakalama değere veya başvuruya göre olup olmadığını belirtir. Ve işareti sahip değişkenler (`&`) öneki başvuruya göre erişilir ve onu yok değişkenleri değere göre erişilir.  
  
 Bir boş yakalama yan tümcesi `[ ]`, lambda ifadesi gövdesi çevreleyen kapsamdaki değişken erişen gösterir.  
  
 Varsayılan yakalama modunu kullanabilirsiniz (*yakalama varsayılan* standart sözdiziminde) herhangi bir lambda başvurulan değişkenleri dış yakalama belirtmek için: `[&]` başvuruda tüm değişkenleri tarafından yakalanan anlamına gelir başvuru, ve `[=]` değeri tarafından yakalanan oldukları anlamına gelir. Varsayılan bir yakalama modu kullanın ve ardından belirli değişkenler için açıkça ters modunu belirtin. Örneğin, bir lambda gövdesi dış değişken erişirse `total` başvurusu ve dış değişken `factor` değer ile ardından aşağıdaki yakalama yan tümceleri eşdeğerdir:  
  
```cpp  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 Yakalama varsayılan kullanıldığında lambda içinde açıklanan değişkenleri yakalanır.  
  
 Yakalama varsayılan bir yakalama yan tümcesi içeriyorsa, `&`, sonra hiçbir `identifier` içinde bir `capture` Bu yakalama formun yan tümcesi bulunan `& identifier`. Benzer şekilde, bir yakalama varsayılan yakalama yan tümcesi içeriyorsa, `=`, sonra hiçbir `capture` Bu yakalama formun yan tümcesi bulunan `= identifier`. Tanımlayıcı veya `this` yakalama yan tümcesinde birden çok kez yer alamaz. Aşağıdaki kod parçacığı bazı örnekler göstermektedir.  
  
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
  
 Bu gösterildiği gibi üç nokta ve ardından bir yakalama paketi genişletme olan [variadic şablonu](../cpp/ellipses-and-variadic-templates.md) örnek:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 Lambda ifadeleri bir sınıf yöntemi gövdesinde kullanmak için geçirmek `this` kapsayan sınıfı yöntemleri ve verileri üyelerine erişim sağlamak için yakalama yan tümcesi işaretçi. 
 
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): `this` işaretçi yakalanıp değeriyle belirterek `*this` yakalama yan tümcesinde. Yakalama değere göre gelir, tüm *Kapatılmak üzere*, o encapulates lambda ifadesi adsız bir işlev nesnesidir, lambda çağrılır burada her çağrı sitesine kopyalanır. Yakalama değere göre lambda özellikle NUMA gibi belirli donanım mimarileri üzerinde paralel veya zaman uyumsuz işlemler yürütecek yararlıdır. 

Lambda ifadeleri sınıfı yöntemlerinin ile nasıl kullanılacağını gösteren bir örnek için bkz: "Örnek: kullanarak bir Lambda ifadesi, bir yöntemi" [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md).  
  
 Yakalama yan tümcesi kullandığınızda, özellikle Lambda'lar ile kullandığınızda aşağıdaki noktaları göz önünde bulundurmanız önerilir çoklu iş parçacığı kullanımı:  
  
-   Başvuru yakalamaları dışında değişkenlerini değiştirmek için kullanılabilir, ancak değer yakalamaları olamaz. (`mutable` değiştirilecek kopyalar, ancak değil özgün sağlar.)  
  
-   Başvuru yakalamaları dışında değişkenlere güncelleştirmelerini yansıtma, ancak değer yakalamaları yapın.  
  
-   Ömür bağımlılık başvurusu yakalamaları tanıtmak ancak değer yakalamaları hiçbir ömrü bağımlılıkları vardır. Lambda zaman uyumsuz olarak çalıştığında, bu seçenek özellikle önemlidir. Zaman uyumsuz lambda başvuruya göre yerel bir yakalarsanız, yerel çok büyük bir olasılıkla lambda çalıştığında, tarafından çalışma zamanında bir erişim ihlali sonuçta silinecekler.  
  
### <a name="generalized-capture-c-14"></a>Genelleştirilmiş yakalama (C++ 14)  
  
 C ++ 14, ortaya çıkarabilir ve bu değişkenleri gerek kalmadan yakalama yan tümcesinde yeni değişkenleri başlatma lambda işlevin kapsayan kapsamda mevcuttur. Başlatma herhangi rastgele bir ifade ifade edilebilir; Yeni değişken türünü ifade tarafından üretilen türünden anlaşılabilen. Bu özelliğin bir avantaj C ++ 14'te (örneğin, std::unique_ptr) yalnızca taşıma değişkenleri çevresindeki kapsamdan yakalayabilir ve bunları bir lambda kullanmak emin olmalıdır.  
  
```cpp  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### <a name="parameter-list"></a>Parametre Listesi  
 Değişkenleri yakalama yanı sıra bir lambda giriş parametreleri kabul edebilir. Parametre listesi (*lambda bildirimcisi* standart sözdiziminde) isteğe bağlıdır ve birçok yönden işlevi için parametre listesi benzer.  
  
```cpp  
auto y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 İçinde **C++ 14**, parametre türü genel ise, auto anahtar sözcüğü tür belirteci kullanabilirsiniz. Bu işlev çağırma işleci bir şablon olarak oluşturmak için derleyici bildirir. Otomatik parametre listesindeki her bir örneği farklı tür parametresi eşdeğerdir.  
  
```cpp  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 Bir lambda ifadesi, kendi bağımsız değişkeni olarak başka bir lambda ifadesini alabilir. Daha fazla bilgi için "Yüksek düzey Lambda ifadeleri" konusuna bakın. [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md).  
  
 Parametre listesi isteğe bağlı olduğundan, lambda ifadesi bağımsız değişkenleri geçmeyin ve kendi lambda bildirimcisi içermeyen boş parantez atlayabilirsiniz *özel durum belirtimi*,  *sondaki-dönüş türü*, veya `mutable`.  
  
### <a name="mutable-specification"></a>Değişebilir Belirtim  
 Genellikle, sabit değerli bir lambda's işlev çağırma işleci, ancak kullanımı `mutable` anahtar sözcüğü iptal eder Bu. Değişebilir veri üyeleri oluşturmaz. Değişebilir belirtim, bir lambda ifadesinin gövdesinin değere göre yakalanan değişkenleri değiştirmesini sağlar. Bazı örnekler bu makalenin sonraki bölümlerinde nasıl kullanılacağını gösteren `mutable`.  
  
### <a name="exception-specification"></a>Özel Durum Belirtimi  
 Kullanabileceğiniz `noexcept` lambda ifadesi tüm özel durumlar oluşturmadığını belirtmek için özel durum belirtimi. Sıradan işlevleriyle Visual C++ derleyicisi uyarısı oluşturur gibi [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) lambda ifadesi bildirirse `noexcept` özel durum belirtimi ve lambda gövde aşağıda gösterildiği gibi bir özel durum oluşturur:  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() noexcept { throw 5; }();  
}  
```  
  
 Daha fazla bilgi için bkz: [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).  
  
### <a name="return-type"></a>Dönüş Türü  
 Lambda ifadesi dönüş türünü otomatik olarak anlaşılabilen. Kullanmak zorunda değilsiniz [otomatik](../cpp/auto-cpp.md) anahtar sözcüğü belirtmediğiniz sürece bir *sondaki-dönüş türü*. *Sondaki-dönüş türü* bir sıradan yöntemi veya işlev dönüş türü parçası benzer. Ancak, dönüş türü parametre listesine izlemelisiniz ve sondaki-dönüş türü anahtar sözcüğü içermelidir `->` önce dönüş türü.  
  
 Yalnızca bir dönüş ifadesi lambda gövdesi içeriyorsa veya ifade bir değer döndürmüyor lambda ifadesi dönüş türü bölümünü atlayabilirsiniz. Lambda gövdesi bir return deyimi içeriyorsa, derleyici dönüş ifadesi türü dönüş türünden deduces. Aksi takdirde derleyici olması için dönüş türü deduces `void`. Bu ilkeyi gösteren aşağıdaki kod parçacıkları örneğini inceleyin.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
```  
  
 Lambda ifadesi, kendi dönüş değeri olarak başka bir lambda ifadesi üretebilir. Daha fazla bilgi için bkz: "Yüksek düzey Lambda ifadeleri" [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md).  
  
### <a name="lambda-body"></a>Lambda Gövdesi  
 Lambda gövdesi (*bileşik deyim* standart sözdiziminde) bir lambda ifadesi bir sıradan yöntemi veya işlev gövdesi içerebilir herhangi bir şey içerebilir. Sıradan bir işlev ve lambda ifadesi gövdesi değişkenleri bu tür erişebilirsiniz:  
  
-   Değişkenleri kapsayan kapsamından daha önce açıklandığı gibi yakalandı.  
  
-   Parametreler  
  
-   Yerel olarak bildirilen değişkenler  
  
-   Bir sınıf içinde bildirilen olduğunda veri üyeleri, sınıf ve `this` yakalanır  
  
-   Statik depolama süresi olan herhangi bir değişken — Örneğin, genel değişkenler  
  
 Aşağıdaki örnek, açıkça değişkeni yakalayan bir lambda ifadesi içerir `n` değeriyle ve örtülü olarak değişkeni yakalar `m` başvuruya göre:  
  
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
  
 Çünkü değişkeni `n` değer ile kendi değeri kalır yakalanan `0` lambda ifadesi çağrısından sonra. `mutable` Belirtimlerinden `n` lambda içinde değiştirilecek.  
  
 Lambda ifadesi yalnızca otomatik depolama süresine sahip değişkenleri yakalayabilse de, bir lambda ifadesinin gövdesindeki statik depolama süresine sahip değişkenleri kullanabilirsiniz. Aşağıdaki örnek kullanır `generate` işlevi ve her bir öğe için bir değer atamak için bir lambda ifadesi bir `vector` nesnesi. Lambda ifadesi sonraki öğenin değerini oluşturmak için statik değişkeni değiştirir.  
  
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
  
 Daha fazla bilgi için bkz: [oluşturmak](../standard-library/algorithm-functions.md#generate).  
  
 Aşağıdaki kod örneğinde önceki örnekten işlevini kullanır ve C++ Standart Kitaplığı algoritmasını kullanan bir lambda ifadesi örneği ekler `generate_n`. Bu lambda ifadesi bir öğe atar bir `vector` öğelerin toplamı, önceki iki nesne. `mutable` Lambda ifadesi gövdesi dış değişkenleri kendi kopyalarını değiştirmenize olanak sağlayan anahtar sözcüğü kullanılır `x` ve `y`, hangi lambda ifadesi değeriyle yakalar. Lambda ifadesi özgün değişkenleri yakalar çünkü `x` ve `y` değer ile bunların değerleri kalır `1` lambda yürütüldükten sonra.  
  
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
  
 Daha fazla bilgi için bkz: [generate_n](../standard-library/algorithm-functions.md#generate_n).  

## <a name="constexpr-lambda-expressions"></a>constexpr lambda ifadeleri
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): lambda ifadesi olarak bildirilmelidir `constexpr` veya sabit bir ifadede kullanılan zaman başlatma her veri üyesi olan yakalar veya tanıtır içinde bir sabit ifadesine izin verilir.  

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
Bir lambda örtülü olarak başvuruluyor `constexpr` sonucu gereksinimlerini karşılayıp karşılamadığını bir `constexpr` işlevi:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Bir lambda örtük veya açık olarak ise `constexpr`, bir işlev işaretçisi dönüştürme üreten bir `constexpr` işlevi:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="microsoft-specific"></a>Microsoft'a özgü  
 Lambda'lar aşağıdaki ortak dil çalışma zamanı (CLR) yönetilen varlıklar desteklenmiyor: `ref class`, `ref struct`, `value class`, veya `value struct`.  
  
 Microsoft'a özgü değiştiricisi gibi kullanıyorsanız [__declspec](../cpp/declspec.md), bir lambda ifadesi Ekle hemen sonra `parameter-declaration-clause`— örneğin:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Bir değiştirici Lambda'lar tarafından desteklenip desteklenmediğini belirlemek için ilgili makalesine bakın [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md) belgelere bölümü.  
  
 C ++ 11 standart lambda işlevlere ek olarak, Visual Studio omni dönüştürülebilir rasgele çağırma kurallarını kullanmak işlev işaretçileri durum bilgisiz Lambda'lar destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı'nda işlev nesneleri](../standard-library/function-objects-in-the-stl.md)   
 [İşlev çağrısı](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
