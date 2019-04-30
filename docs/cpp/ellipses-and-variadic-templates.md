---
title: Üç Nokta ve Variadic Şablonları
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 387cf4478192cb9470804c219eee8046f8e47abe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392225"
---
# <a name="ellipses-and-variadic-templates"></a>Üç Nokta ve Variadic Şablonları

Bu makalede, üç nokta kullanılacak gösterilmektedir (`...`) C++ değişen sayıda bağımsız değişken şablonları ile. Üç nokta C ve C++'ta pek çok kullanımı oluşturdu. Bunlar işlevler için değişken bağımsız değişken listeleri içerir. `printf()` İşlevi C Çalışma Zamanı Kitaplığı'ndan en iyi bilinen örneklerden biridir.

A *variadic şablon* rastgele bir bağımsız değişken sayısını destekleyen bir sınıf veya işlev şablonudur. Sınıf şablonları hem işlev şablonları için geçerlidir ve böylece çok çeşitli tür-güvenli ve basit olmayan işlevler ve esneklik sağlar çünkü bu mekanizma C++ Kitaplığı geliştiriciler için özellikle yararlıdır.

## <a name="syntax"></a>Sözdizimi

Üç nokta, değişen sayıda bağımsız değişken şablonları tarafından iki şekilde kullanılır. Sağındaysa parametre adının solunda bir *parametre paketi*, ve sağa parametre adının parametre paketlerini ayrı adlarda genişletir.

İşte basit bir örneği *variadic Şablon sınıfı* tanım sözdizimi:

```cpp
template<typename... Arguments> class classname;
```

Bu örneklerde gösterildiği gibi tercihinize göre üç nokta çevresinde boşluk, parametre paketleri ve genişletmeleri için ekleyebilirsiniz:

```cpp
template<typename ...Arguments> class classname;
```

Veya bu:

```cpp
template<typename ... Arguments> class classname;
```

Bu makalede ilk örnekte gösterilen kuralı kullandığından emin olun (üç nokta iliştirildiği `typename`).

Önceki örneklerde, *bağımsız değişkenleri* bir parametre paketidir. Sınıf `classname` değişken sayıda bağımsız değişkenler, aşağıdaki örneklerde gösterildiği gibi kabul edebilir:

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Değişen sayıda bağımsız değişken sınıf tanımlarını kullanarak en az bir parametre gerektirebilir:

```cpp
template <typename First, typename... Rest> class classname;
```

İşte basit bir örneği *variadic şablon işlevi* söz dizimi:

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

*Bağımsız değişkenleri* sonraki bölümde gösterildiği gibi parametre paketi kullanmak için ardından Genişletilmiş **bağımsız değişken içeren şablonları anlama**.

Diğer tür değişen şablonu işlev sözdizimi mümkündür; ancak bunlarla sınırlı olmamak üzere, şu örnekleri içerir:

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

Gibi belirleyicilere **const** de izin verilir:

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Olarak variadic Şablon sınıfı tanımlarında olduğu gibi en az bir parametre gerektiren işlevleri yapabilirsiniz:

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Değişken içeren şablonları `sizeof...()` işleci (eski ilgisiz `sizeof()` işleci):

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

Bu makalede, parametre paketleri ve genişletmeleri olarak tanımlayan üç nokta yerleştirme daha önce açıklanan "sola parametre adının sağındaysa parametre paketi ve sağa parametre adının parametre paketlerini ayrı adlarda genişletir". Bu teknik geçerlidir ancak kod çevirisi kafa karıştırıcı olabilir. Göz önünde bulundurun:

- Bir şablon-parametre-listesi içinde (`template <parameter-list>`), `typename...` bir şablon parametre paketi sunar.

- Bir parametre-bildirim-yan tümcesinde (`func(parameter-list)`), bir işlev parametre paketi bir "en üst düzey" üç nokta tanıtır ve üç nokta konumlandırma önemlidir:

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- Bir parametre adı hemen sonra üç nokta görünür olduğunda, bir parametre paketi genişletme sahip.

## <a name="example"></a>Örnek

Değişen sayıda bağımsız değişken şablonu işlev mekanizmasını göstermenin en iyi yolu bir yeniden yazma bazı işlevlerini kullanmak için olan `printf`:

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

## <a name="output"></a>Çıkış

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
>  Değişen şablon işlevlerini bir araya getiren çoğu uygulamaları bazı formunun özyineleme kullanır, ancak geleneksel özyineleme biraz farklıdır.  Geleneksel özyineleme, aynı imzayı kullanarak kendisini çağıran bir işlev içerir. (Aşırı yüklenmiş veya şablon oluşturulmuş olabilir, ancak her seferinde aynı imza seçilir.) (Hemen her zaman Azalan) farklı sayıda bağımsız değişken kullanarak ve böylece farklı imza her zaman damgası bir değişken içeren işlevi şablonu çağırmak değişken içeren özyineleme gerektirir. "Temel durum" hala gereklidir ancak Özyinelemenin yapısı farklıdır.