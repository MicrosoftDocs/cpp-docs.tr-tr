---
description: "Daha fazla bilgi edinin: C++ ' da lambda Ifadeleri"
title: C++'deki Lambda İfadeleri
ms.date: 05/07/2019
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
ms.openlocfilehash: 5e65279fa8740876ad8824803ec459ced154f952
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321047"
---
# <a name="lambda-expressions-in-c"></a>C++'deki Lambda İfadeleri

C++ 11 ve sonraki sürümlerinde, genellikle *lambda* olarak adlandırılan bir lambda ifadesi, bir işlev için bağımsız değişken olarak çağrıldığı veya geçirildiği konumda anonim işlev nesnesi (bir *Kapanış*) tanımlamanın kolay bir yoludur. Genellikle Lambdalar, algoritmalara veya zaman uyumsuz yöntemlere geçirilen birkaç satır kodu kapsüllemek için kullanılır. Bu makale lambdaların ne olduğunu tanımlar, bunları diğer programlama teknikleri ile karşılaştırır, faydalarını anlatır ve temel bir örnek verir.

## <a name="related-topics"></a>İlgili Konular

- [Lambda ifadeleri ile işlev nesneleri](lambda-expression-syntax.md)
- [Lambda ifadeleriyle çalışma](examples-of-lambda-expressions.md)
- [constexpr lambda ifadeleri](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>Lambda Ifadesinin kısımları

ISO C++ standardı, işleve üçüncü bağımsız değişken olarak geçirilen basit bir lambda gösterir `std::sort()` :

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

Bu çizimde bir lambda 'nin bölümleri gösterilmektedir:

![Lambda ifadesinin yapısal öğeleri](../cpp/media/lambdaexpsyntax.png "Lambda ifadesinin yapısal öğeleri")

1. *Capture yan tümcesi* (C++ belirtiminde *lambda-tanıtıcı cer* olarak da bilinir.)

1. *parametre listesi* Seçim. ( *Lambda bildirimci* olarak da bilinir)

1. *kesilebilir belirtim* Seçim.

1. *özel durum belirtimi* Seçim.

1. *sondaki dönüş türü* Seçim.

1. *lambda gövdesi*.

### <a name="capture-clause"></a>Yakalama Yan Tümcesi

Lambda, gövdesinde ( **C++ 14**' te) yeni değişkenler ekleyebilir ve ayrıca çevreleyen kapsamdaki değişkenlere erişebilir veya bunları *yakalayabilir*. Lambda, yakalama yan tümcesi (Standart sözdiziminde *lambda-tanıtıcı cer* ) ile başlar, hangi değişkenlerin yakalandığını ve yakalamanın değere göre mi yoksa başvuruya göre mi olduğunu belirtir. Ampersan ( `&` ) ön ekine sahip değişkenlere, bu değere göre erişilmeyen başvuru ve değişkenlere göre erişilir.

Boş bir yakalama yan tümcesi, `[ ]` lambda ifadesinin gövdesinin kapsayan kapsamda hiçbir değişken olmadığını gösterir.

Lambda içinde başvurulan herhangi bir dış değişkenin nasıl yakalanacağını belirtmek için varsayılan yakalama modunu (Standart sözdiziminde *yakala-varsayılan* ) kullanabilirsiniz: `[&]` başvuruda bulunulan tüm değişkenler başvuruya göre yakalanır ve `[=]` değer tarafından yakalandıkları anlamına gelir. Varsayılan yakalama modunu kullanabilir ve ardından belirli değişkenler için ters modu açıkça belirtebilirsiniz. Örneğin, bir lambda gövdesi External değişkenine `total` başvuruya ve dış değişkene `factor` değere göre erişiyorsa, aşağıdaki yakalama yan tümceleri eşdeğerdir:

```cpp
[&total, factor]
[factor, &total]
[&, factor]
[factor, &]
[=, &total]
[&total, =]
```

Yalnızca bir yakalama varsayılan kullanıldığında lambda içinde bahsedilen değişkenler yakalanır.

Bir yakalama yan tümcesi yakalama varsayılanını içeriyorsa `&` , `identifier` `capture` Bu yakalama yan tümcesinin içinde Hayır formu olabilir `& identifier` . Benzer şekilde, yakalama yan tümcesi bir Capture-default içeriyorsa `=` , `capture` Bu yakalama yan tümcesinin hiçbir ikisi de forma sahip olamaz `= identifier` . Bir tanımlayıcı veya **`this`** bir yakalama yan tümcesinde birden çok kez görünemez. Aşağıdaki kod parçacığı bazı örnekler göstermektedir.

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

Daha sonra üç nokta olan bir yakalama, bu [değişen sayıda bağımsız değişken şablon](../cpp/ellipses-and-variadic-templates.md) örneğinde gösterildiği gibi bir paket genişletmesine sahiptir:

```cpp
template<class... Args>
void f(Args... args) {
    auto x = [args...] { return g(args...); };
    x();
}
```

Bir sınıf yönteminin gövdesinde lambda ifadeleri kullanmak için, **`this`** kapsayan sınıfın yöntemlerine ve veri üyelerine erişim sağlamak üzere işaretçiyi yakalama yan tümcesine geçirin.

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): **`this`** işaretçi **`*this`** , yakalama yan tümcesinde belirtilerek değere göre yakalanamaz. Değere göre yakala, lambda ifadesini ifade eden anonim işlev nesnesi olan tüm *kapanışın*, lambda 'nin çağrıldığı her çağrı sitesine kopyalandığı anlamına gelir. Özellikle NUMA gibi belirli donanım mimarilerinde, lambda paralel veya zaman uyumsuz işlemlerde yürütülecektir, değere göre yakala yararlı olur.

Lambda ifadelerinin sınıf yöntemleriyle nasıl kullanılacağını gösteren bir örnek için, [lambda Ifadeleri örneklerinde](../cpp/examples-of-lambda-expressions.md)"örnek: bir yöntemde lambda ifadesi kullanma" konusuna bakın.

Capture yan tümcesini kullandığınızda, özellikle çoklu iş parçacıklı lambdaları kullandığınızda bu noktaları aklınızda tutmanız önerilir:

- Başvuru yakalamaları, dışındaki değişkenleri değiştirmek için kullanılabilir, ancak değer yakalamaları olamaz. ( **`mutable`** kopyaların değiştirilmesine izin verir, ancak orijinallerin değil.)

- Başvuru yakalamaları, dışındaki değişkenlere yapılan güncelleştirmeleri yansıtır, ancak değer yakalamaları desteklemez.

- Başvuru yakalamaları ömür bağımlılığını ortaya çıkarabilir, ancak değer yakalamalarında yaşam süresi bağımlılıkları yoktur. Lambda zaman uyumsuz olarak çalıştırıldığında bu özellikle önemlidir. Bir zaman uyumsuz lambdabaşvuruya göre yerel olarak yakalarsanız, söz konusu yerel, lambda çalışma zamanında bir erişim ihlaline neden olacak şekilde bu yerel olarak çok büyük olasılıkla geçmiş olur.

### <a name="generalized-capture-c-14"></a>Genelleştirilmiş yakalama (C++ 14)

C++ 14 ' te, bu değişkenlerin lambda işlevinin kapsayan kapsamında mevcut olması gerekmeden, yakalama yan tümcesinde yeni değişkenler oluşturabilir ve başlatabilirsiniz. Başlatma, herhangi bir rastgele ifade olarak ifade edilebilir; Yeni değişkenin türü, ifade tarafından üretilen türden çıkarılır. Bu özelliğin bir avantajı, C++ 14 ' te yalnızca taşıma değişkenlerini (std:: unique_ptr gibi) çevreleyen kapsamdan yakalayabilir ve bunları bir lambda içinde kullanabilirsiniz.

```cpp
pNums = make_unique<vector<int>>(nums);
//...
      auto a = [ptr = move(pNums)]()
        {
           // use ptr
        };
```

### <a name="parameter-list"></a>Parametre Listesi

Bir lambda, değişkenleri yakalamaya ek olarak giriş parametrelerini kabul edebilir. Bir parametre listesi (Standart sözdiziminde *lambda bildirimci* ) isteğe bağlıdır ve çoğu yönü bir işlevin parametre listesine benzer.

```cpp
auto y = [] (int first, int second)
{
    return first + second;
};
```

**C++ 14**' te, parametre türü geneldir ise, **`auto`** anahtar sözcüğünü tür belirleyicisi olarak kullanabilirsiniz. Bu, derleyiciye işlev çağrısı işlecini şablon olarak oluşturmasını söyler. **`auto`** Bir parametre listesindeki her bir örneği ayrı bir tür parametresine eşdeğerdir.

```cpp
auto y = [] (auto first, auto second)
{
    return first + second;
};
```

Bir lambda ifadesi, kendi bağımsız değişkeni olarak başka bir lambda ifadesini alabilir. Daha fazla bilgi için bkz. [lambda Ifadelerinin örnekleri](../cpp/examples-of-lambda-expressions.md)konusundaki "daha yüksek sıralı Lambda ifadeleri".

Bir parametre listesi isteğe bağlı olduğu için, lambda ifadesine bağımsız değişkenler geçirmezseniz ve lambda bildirimci *özel durum belirtimi*, *sonda-Return-Type* ya da içermiyorsa boş ayraçları atlayabilirsiniz **`mutable`** .

### <a name="mutable-specification"></a>Değişebilir Belirtim

Genellikle, bir lambda 'nin işlev çağrısı işleci sabit değere göre, ancak **`mutable`** anahtar sözcüğünün kullanılması bunu iptal eder. Değişebilir veri üyeleri oluşturmaz. Değişebilir belirtim, bir lambda ifadesinin gövdesinin değere göre yakalanan değişkenleri değiştirmesini sağlar. Bu makalenin ilerleyen kısımlarında bazı örnekler, nasıl kullanılacağını göstermektedir **`mutable`** .

### <a name="exception-specification"></a>Özel Durum Belirtimi

**`noexcept`** Lambda ifadesinin özel durumlar oluşturmadığını belirtmek için özel durum belirtimini kullanabilirsiniz. Normal işlevlerde olduğu gibi, bir lambda ifadesi [](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) **`noexcept`** özel durum belirtimini bildirirse ve lambda gövdesi aşağıda gösterildiği gibi bir özel durum oluşturursa, Microsoft C++ derleyicisi uyarı C4297 oluşturur:

```cpp
// throw_lambda_expression.cpp
// compile with: /W4 /EHsc
int main() // C4297 expected
{
   []() noexcept { throw 5; }();
}
```

Daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).

