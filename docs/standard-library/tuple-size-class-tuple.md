---
title: tuple_size sınıfı;
ms.date: 11/04/2016
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
ms.openlocfilehash: 1c03c02dde3178a257a83720ff437f7981f5f7ed
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241548"
---
# <a name="tuplesize-class"></a>tuple_size sınıfı;

Öğe sayısı raporları, bir `tuple` içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
// TEMPLATE STRUCT tuple_size
template <class Tuple>
   struct tuple_size;

// number of elements in array
template <class Elem, size_t Size>
   struct tuple_size<array<Elem, Size>>
      : integral_constant<size_t, Size>;

// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>>
      : integral_constant<size_t, 2>

// size of tuple
template <class... Types>
   struct tuple_size<tuple<Types...>>
      : integral_constant<size_t, sizeof...(Types)>;

// size of const tuple
template <class Tuple>
   struct tuple_size<const Tuple>;

// size of volatile tuple
template <class Tuple>
   struct tuple_size<volatile Tuple>;

// size of const volatile tuple
template <class Tuple>
   struct tuple_size<const volatile Tuple>;
```

```cpp
template <class T> inline constexpr size_t tuple_size_v = tuple_size<T>::value;
```

### <a name="parameters"></a>Parametreler

*Tanımlama grubu*\
Demet türü.

*Elem*\
Dizi öğelerinin türü.

*Boyutu*\
Dizinin boyutu.

*T1*\
Çiftin ilk üye türü.

*T2*\
Çiftin ikinci üyenin türü.

*Türleri*\
Tanımlama grubu öğelerinin türleri.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı üyesinin `value` diğer bir deyişle, değeri olan tanımlama grubu türüyle kapsamını integral sabit ifadesi *demet*.

Şablon uzmanlığı diziler için bir üyenin `value` değeri olan diğer bir deyişle bir integral sabit ifadesi *boyutu*, dizinin boyutunu olduğu.

Şablon uzmanlığı çifti için bir üyenin `value` değeri 2 olan diğer bir deyişle bir integral sabit ifadesi.

## <a name="example"></a>Örnek

```cpp
#include <tuple>
#include <iostream>

using namespace std;

typedef tuple<int, double, int, double> MyTuple;
int main()
{
    MyTuple c0(0, 1.5, 2, 3.7);

    // display contents "0 1 2 3"
    cout << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size "4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
0 1.5 2 3.7
4
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kayıt >

**Başlık:** \<array > (için dizi özelleştirme)

**Başlık:** \<yardımcı programı > (için çifti özelleştirme)

**Namespace:** std
