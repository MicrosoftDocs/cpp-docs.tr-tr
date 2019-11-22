---
title: Auto (C++)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 8af2aceb2964a5ec3adcbb0b0accab0b051ff48c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303387"
---
# <a name="auto-c"></a>Auto (C++)

Bir belirtilen değişkenin türünü başlatma ifadesinden kesintiler.

## <a name="syntax"></a>Sözdizimi

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>Açıklamalar

**Auto** anahtar sözcüğü, derleyicisini, türü bir veya bir lambda ifade parametresi olan bir veya bir bağımsız değişken olarak kullanmak için olarak bildirir.

Bu avantajları sağladığından, gerçekten bir dönüştürme istemediğiniz durumlar dışında, **Otomatik** anahtar sözcüğünü kullanmanızı öneririz:

- **Sağlamlık:** İfadenin türü değiştirilirse — bu, bir işlev dönüş türü değiştirildiğinde, yalnızca çalışır.

- **Performans:** Hiçbir dönüştürme işleminin olmaması garanti edilir.

- **Kullanılabilirlik:** Tür adı yazımı sorunları ve yazım hataları hakkında endişelenmeniz gerekmez.

- **Verimlilik:** Kodlarınız daha verimli olabilir.

**Otomatik**olarak kullanmak isteyebileceğiniz dönüştürme durumları:

- Belirli bir tür istediğinizde, başka hiçbir şey yapmayabilir.

- İfade şablonu yardımcı türleri — Örneğin, `(valarray+valarray)`.

**Auto** anahtar sözcüğünü kullanmak için bir değişken bildirmek üzere bir tür yerine bunu kullanın ve bir başlatma ifadesi belirtin. Ayrıca, **const**, **volatile**, işaretçi (`*`), başvuru (`&`) ve rvalue başvurusu (`&&`) gibi belirticileri ve bildirimcileri kullanarak **Auto** anahtar sözcüğünü değiştirebilirsiniz. Derleyici başlatma ifadesini değerlendirir ve değişkenin türünü bırakmak için bu bilgileri kullanır.

Başlatma ifadesi bir atama (eşittir işareti sözdizimi), doğrudan başlatma (işlev stili sözdizimi), [işleç New](new-operator-cpp.md) ifadesi veya başlatma ifadesi [Aralık tabanlı for deyimi (C++)](../cpp/range-based-for-statement-cpp.md) deyiminde *Aralık bildirimi* parametresi olabilir. Daha fazla bilgi için bu belgede daha sonra [başlatıcılar](../cpp/initializers.md) ve kod örnekleri bölümüne bakın.

**Auto** anahtar sözcüğü bir tür için yer tutucudur, ancak kendisi bir tür değildir. Bu nedenle, **Auto** anahtar sözcüğü [sizeof](../cpp/sizeof-operator.md) ve (/CLI için C++) [TypeId](../extensions/typeid-cpp-component-extensions.md)gibi tür veya işleçlerinde kullanılamaz.

## <a name="usefulness"></a>Yarar

**Auto** anahtar sözcüğü, karmaşık bir türü olan bir değişkeni bildirmenin basit bir yoludur. Örneğin, başlatma ifadesinin şablonlar, işlev işaretçileri veya üye işaretçileri içeren bir değişken bildirmek için **Auto** kullanabilirsiniz.