### <a name="return-type"></a>Dönüş Türü

Lambda ifadesinin dönüş türü otomatik olarak çıkarılır. [`auto`](../cpp/auto-cpp.md)Bir *sondaki dönüş türü* belirtmediğiniz müddetçe anahtar sözcüğünü kullanmanız gerekmez. *Sondaki dönüş türü* sıradan bir yöntemin veya işlevin dönüş türü bölümüne benzer. Ancak, dönüş türü parametre listesini izlemelidir ve dönüş türünden önce sondaki-Return-Type anahtar sözcüğünü dahil etmeniz gerekir **`->`** .

Lambda gövdesinde yalnızca bir dönüş deyimi varsa veya ifade bir değer döndürmezse bir lambda ifadesinin dönüş türü bölümünü atlayabilirsiniz. Lambda gövdesi bir dönüş deyimi içeriyorsa, derleyici dönüş türünü dönüş ifadesinin türünden çıkarır. Aksi halde, derleyici dönüş türünü olarak bir kesinti olur **`void`** . Bu ilkeyi gösteren aşağıdaki kod parçacıkları örneğini inceleyin.

```cpp
auto x1 = [](int i){ return i; }; // OK: return type is int
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing
                                  // return type from braced-init-list is not valid
```

Lambda ifadesi, kendi dönüş değeri olarak başka bir lambda ifadesi üretebilir. Daha fazla bilgi için [lambda Ifadeleri örneklerinde](../cpp/examples-of-lambda-expressions.md)"daha yüksek sıralı Lambda ifadeleri" başlığına bakın.

