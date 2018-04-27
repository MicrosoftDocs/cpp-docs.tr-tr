---
title: tuple_element sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- utility/std::tuple_element
dev_langs:
- C++
helpviewer_keywords:
- std::tuple_element
ms.assetid: 4c51a6c1-ce81-462f-8c6c-291d69f2b77c
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08a7ab97d397022f86a390622803c38752f78808
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="tupleelement-class"></a>tuple_element Sınıfı

Saran bir `tuple` öğesi. Özelleştirmeleri kaydırma `array` öğeleri ve `pair` öğeleri.

## <a name="syntax"></a>Sözdizimi

```cpp
// CLASS tuple_element (find element by index)
template <size_t Index, class Tuple>
   struct tuple_element;

// tuple_element for const
template <size_t Index, class Tuple>
   struct tuple_element<Index, const Tuple>;

// tuple_element for volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, volatile Tuple>;

// tuple_element for const volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, const volatile Tuple>;

// Helper typedef
template <size_t Index, class Tuple>
   using tuple_element_t = typename tuple_element<Index, Tuple>::type;

// Specialization for arrays
template <size_t Index, class Elem, size_t Size>
   struct tuple_element<Index, array<Elem, Size>>;

// Specializations for pairs
// struct to determine type of element 0 in pair
template <class T1, class T2>
   struct tuple_element<0, pair<T1, T2>>;

// struct to determine type of element 1 in pair
template <class T1, class T2>
   struct tuple_element<1, pair<T1, T2>>;
```

### <a name="parameters"></a>Parametreler

*Dizin* belirtilen öğenin dizini.

*Tuple* kayıt türü.

*Elem* dizi öğenin türü.

*Boyutu* dizinin boyutu.

*T1* çifti ilk öğe türü.

*T2* çifti ikinci öğe türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı `tuple_element` iç içe geçmiş typedef sahip `type` eşanlamlısı dizinindeki türü için başka bir deyişle `Index` türünün `Tuple`.

Typedef `tuple_element_t` için kullanışlı bir diğer adı olan `tuple_element<Index, Tuple>::type`.

Diziler için Şablon sınıfı özelleştirmesi için bir arabirim sunan bir `array` tanımlama grubu olarak `Size` öğeleri, her biri aynı türe sahip. Bir iç içe geçmiş typedef her uzmanlık sahip `type` eşanlamlısı türü için başka bir deyişle `Index` öğesinin `array`, korunan tüm const geçici nitelikleri ile.

Şablon özelleştirmeleri için `pair` türleri her sağlayan bir tek üye typedef `type`, çifti korunarak const ve/veya volatile nitelikleri ile belirtilen konumda öğesinin türü eşanlamlısı olduğu. Typedef `tuple_element_t` için kullanışlı bir diğer adı olan `tuple_element<N, pair<T1, T2>>::type`.

Kullanım [get işlevi &lt;yardımcı programı&gt; ](../standard-library/utility-functions.md#get) öğe belirtilen konuma veya belirtilen bir türün dönün.

## <a name="example"></a>Örnek

```cpp
#include <tuple>
#include <string>
#include <iostream>

using namespace std;
typedef tuple<int, double, string> MyTuple;

int main() {
    MyTuple c0{ 0, 1.5, "Tail" };

    tuple_element_t<0, MyTuple> val = get<0>(c0); //get by index
    tuple_element_t<1, MyTuple> val2 = get<1>(c0);
    tuple_element_t<2, MyTuple> val3 = get<string>(c0); // get by type

    cout << val << " " << val2 << " " << val3 << endl;
}
```

```Output
0 1.5 Tail
```

## <a name="example"></a>Örnek

```cpp
#include <array>
#include <iostream>

using namespace std;
typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    for (const auto& e : c0)
    {
        cout << " " << e;
    }
    cout << endl;

    // display first element " 0"
    tuple_element<0, MyArray>::type val = c0.front();
    cout << " " << val << endl;
}
```

```Output
 0 1 2 3
 0
```

## <a name="example"></a>Örnek

```cpp
#include <utility>
#include <iostream>

using namespace std;

typedef pair<int, double> MyPair;
int main() {
    MyPair c0(0, 1.333);

    // display contents " 0 1"
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // display first element " 0" by index
    tuple_element<0, MyPair>::type val = get<0>(c0);
    cout << " " << val;

    // display second element by type
    tuple_element<1, MyPair>::type val2 = get<double>(c0);
    cout << " " << val2 << endl;
}
```

```Output
 0 1.333
 0 1.333
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<tanımlama grubu > **üstbilgisi:** \<dizi > (için dizi uzmanlık) **üstbilgisi:** \<yardımcı programı > (için çifti özelleştirmeleri)  **Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Tanımlama grubu ](../standard-library/tuple-class.md)<br/>
