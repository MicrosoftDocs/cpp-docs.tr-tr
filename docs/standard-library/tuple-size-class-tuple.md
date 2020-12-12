---
description: 'Hakkında daha fazla bilgi edinin: tuple_size Class;'
title: tuple_size Sınıfı;
ms.date: 11/04/2016
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
ms.openlocfilehash: e825acc02e27a8d0c1ae29e5bfcf4ac1e0a708b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168884"
---
# <a name="tuple_size-class"></a>tuple_size Sınıfı;

İçerdiği öğelerin sayısını raporlar `tuple` .

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

*Le*\
Kayıt düzeni türü.

*Elem*\
Dizi öğelerinin türü.

*Boyutla*\
Dizinin boyutu.

*T1*\
Çiftin ilk üyesinin türü.

*T2*\
Çiftin ikinci üyesinin türü.

*Türü*\
Demet öğelerinin türleri.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, `value` değeri demet türü *tanımlama grubu* olan bir integral sabit ifadesi olan bir üyeye sahiptir.

Diziler için şablon özelleştirmesi, `value` değeri *Boyut* olan ve dizinin boyutu olan bir integral sabit ifadesi olan bir üyeye sahiptir.

Çiftin şablon özelleştirmesi, `value` değeri 2 olan integral sabit ifadesi olan bir üyeye sahiptir.

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

**Üst bilgi:**\<tuple>

**Üst bilgi:** \<array> (dizi özelleştirmesi için)

**Üst bilgi:** \<utility> (çift özelleşme için)

**Ad alanı:** std
