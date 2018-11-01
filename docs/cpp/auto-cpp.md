---
title: Otomatik (C++)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: f396d95d08a435ac3d85e214226921ce468a2259
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447456"
---
# <a name="auto-c"></a>Otomatik (C++)

Kendi başlatma ifadesinden bildirilmiş bir değişken türü çıkarır.

## <a name="syntax"></a>Sözdizimi

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>Açıklamalar

**Otomatik** anahtar sözcüğü, derleyicinin kendi türü için başlatma ifadesini bildirilmiş bir değişken veya lambda ifadesi parametre kullanmasını yönlendirir.

Kullanmanızı öneririz **otomatik** çoğu durum için anahtar sözcüğü — bir dönüştürme gerçekten istemediğiniz sürece; çünkü bu avantajlar sağlar:

- **Sağlamlık:** ifadenin türü değiştirilirse — Bu, bir işlevin dönüş türü değiştirildiğinde içerir — düzgün çalışır.

- **Performans:** dönüştürme olacaktır garanti.

- **Kullanılabilirlik:** türü adı yazım güçlükler ve yazım yanlışları hakkında endişelenmeniz gerekmez.

- **Verimliliği:** kodlamanızı daha verimli olabilir.

Dönüştürme durumları değil istediğiniz kullanılacak **otomatik**:

- Belirli bir tür ve başka hiçbir şey istediğinizde yapın.

- İfade şablon yardımcı türü — örneğin, `(valarray+valarray)`.

Kullanılacak **otomatik** anahtar sözcüğü, bir tür yerine bir değişken bildirmek için kullanın ve bir başlatma ifadesi belirtin. Ayrıca, değiştirebileceğiniz **otomatik** tanımlayıcıların ve bildirimcilerin gibi kullanarak anahtar sözcüğü **const**, **geçici**, işaretçi (`*`), başvuru (`&`) ve rvalue başvurusu (`&&`). Derleyici, başlatma ifadesini değerlendirir ve sonra değişkenin türü için bu bilgileri kullanır.

Atama (eşittir işareti sözdizimi) doğrudan başlatmadaki (işlev stili sözdizimi) başlatma ifadesi olabilir bir [new işleci](new-operator-cpp.md) ifadesi veya başlatma ifadesi olabilir  *için aralığı-bildirimi* parametresinde bir [aralık tabanlı for deyimi (C++)](../cpp/range-based-for-statement-cpp.md) deyimi. Daha fazla bilgi için [başlatıcılar](../cpp/initializers.md) ve daha sonra bu belgedeki kod örnekleri.

**Otomatik** anahtar sözcüğü bir tür için bir yer tutucudur, ancak kendisi değil bir tür. Bu nedenle, **otomatik** anahtar sözcüğü kullanılamaz atamaları veya işleçler gibi [sizeof](../cpp/sizeof-operator.md) ve [TypeID](../windows/typeid-cpp-component-extensions.md).

## <a name="usefulness"></a>Fayda

**Otomatik** anahtar sözcüğü, bir karmaşık türü bir değişken bildirmek için basit bir yoludur. Örneğin, kullanabileceğiniz **otomatik** burada başlatma ifadesini içerir şablonları, işlev işaretçileri veya üye işaretçileri bir değişken bildirmek için.

