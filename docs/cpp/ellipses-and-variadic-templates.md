---
title: Üç nokta ve değişken bağımsız değişken Şablonlar
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: e916dac40355f4397ef4846c0edf568c60b7d3dd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221633"
---
# <a name="ellipsis-and-variadic-templates"></a>Üç nokta ve değişken bağımsız değişken Şablonlar

Bu makalede, `...` C++ değişen tek değişkenli şablonlar ile üç nokta () nasıl kullanılacağı gösterilmektedir. Üç nokta, C ve C++ ' da birçok kullanım içeriyordu. Bunlar, işlevleri için değişken bağımsız değişken listeleri içerir. `printf()`C çalışma zamanı kitaplığındaki işlev, en iyi bilinen örneklerden biridir.

Değişen bir bağımsız değişken *şablon* , rastgele sayıda bağımsız değişkeni destekleyen bir sınıf veya işlev şablonudur. Bu mekanizma, hem sınıf şablonlarına hem de işlev şablonlarına uygulayabileceğiniz ve bu sayede çok sayıda tür kullanımı güvenli ve önemsiz olmayan işlevsellik ve esneklik sağlayan C++ kitaplık geliştiricileri için yararlıdır.

## <a name="syntax"></a>Sözdizimi

Üç nokta, değişen sayıda bağımsız değişken içeren şablonlar tarafından iki şekilde kullanılır. Parametre adının solunda, bir *parametre paketini*ve parametre adının sağından bağımsız olarak parametre paketlerini ayrı adlara genişletir.

Aşağıda, değişken sayıda bağımsız *değişken içeren şablon sınıfı* tanım sözdiziminin temel bir örneği verilmiştir:

```cpp
template<typename... Arguments> class classname;
```

Hem parametre paketleri hem de genişletmeleri için, aşağıdaki örneklerde gösterildiği gibi, tercihlerinize göre üç nokta etrafında boşluk ekleyebilirsiniz:

```cpp
template<typename ...Arguments> class classname;
```

Ya da şunları yapın:

```cpp
template<typename ... Arguments> class classname;
```

Bu makalede, ilk örnekte gösterilen kuralı (üç nokta eklenmiş olan) kullandığına dikkat edin **`typename`** .

Yukarıdaki örneklerde *bağımsız değişkenler* bir parametre paketidir. Sınıfı `classname` , bu örneklerde olduğu gibi değişken sayıda bağımsız değişken kabul edebilir:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Değişen bir bağımsız değişken şablon sınıfı tanımı kullanarak, en az bir parametre de gerektirebilir:

```cpp
template <typename First, typename... Rest> class classname;
```

Aşağıda, değişken sayıda bağımsız *değişken şablon işlev* sözdiziminin temel bir örneği verilmiştir:

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

*Bağımsız değişkenler* parametre paketi daha sonra kullanılmak üzere genişletilir ve bu, sonraki bölümde gösterildiği gibi, değişken olmayan, değişken olmayan **şablonları anlama**.

Değişen bağımsız değişken şablon işlevi sözdizimi, ancak bunlarla sınırlı olmamak üzere, şunlar gibi diğer biçimleri olabilir:

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

Benzer tanımlayıcılar **`const`** da kullanılabilir:

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Değişen sayıda bağımsız değişken şablon sınıfı tanımlarında olduğu gibi, en az bir parametre gerektiren işlevler yapabilirsiniz:

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Bağımsız değişken olmayan şablonlar `sizeof...()` işleci kullanır (eski `sizeof()` işleçle ilgisi yoktur):

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>Üç nokta yerleşimi hakkında daha fazla bilgi

Daha önce Bu makalede parametre paketlerinin solunda "parametre adı ve genişletmeleri tanımlayan üç nokta yerleşimi açıklanmış, bir parametre paketi ve parametre adının sağında, parametre paketleri ayrı adlara genişletilir". Bu teknik açıdan doğrudur ancak koda çeviri için kafa karıştırıcı olabilir. Aşağıdakileri dikkate alın:

- Bir Template-List ( `template <parameter-list>` ) parametresinde `typename...` bir şablon parametre paketi tanıtılmıştır.

- Bir parametre-yan tümce () içinde `func(parameter-list)` , "üst düzey" üç nokta bir işlev parametre paketi tanıtır ve üç nokta konumlandırma önemlidir:

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- Üç nokta bir parametre adından hemen sonra göründüğünde bir parametre paketi genişletmeye sahip olursunuz.

## <a name="example"></a>Örnek

Değişen sayıda bağımsız değişken şablon işlev mekanizmasını belirtmenin iyi bir yolu, bazı işlevlerinden bazılarının yeniden yazılması halinde kullanmaktır `printf` :

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
> Değişken bağımsız değişken şablon işlevleri içeren çoğu uygulama, bazı formun özyineleme kullanır, ancak geleneksel özyinelemeden biraz farklıdır.  Geleneksel özyineleme aynı imzayı kullanarak kendisini çağıran bir işlev içerir. (Aşırı yüklenmiş veya şablonlu olabilir, ancak her seferinde aynı imza seçilir.) Değişen sayıda özyineleme, farklı (neredeyse her zaman azalan) bağımsız değişken kullanarak değişen bir değişken işlev şablonunun çağrılmasını ve böylece her seferinde farklı bir imzayı damgalamayı içerir. "Temel Case" yine de gereklidir, ancak özyineleme doğası farklıdır.
