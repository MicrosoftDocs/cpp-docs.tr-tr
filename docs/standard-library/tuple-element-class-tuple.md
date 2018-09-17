---
title: tuple_element sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::tuple_element
dev_langs:
- C++
helpviewer_keywords:
- std::tuple_element
ms.assetid: 4c51a6c1-ce81-462f-8c6c-291d69f2b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fb89f479320287ff238517cc649f199e0081ffa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716202"
---
# <a name="tupleelement-class"></a>tuple_element Sınıfı

Saran bir `tuple` öğesi. Uzmanlıkları kaydırma `array` öğeleri ve `pair` öğeleri.

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

*Index*<br/>
Belirtilen öğenin dizini.

*Tanımlama grubu*<br/>
Demet türü.

*Elem*<br/>
Bir dizi öğe türü.

*Boyutu*<br/>
Dizinin boyutu.

*T1*<br/>
Bir çift ilk öğenin türü.

*T2*<br/>
Bir çift ikinci öğe türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı `tuple_element` sahip iç içe geçmiş bir tür tanımı `type` diğer bir deyişle dizinindeki bir türe ilişkin bir eşanlam *dizin* türünün *demet*.

Typedef `tuple_element_t` için kullanışlı bir diğer addır `tuple_element<Index, Tuple>::type`.

Şablon sınıfı bir özelleştirmeye diziler için bir arabirim sağlar. bir `array` tanımlama grubu `Size` öğeleri, her biri aynı türe sahip. İç içe geçmiş bir tür tanımı her uzmanlığı olan `type` diğer bir deyişle türe ilişkin bir eşanlam *dizin* öğesinin `array`, korunur herhangi bir const-volatile niteliklere sahip.

Şablon uzmanlıkları için `pair` türleri her sağlayan bir tek üyeye typedef `type`, belirli bir konumda korunmuş const ve/veya volatile niteliklere sahip çiftindeki öğesinin türü için bir eşanlamlı olduğu. Typedef `tuple_element_t` için kullanışlı bir diğer addır `tuple_element<N, pair<T1, T2>>::type`.

Kullanım [get işlevi &lt;yardımcı programı&gt; ](../standard-library/utility-functions.md#get) belirtilen konumda ya da belirtilen bir türün öğesi döndürülecek.

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

**Başlık:** \<kayıt >

**Başlık:** \<array > (için dizi özelleştirme)

**Başlık:** \<yardımcı programı > (için çifti uzmanlıkları)

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Tanımlama grubu ](../standard-library/tuple-class.md)<br/>
