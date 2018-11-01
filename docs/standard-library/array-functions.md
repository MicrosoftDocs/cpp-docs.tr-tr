---
title: '&lt;dizi&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- array/std::array::get
- array/std::get
- array/std::swap
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
helpviewer_keywords:
- std::array [C++], get
- std::get [C++]
- std::swap [C++]
ms.openlocfilehash: 719377be2ac130100e3f9e9ea608c5c27be3101f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562311"
---
# <a name="ltarraygt-functions"></a>&lt;dizi&gt; işlevleri

\<Dizi > üst bilgi içeren iki üye olmayan işlevleri `get` ve `swap`, üzerinde çalışan **dizi** nesneleri.

|||
|-|-|
|[get](#get)|[değiştirme](#swap)|

## <a name="get"></a>  Al

Belirtilen öğe dizinin bir başvuru döndürür.

```cpp
template <int Index, class T, size_t N>
constexpr T& get(array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr const T& get(const array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr T&& get(array<T, N>&& arr) noexcept;
```

### <a name="parameters"></a>Parametreler

*Index*<br/>
Öğe uzaklığı.

*T*<br/>
Öğenin türü.

*N*<br/>
Dizideki öğelerin sayısı

*arr*<br/>
Aralarından seçim yapabileceğiniz dizisi.

### <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

using namespace std;

typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (const auto& e : c0)
    {
        cout << " " << e;
    }
    cout << endl;

    // display odd elements " 1 3"
    cout << " " << get<1>(c0);
    cout << " " << get<3>(c0) << endl;
}
```

```Output
0 1 2 3
1 3
```

## <a name="swap"></a>  değiştirme

Üye olmayan şablon özelleştirmesi `std::swap` iki değiştirir **dizi** nesneleri.

```cpp
template <class Ty, std::size_t N>
void swap(array<Ty, N>& left, array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Öğenin türü.

*N*<br/>
Dizinin boyutu.

*Sol*<br/>
Takas etmek için ilk dizi.

*sağ*<br/>
Takas etmek için ikinci dizi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütür `left.swap(right)`.

### <a name="example"></a>Örnek

```cpp
// std__array__swap.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
0 1 2 3
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Array >](../standard-library/array.md)<br/>
