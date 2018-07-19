---
title: tuple_size sınıfı; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c03c47502fdd9309b3d6553c3f46f9685d4eaa9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958272"
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

### <a name="parameters"></a>Parametreler

*Tanımlama grubu*  
Demet türü.

*Elem*  
Dizi öğelerinin türü.

*Boyutu*  
Dizinin boyutu.

*T1*  
Çiftin ilk üye türü.

*T2*  
Çiftin ikinci üyenin türü.

*Türler*  
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

    // display contents " 0 1 2 3"
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size " 4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
 0 1.5 2 3.7
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<tanımlama grubu > **başlığı:** \<dizi > (için dizi özelleştirme) **başlığı:** \<yardımcı programı > (için çifti özelleştirme)

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Tanımlama grubu >](../standard-library/tuple.md)<br/>
[Tanımlama grubu](../standard-library/tuple-class.md)<br/>
[tuple_element sınıfı](../standard-library/tuple-element-class-tuple.md)<br/>