Ayrıca, bir lambda ifadesine bir değişken bildirmek ve başlatmak için **Auto** öğesini de kullanabilirsiniz. Lambda ifadesinin türü yalnızca derleyiciye bilindiği için değişkenin türünü kendiniz bildiremezsiniz. Daha fazla bilgi için bkz. [lambda Ifadelerine örnekler](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Sondaki dönüş türleri

Şablon kitaplıklarını yazmaya yardımcı olması için, **Otomatik**olarak, **decltype** tür belirleyicisi ile birlikte kullanabilirsiniz. Dönüş türü, şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için **Auto** ve **decltype** kullanın. Ya da **Otomatik** ve **decltype** kullanarak başka bir işleve yapılan çağrıyı sarmalayan bir şablon işlevi bildirir ve sonra bu diğer işlevin dönüş türü olan herhangi bir değer döndürür. Daha fazla bilgi için bkz. [decltype](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Başvurular ve CV niteleyicileri

**Otomatik** bırakılanlar başvurularını, const niteleyicilerini ve geçici niteleyicileri kullanmayı unutmayın. Aşağıdaki örnek göz önünde bulundurun:

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

Önceki örnekte, myAuto bir int başvurusu değil int 'tir, bu nedenle çıkış `11 11`, `11 12` değil, başvuru niteleyicisi **Otomatik**olarak bırakılmadığı takdirde olur.

## <a name="type-deduction-with-braced-initializers-c14"></a>Küme ayracıyla belirtilen başlatıcıları ile tür kesintisi (c++ 14)

Aşağıdaki kod örneğinde, küme ayraçları kullanılarak otomatik değişkenin nasıl başlatıldığı gösterilmektedir. B ve C arasındaki ve ile E arasındaki farkı dikkate alın.

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

## <a name="restrictions-and-error-messages"></a>Kısıtlamalar ve hata Iletileri

Aşağıdaki tabloda **Auto** anahtar sözcüğünün kullanımıyla ilgili kısıtlamalar ve derleyicinin yaydığı karşılık gelen tanılama hata iletisi listelenmektedir.

|Hata numarası|Açıklama|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**Auto** anahtar sözcüğü diğer tür tanımlayıcılarla birleştirilemez.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|**Auto** anahtar sözcüğüyle belirtilen sembolün bir başlatıcısı olmalıdır.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Bir tür bildirmek için **Auto** anahtar sözcüğünü yanlış kullandınız. Örneğin, bir yöntem dönüş türü veya dizi bildirdiniz.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Bir parametre veya şablon bağımsız değişkeni **Auto** anahtar sözcüğüyle bildirilemez.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Yöntem veya şablon parametresi **Auto** anahtar sözcüğüyle bildirilemez.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Bir sembol başlatılmadan önce kullanılamaz. Pratikte bu, değişken kendisini başlatmak için kullanılamayan anlamına gelir.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|**Auto** anahtar sözcüğüyle belirtilen bir türe atanamaz.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|**Auto** anahtar sözcüğüyle belirtilen bir bildirimci listesindeki tüm semboller aynı türe çözümlenmelidir. Daha fazla bilgi için bkz. [Bildirimler ve tanımlar](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md) ve [TypeId](../extensions/typeid-cpp-component-extensions.md) işleçleri **Auto** anahtar sözcüğüyle belirtilen bir simgeye uygulanamaz.|

## <a name="examples"></a>Örnekler

Bu kod parçaları, **Auto** anahtar sözcüğünün kullanılabileceği bazı yolları gösterir.

Aşağıdaki bildirimler eşdeğerdir. İlk ifadede, değişken `j` **int**türünde olarak bildirilmiştir. İkinci deyimde, başlangıç ifadesi (0) bir tamsayı olduğu için değişken `k` **int** türü olarak anlaşılamıyor.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Aşağıdaki bildirimler eşdeğerdir, ancak ikinci bildirim birinciden daha basittir. **Auto** anahtar sözcüğünü kullanmanın en etkileyici nedenlerinden biri basitdir.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

Aşağıdaki kod parçası, **for** **döngüleri başlatıldığında** `iter` ve `elem` değişkenlerin türünü bildirir.

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

Aşağıdaki kod parçası, işaretçileri bildirmek için **New** operator ve pointer bildirimini kullanır.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

Sonraki kod parçası her bildirim ifadesinde birden çok sembol bildirir. Her deyimdeki tüm sembollerin aynı türe çözümlendiğine dikkat edin.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

Bu kod parçası, değişken `x` 200 değerine sahip bir tamsayı olarak bildirmek için koşullu işleci (`?:`) kullanır:

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Aşağıdaki kod parçası, **int**yazmak için değişken `x` `y`, **const int**türünde bir başvuruya ve değişken `fp` de **int**türü döndüren bir işlevin işaretçisine bir işaretçi olarak başlatır.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
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
[typeid](../extensions/typeid-cpp-component-extensions.md)<br/>
[New işleci](new-operator-cpp.md)<br/>
[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)<br/>
[Lambda İfadeleri Örnekleri](../cpp/examples-of-lambda-expressions.md)<br/>
[Başlatıcılar](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
