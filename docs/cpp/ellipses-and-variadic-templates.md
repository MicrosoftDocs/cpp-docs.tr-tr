---
title: Üç Nokta ve Variadic Şablonları
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 358cdeeaf6f3e8c7f7841bbc796eca6557ccd145
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366332"
---
# <a name="ellipses-and-variadic-templates"></a>Üç Nokta ve Variadic Şablonları

Bu makalede, C++ değişken şablonları ile elips ( )`...`nasıl kullanılacağı gösterilmektedir. Elipslerin C ve C++'da birçok kullanımı olmuştur. Bunlar, işlevler için değişken bağımsız değişken listeleri içerir. `printf()` C Runtime Kitaplığı işlevi en iyi bilinen örneklerden biridir.

*Variadic şablon,* rasgele sayıda bağımsız değişkeni destekleyen bir sınıf veya işlev şablonudur. Bu mekanizma, hem sınıf şablonlarına hem de işlev şablonlarına uygulayabileceğiniz ve böylece çok çeşitli tür güvenli ve önemsiz olmayan işlevsellik ve esneklik sağlayabildiğiniz için Özellikle C++ kitaplık geliştiricileri için yararlıdır.

## <a name="syntax"></a>Sözdizimi

Bir elips variadik şablonlar tarafından iki şekilde kullanılır. Parametre adının solunda, bir *parametre paketini*ve parametre adının sağında, parametre paketlerini ayrı adlara genişletir.

*Variadic şablon sınıf* tanımı sözdiziminin temel bir örneği aşağıda verilmiştir:

```cpp
template<typename... Arguments> class classname;
```

Hem parametre paketleri hem de genişletmeler için, aşağıdaki örneklerde gösterildiği gibi, tercihinize göre elipslerin etrafına boşluk ekleyebilirsiniz:

```cpp
template<typename ...Arguments> class classname;
```

Ya da bu:

```cpp
template<typename ... Arguments> class classname;
```

Bu makalenin ilk örnekte gösterilen kuralı kullandığına `typename`dikkat edin (elipsler eklenir).

Önceki örneklerde, *Bağımsızlar* bir parametre paketidir. Sınıf, `classname` aşağıdaki örneklerde olduğu gibi değişken sayıda bağımsız değişken kabul edebilir:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Değişken şablon sınıf tanımı nı kullanarak, en az bir parametre de ekleyebilirsiniz:

```cpp
template <typename First, typename... Rest> class classname;
```

*Variadic şablon işlevi* sözdiziminin temel bir örneği aşağıda verilmiştir:

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

*Bağımsız değişken* parametre paketi, bir sonraki bölümde gösterildiği gibi, **çeşitli şablonları anlamak**için genişletilir.

Variadic şablon işlev sözdizimi diğer formları mümkündür -dahil, ancak bunlarla sınırlı değildir, bu örnekler:

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

**Const** gibi belirteciler de izin verilir:

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Variadic şablon sınıf tanımlarında olduğu gibi, en az bir parametre gerektiren işlevler yapabilirsiniz:

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Variadic şablonlar `sizeof...()` işleci (eski `sizeof()` işleç ile ilgisi olmayan) kullanın:

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>Elips yerleşimi hakkında daha fazla şey

Daha önce, bu makalede, parametre paketleri ve açılımları "parametre adının solunda, parametre paketini belirtir ve parametre adının sağında, parametre paketlerini ayrı adlara genişletir" olarak tanımlayan elips yerleşimi açıklanmıştır. Bu teknik olarak doğrudur, ancak koda çeviri de kafa karıştırıcı olabilir. Aşağıdakileri dikkate alın:

- Şablon parametre listesinde (`template <parameter-list>`), `typename...` şablon parametre paketini tanır.

- Parametre-deklarasyon-yan`func(parameter-list)`tümcesinde ( ), "üst düzey" elips bir işlev parametre paketi sunar ve elips konumlandırma önemlidir:

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- Elipsin bir parametre adından hemen sonra görüntülendiği durumlarda, parametre paketi genişletmeniz gerekir.

## <a name="example"></a>Örnek

Variadik şablon işlev mekanizmasıgöstermek için iyi bir yolu bazı işlevsellik bir yeniden `printf`yazmak kullanmaktır:

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>Çıktı

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
> Variadik şablon işlevlerini içeren uygulamaların çoğu, bazı formların özyinelemesini kullanır, ancak geleneksel özyinelemeden biraz farklıdır.  Geleneksel özyineleme, aynı imzayı kullanarak kendisini çağıran bir işlev içerir. (Aşırı yüklenmiş veya şablonlanmış olabilir, ancak her seferinde aynı imza seçilir.) Variadic özyineleme, farklı (hemen hemen her zaman azalan) bağımsız değişken sayılarını kullanarak ve bu nedenle her seferinde farklı bir imzayı damgalayarak variadik bir işlev şablonu çağırmayı içerir. Bir "temel durum" hala gereklidir, ancak özyinelemenin doğası farklıdır.
