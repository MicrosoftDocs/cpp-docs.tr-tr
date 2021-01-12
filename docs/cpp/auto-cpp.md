---
description: 'Hakkında daha fazla bilgi edinin: `auto` (C++)'
title: auto (C++)
ms.date: 12/10/2019
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 061ddac33af4b8e1587b2ab1035d9f96ba18b108
ms.sourcegitcommit: 14d6ae0d527d05d153e26463d4cd5ada0f43e864
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2021
ms.locfileid: "98104758"
---
# <a name="auto-c"></a>`auto` C++

Bir belirtilen değişkenin türünü başlatma ifadesinden kesintiler.

> [!NOTE]
> C++ standardı, bu anahtar sözcük için özgün ve düzeltilmiş anlamı tanımlar. Visual Studio 2010 ' den önce, **`auto`** anahtar sözcüğü *Otomatik* depolama sınıfında bir değişken bildirir; diğer bir deyişle, yerel ömrü olan bir değişkendir. Visual Studio 2010 ' den itibaren **`auto`** anahtar sözcüğü, türü, bildiriminde başlatma ifadesinden çıkarılan bir değişken bildirir. [ `/Zc:auto`&#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği, **`auto`** anahtar sözcüğünün anlamını denetler.

## <a name="syntax"></a>Syntax

> **`auto`***bildirimci* *başlatıcısı***`;`**

> **`[](auto`***Param1* **`, auto`** *param2***`) {};`**

## <a name="remarks"></a>Açıklamalar

**`auto`** Anahtar sözcüğü, derleyicisini, türü olarak belirtilen bir değişkenin veya lambda ifadesi parametresinin başlatma ifadesini kullanacak şekilde yönlendirir.

**`auto`** Bu avantajları sağladığından, gerçekten bir dönüştürme istemediğiniz durumlar için anahtar sözcüğünü kullanmanızı öneririz:

- **Sağlamlık:** İfadenin türü değiştirilirse — bu, bir işlev dönüş türü değiştirildiğinde, yalnızca çalışır.

- **Performans:** Hiçbir dönüştürme işleminin olmaması garanti edilir.

- **Kullanılabilirlik:** Tür adı yazımı sorunları ve yazım hataları hakkında endişelenmeniz gerekmez.

- **Verimlilik:** Kodlarınız daha verimli olabilir.

Kullanmak isteyebileceğiniz dönüştürme durumları **`auto`** :

- Belirli bir tür istediğinizde, başka hiçbir şey yapmayabilir.

- İfade şablonu yardımcı türleri — Örneğin, `(valarray+valarray)` .

Anahtar sözcüğünü kullanmak için bir **`auto`** değişken bildirmek üzere bir tür yerine bunu kullanın ve bir başlatma ifadesi belirtin. Ayrıca, **`auto`** anahtar sözcüğünü **`const`** ,, **`volatile`** işaretçi ( **`*`** ), başvuru () **`&`** ve rvalue başvurusu ( **`&&`** ) gibi belirticileri ve bildirimcileri kullanarak da değiştirebilirsiniz. Derleyici başlatma ifadesini değerlendirir ve değişkenin türünü bırakmak için bu bilgileri kullanır.

**`auto`** Başlatma ifadesi birkaç form alabilir:

- Evrensel başlatma söz dizimi, örneğin `auto a { 42 };` .
- Atama söz dizimi, örneğin `auto b = 0;` .
- Önceki iki formu birleştiren evrensel atama söz dizimi `auto c = { 3.14156 };` .
- Doğrudan başlatma veya gibi Oluşturucu stili sözdizimi `auto d( 1.41421f );` .

Daha fazla bilgi için bu belgede daha sonra [başlatıcılar](../cpp/initializers.md) ve kod örnekleri bölümüne bakın.

**`auto`** Aralık tabanlı bir ifadede döngü parametresini bildirmek için kullanıldığında, **`for`** Örneğin, farklı bir başlatma sözdizimi kullanır `for (auto& i : iterable) do_action(i);` . Daha fazla bilgi için bkz. [Aralık tabanlı `for` Ifade (C++)](../cpp/range-based-for-statement-cpp.md).

**`auto`** Anahtar sözcüğü bir tür için yer tutucudur, ancak kendisi bir tür değildir. Bu nedenle **`auto`** anahtar sözcüğü, [`sizeof`](../cpp/sizeof-operator.md) ve gibi (C++/CLI için) atamalar veya operatörler içinde kullanılamaz [`typeid`](../extensions/typeid-cpp-component-extensions.md) .

## <a name="usefulness"></a>Yarar

**`auto`** Anahtar sözcüğü, karmaşık bir türü olan bir değişkeni bildirmenin basit bir yoludur. Örneğin, **`auto`** başlatma ifadesinin şablonlar, işlev işaretçileri veya üye işaretçileri içeren bir değişken bildirmek için kullanabilirsiniz.

Bir **`auto`** lambda ifadesine bir değişken bildirmek ve başlatmak için de kullanabilirsiniz. Lambda ifadesinin türü yalnızca derleyiciye bilindiği için değişkenin türünü kendiniz bildiremezsiniz. Daha fazla bilgi için bkz. [lambda Ifadelerine örnekler](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Sondaki dönüş türleri

**`auto`** **`decltype`** Şablon kitaplıklarını yazmaya yardımcı olması için tür belirticisiyle birlikte kullanabilirsiniz. **`auto`** **`decltype`** Dönüş türü, şablon bağımsız değişkenlerinin türlerine bağlı olan bir şablon işlevi bildirmek için ve kullanın. Veya, **`auto`** başka bir **`decltype`** işleve yapılan çağrıyı sarmalayan bir şablon işlevi bildirmek için ve öğesini kullanın ve ardından diğer işlevin dönüş türü olan herhangi bir değer döndürür. Daha fazla bilgi için bkz. [`decltype`](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Başvurular ve CV niteleyicileri

' Nin, bu **`auto`** başvuruları, **`const`** niteleyicileri ve niteleyicileri kullanma ' yı unutmayın **`volatile`** . Aşağıdaki örneği inceleyin:

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

Önceki örnekte, myAuto bir **`int`** başvuru değildir, bu **`int`** nedenle çıkış, `11 11` `11 12` başvuru niteleyicisi tarafından bırakılmadığı takdirde olduğu gibi değildir **`auto`** .

## <a name="type-deduction-with-braced-initializers-c14"></a>Küme ayracıyla belirtilen başlatıcıları ile tür kesintisi (c++ 14)

Aşağıdaki kod örneği, **`auto`** küme ayraçları kullanarak nasıl bir değişkenin başlatılacağını göstermektedir. B ve C arasındaki ve ile E arasındaki farkı dikkate alın.

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

Aşağıdaki tabloda **`auto`** , anahtar sözcüğünün kullanımıyla ilgili kısıtlamalar ve derleyicinin yaydığı karşılık gelen tanılama hata iletisi listelenmektedir.

|Hata numarası|Açıklama|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**`auto`** Anahtar sözcüğü diğer tür tanımlayıcılarla birleştirilemez.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|**`auto`** Anahtar sözcüğüyle belirtilen sembolün bir başlatıcısı olmalıdır.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|**`auto`** Bir tür bildirmek için anahtar sözcüğünü yanlış kullandınız. Örneğin, bir yöntem dönüş türü veya dizi bildirdiniz.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Bir parametre veya şablon bağımsız değişkeni, **`auto`** anahtar sözcüğüyle bildirilemez.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Bir yöntem veya şablon parametresi **`auto`** anahtar sözcüğü ile bildirilemez.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Bir sembol başlatılmadan önce kullanılamaz. Pratikte bu, değişken kendisini başlatmak için kullanılamayan anlamına gelir.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Anahtar sözcüğüyle belirtilen bir türe atanamaz **`auto`** .|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Anahtar sözcükle belirtilen bir bildirimci listesindeki tüm semboller **`auto`** aynı türe çözümlenmelidir. Daha fazla bilgi için bkz. [Bildirimler ve tanımlar](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md) ve [TypeId](../extensions/typeid-cpp-component-extensions.md) işleçleri, anahtar sözcüğüyle belirtilen bir simgeye uygulanamaz **`auto`** .|

## <a name="examples"></a>Örnekler

Bu kod parçaları, **`auto`** anahtar sözcüğünün kullanılabileceği bazı yolları gösterir.

Aşağıdaki bildirimler eşdeğerdir. İlk ifadede, değişken tür olarak `j` bildirilmiştir **`int`** . İkinci ifadede, `k` **`int`** başlangıç ifadesi (0) bir tamsayı olduğundan değişken tür olarak anlaşılamıyor.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Aşağıdaki bildirimler eşdeğerdir, ancak ikinci bildirim birinciden daha basittir. Anahtar sözcüğünü kullanmanın en etkileyici nedenlerinden biri **`auto`** basitdir.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

Aşağıdaki kod parçası değişkenlerin türünü `iter` ve `elem` **`for`** ve Aralık döngülerinin ne zaman başlatılacağını bildirir **`for`** .

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

Aşağıdaki kod parçası, **`new`** işaretçileri bildirmek için işleç ve işaretçi bildirimini kullanır.

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

Bu kod parçası, `?:` değişkeni `x` 200 değerine sahip bir tamsayı olarak bildirmek için koşullu işleci () kullanır:

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Aşağıdaki kod parçası, türü için değişkeni `x` **`int`** , türüne `y` başvuru için değişkeni **`const int`** ve `fp` tür döndüren bir işlevin işaretçisine değişken **`int`** olarak başlatır.

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

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`/Zc:auto` (Değişken türünü türet)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[`sizeof` İşlecinde](../cpp/sizeof-operator.md)<br/>
[`typeid`](../extensions/typeid-cpp-component-extensions.md)<br/>
[`operator new`](new-operator-cpp.md)<br/>
[Bildirimler ve tanımlar](declarations-and-definitions-cpp.md)<br/>
[Lambda Ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md)<br/>
[Başlatıcılar](../cpp/initializers.md)<br/>
[`decltype`](../cpp/decltype-cpp.md)