### <a name="lambda-body"></a>Lambda Gövdesi

Lambda ifadesinin lambda gövdesi (Standart sözdiziminde *bileşik deyim* ), sıradan bir yöntem veya işlev gövdesinin içerebileceği her şeyi içerebilir. Hem sıradan bir işlevin hem de bir lambda ifadesinin gövdesi bu tür değişkenlere erişebilir:

- Daha önce açıklandığı gibi kapsayan kapsamdan yakalanan değişkenler.

- Parametreler

- Yerel olarak bildirilen değişkenler

- Sınıf veri üyeleri, bir sınıf içinde bildirildiğinde ve **`this`** yakalanır

- Statik depolama süresi (örneğin, genel değişkenler) içeren herhangi bir değişken

Aşağıdaki örnek, değişkeni `n` değere göre açıkça yakalayan ve değişkeni başvuruya göre dolaylı olarak yakalayan bir lambda ifadesi içerir `m` :

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

Değişken `n` değere göre yakalandığından, değeri `0` lambda ifadesine çağrıdan sonra kalır. **`mutable`** Belirtim `n` lambda içinde değiştirilmesine izin verir.

Lambda ifadesi yalnızca otomatik depolama süresine sahip değişkenleri yakalayabilse de, bir lambda ifadesinin gövdesindeki statik depolama süresine sahip değişkenleri kullanabilirsiniz. Aşağıdaki örnek, `generate` bir nesnesindeki her öğeye bir değer atamak için işlevini ve bir lambda ifadesini kullanır `vector` . Lambda ifadesi sonraki öğenin değerini oluşturmak için statik değişkeni değiştirir.

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