Ayrıca **otomatik** bir lambda ifadesine bir değişkeni bildirmek ve başlatmak için. Bir lambda ifadesinin türü yalnızca derleyicinin bilindiğinden kendiniz değişkeninin türü bildirimini yapamazsınız. Daha fazla bilgi için [Examples of Lambda Expressions](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Dönüş türlerini takip etme

Kullanabileceğiniz **otomatik**birlikte **decltype** tür şablon kitaplıklarını yazma yardımcı olmak için tanımlayıcısı. Kullanım **otomatik** ve **decltype** türü olan dönüş bir şablon işlevi bildirmek için şablon bağımsız değişkenlerinin türlerine bağlıdır. Ya da kullanmak **otomatik** ve **decltype** başka bir işleve bir çağrı sarılır ve sonra da ne olursa olsun, bu bir işlevin dönüş türü döndüren bir şablon işlevi bildirmek için. Daha fazla bilgi için [decltype](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Başvurular ve cv niteleyicileri

Bu Not **otomatik** başvuruları niteleyicileri const ve volatile niteleyicileri bırakır. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}

```

Çıktı önceki örnekte myAuto int, bir int başvuru olduğundan `11 11`değil `11 12` başvuru niteleyicisi bırakılmış değil, durum olduğu gibi **otomatik**.

## <a name="type-deduction-with-braced-initializers-c14"></a>Küme ayracıyla belirtilen Başlatıcı (C ++ 14) ile tür kesintisi

Aşağıdaki kod örneği, küme ayraçlarını kullanarak bir otomatik değişkeni başlatmak gösterilmektedir. B ve C arasındaki ve A arasındaki farka dikkat edin ve n.

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>Kısıtlamaları ve hata iletileri

Kullanma kısıtlamaları aşağıdaki tabloda **otomatik** anahtar sözcüğü ve derleyici yayan ilgili tanılama hata iletisi.

|Hata sayısı|Açıklama|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**Otomatik** anahtar sözcüğü herhangi başka bir tür tanımlayıcısı ile birleştirilemez.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|İle bildirilen bir sembol **otomatik** anahtar sözcüğü, bir başlatıcıya sahip olmalıdır.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Size yanlış kullanılan **otomatik** bir türü bildirmek için anahtar sözcüğü. Örneğin, bir yöntemin dönüş türü veya dizi bildirimi.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Bir parametre veya şablon bağımsız değişkeni ile bildirilemez **otomatik** anahtar sözcüğü.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Bir yöntem veya şablon parametresi ile bildirilemez **otomatik** anahtar sözcüğü.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Bir sembol başlatılmadan önce kullanılamaz. Uygulamada, kendisini başlatmak için bir değişken kullanılamaz anlamına gelir.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|İle bildirilen bir türe dönüştürülemiyor **otomatik** anahtar sözcüğü.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Bir bildirimci listesinde ile bildirilen tüm sembolleri **otomatik** anahtar sözcüğü, aynı türe çözümlemelisiniz. Daha fazla bilgi için [bildirimlerinin ve tanımlarının](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md) ve [TypeID](../windows/typeid-cpp-component-extensions.md) işleçleri ile bildirilen bir sembol uygulanamaz **otomatik** anahtar sözcüğü.|

## <a name="examples"></a>Örnekler

Bu kod parçalarını yollarla bazılarını göstermeyi **otomatik** anahtar sözcüğü kullanılabilir.

Aşağıdaki bildirimleri eşdeğerdir. Değişken ilk deyiminde `j` türü olarak bildirilmiş **int**. İkinci deyim, değişken içinde `k` türüne atanan **int** başlatma ifadesi (0) bir tamsayı olduğu.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Aşağıdaki bildirimleri eşdeğerdir, ancak ikinci bildirim daha basittir. Kullanmak için en önemli nedenlerinden biri **otomatik** Basitlik bir anahtardır.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

Aşağıdaki kod parçası, değişkenlerin türü bildirir `iter` ve `elem` olduğunda **için** ve aralık **için** döngüsü başlangıç.

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

Aşağıdaki kod parçası kullanan **yeni** işaretçileri bildirmek için işleci ve işaretçi bildirimi.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

Sonraki kod parçası, her bir bildirim deyiminde birden çok sembolleri bildirir. Tüm simgeleri her bir deyimde aynı türe çözmek dikkat edin.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

Bu kod parçasını koşullu işleç kullanır (`?:`) değişkenini bildirmek için `x` 200 değeri bir tamsayı olarak:

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Aşağıdaki kod parçası değişkenini `x` türüne **int**, değişken `y` yazmanız için bir başvuruya **const int**, değişken `fp` bir işlev işaretçisi türü döndüren **int**.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto & y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../cpp/auto-keyword.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof İşleci](../cpp/sizeof-operator.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)<br/>
[new işleci](new-operator-cpp.md)<br/>
[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)<br/>
[Lambda İfadeleri Örnekleri](../cpp/examples-of-lambda-expressions.md)<br/>
[Başlatıcılar](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
