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
ms.openlocfilehash: 61b5404d0f22cd902e35f6bee680df3c719804f2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456780"
---
# <a name="ltarraygt-functions"></a>&lt;dizi&gt; işlevleri

Dizi > üst bilgisi, dizi nesnelerinde çalışan iki üye olmayan `get` iki `swap`işlev içerir.  \<

|||
|-|-|
|[get](#get)|[Kur](#swap)|

## <a name="get"></a>Al

Dizinin belirtilen öğesine bir başvuru döndürür.

```cpp
template <int Index, class T, size_t N>
constexpr T& get(array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr const T& get(const array<T, N>& arr) noexcept;

template <int Index, class T, size_t N>
constexpr T&& get(array<T, N>&& arr) noexcept;
```

### <a name="parameters"></a>Parametreler

*İndeks*\
Öğe boşluğu.

*ŞI*\
Öğenin türü.

*NO*\
Dizideki öğelerin sayısı

*ARR*\
Seçilecek dizi.

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

## <a name="swap"></a>Kur

Öğesinin `std::swap` üye olmayan şablon özelleştirmesi iki **dizi** nesnesini değiştirir.

```cpp
template <class Ty, std::size_t N>
void swap(array<Ty, N>& left, array<Ty, N>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Öğenin türü.

*NO*\
Dizinin boyutu.

*tarafta*\
Takas edilecek ilk dizi.

*Right*\
Takas edilecek ikinci dizi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yürütülür `left.swap(right)`.

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

[\<dizi >](../standard-library/array.md)