Daha fazla bilgi için bkz. [oluşturma](../standard-library/algorithm-functions.md#generate).

Aşağıdaki kod örneği, önceki örnekteki işlevini kullanır ve C++ standart kitaplığı algoritmasını kullanan bir lambda ifadesinin örneğini ekler `generate_n` . Bu lambda ifadesi bir nesnesinin bir öğesini `vector` önceki iki öğenin toplamına atar. **`mutable`** Anahtar sözcüğü, lambda ifadesinin gövdesinin dış değişkenlerin kopyalarını değiştirebilmeleri `x` ve `y` lambda ifadesinin değere göre yakaladığı şekilde kullanılır. Lambda ifadesi özgün değişkenleri `x` ve değere göre yakaladığı için `y` , `1` lambda yürütüldükten sonra değerleri kalır.

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

Daha fazla bilgi için bkz. [generate_n](../standard-library/algorithm-functions.md#generate_n).

## <a name="constexpr-lambda-expressions"></a>`constexpr` Lambda ifadeleri

**Visual Studio 2017 sürüm 15,3 ve üzeri** (ile birlikte kullanılabilir [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): bir lambda ifadesi **`constexpr`** , yakalayan veya tanıtan her bir veri üyesinin başlatılmasına bir sabit ifade dahilinde izin verildiğinde, sabit bir ifadede olarak verilebilir veya kullanılabilir.

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

Bir lambda, **`constexpr`** sonucu bir işlevin gereksinimlerine uygunsa örtük bir şekilde yapılır **`constexpr`** :

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Bir lambda örtük olarak veya açıkça açık ise **`constexpr`** , bir işlev işaretçisine dönüştürme işlevi üretir **`constexpr`** :

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="microsoft-specific"></a>Microsoft'a özgü

Lambdalar şu ortak dil çalışma zamanı (CLR) yönetilen varlıklarda desteklenmez: **`ref class`** , **`ref struct`** , **`value class`** veya **`value struct`** .

Gibi Microsoft 'a özgü bir değiştirici kullanıyorsanız, [`__declspec`](../cpp/declspec.md) bunu hemen sonra bir lambda ifadesine ekleyebilirsiniz `parameter-declaration-clause` — Örneğin:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Bir değiştiricinin Lambdalar tarafından desteklenip desteklenmediğini öğrenmek için, belgelerinin [Microsoft 'A özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md) bölümünde onunla ilgili makaleye bakın.

C++ 11 standart lambda işlevselliğine ek olarak Visual Studio, rastgele çağırma kuralları kullanan işlev işaretçilerine dönüştürülebilir durum bilgisiz lambda 'leri destekler.

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığındaki işlev nesneleri](../standard-library/function-objects-in-the-stl.md)<br/>
[İşlev çağrısı](../cpp/function-call-cpp.md)<br/>
[`for_each`](../standard-library/algorithm-functions.md#for_each)
