---
title: initializer_list sınıfı
description: Microsoft tarafından Visual Studio'da uygulandığı gibi, C++ Standart kitaplığındaki initializer_list sınıfı için bir başvuru.
ms.date: 01/28/2020
f1_keywords:
- initializer_list/std::initializer_list::initializer_list
- initializer_list/std::initializer_list::begin
- initializer_list/std::initializer_list::end
- initializer_list/std::initializer_list::size
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
helpviewer_keywords:
- std::initializer_list::initializer_list
- std::initializer_list::begin
- std::initializer_list::end
- std::initializer_list::size
ms.openlocfilehash: b1d33ce484948e731f8d3062b7a99df06ef26073
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373355"
---
# <a name="initializer_list-class"></a>initializer_list sınıfı

Her üyenin belirtilen türden olduğu bir dizi öğeye erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

*Türü*\
Depolanacak öğe veri `initializer_list`türü.

## <a name="remarks"></a>Açıklamalar

Bir `initializer_list` braced initializer listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici, homojen öğelerle `initializer_list` braced initializer listelerini işlev imzası nın `initializer_list`bir . Kullanma `initializer_list`hakkında daha fazla bilgi için, [Bkz. Tekdüzen başlatma ve kurucuları delegating](../cpp/uniform-initialization-and-delegating-constructors.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](#initializer_list)|Türünde `initializer_list`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|`value_type`|'deki öğelerin `initializer_list`türü.|
|`reference`|`initializer_list`Bir öğeye başvuru sağlayan bir tür.|
|`const_reference`|`initializer_list`Bir öğeye sabit bir başvuru sağlayan bir tür.|
|`size_type`|`initializer_list`'deki öğe sayısını temsil eden bir tür.|
|`iterator`|`initializer_list`Için bir yineleyici sağlayan bir tür.|
|`const_iterator`|Için sabit bir yineleyici sağlayan bir `initializer_list`tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|Bir `initializer_list`'deki ilk öğeye işaretçi döndürür|
|[Son -unda](#end)|Bir `initializer_list`işaretçiyi bir 'deki son öğeyi geçmiş bir işaretçiye döndürür|
|[Boyutu](#size)|`initializer_list`'deki öğe sayısını verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<initializer_list>

**Ad alanı:** std

## <a name="initializer_listbegin"></a><a name="begin"></a>initializer_list::başla

Bir `initializer_list`'deki ilk öğeye işaretçi döndürür

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

`initializer_list`'nin ilk öğesine işaretçi Liste boşsa, işaretçi listenin başı ve sonu için aynıdır.

## <a name="initializer_listend"></a><a name="end"></a>initializer_list::sonu

Bir `initializer list`işaretçiyi bir 'deki son öğeyi geçmiş bir işaretçiye döndürür

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Listedeki son öğeyi geçmiş bir işaretçi. Liste boşsa, listedeki ilk öğenin işaretçisi ile aynıdır.

## <a name="initializer_listinitializer_list"></a><a name="initializer_list"></a>initializer_list:initializer_list

Türünde `initializer_list`bir nesne oluşturuyor.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Kopyalanacak öğeler aralığındaki ilk öğenin konumu.

*Son*\
İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.

### <a name="remarks"></a>Açıklamalar

An, `initializer_list` belirtilen türden bir dizi nesneyi temel alır. Kopyalama, `initializer_list` aynı nesneleri işaret eden bir listenin ikinci bir örneğini oluşturur; temel nesneler kopyalanmıyor.

### <a name="example"></a>Örnek

```cpp
// initializer_list_class.cpp
// compile with: /EHsc
#include <initializer_list>
#include <iostream>

int main()
{
    using namespace std;
    // Create an empty initializer_list c0
    initializer_list <int> c0;

    // Create an initializer_list c1 with 1 element
    initializer_list <int> c1{ 3 };

    // Create an initializer_list c2 with 5 elements
    initializer_list <int> c2{ 5, 4, 3, 2, 1 };

    // Create a copy, initializer_list c3, of initializer_list c2
    initializer_list <int> c3(c2);

    // Create a initializer_list c4 by copying the range c3[ first,  last)
    const int* c3_ptr = c3.begin();
    c3_ptr++;
    c3_ptr++;
    initializer_list <int> c4(c3.begin(), c3_ptr);

    // Move initializer_list c4 to initializer_list c5
    initializer_list <int> c5(move(c4));

    cout << "c1 =";
    for (auto c : c1)
        cout << " " << c;
    cout << endl;

    cout << "c2 =";
    for (auto c : c2)
        cout << " " << c;
    cout << endl;

    cout << "c3 =";
    for (auto c : c3)
        cout << " " << c;
    cout << endl;

    cout << "c5 =";
    for (auto c : c5)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 3
c2 = 5 4 3 2 1
c3 = 5 4 3 2 1
c5 = 5 4
```

## <a name="initializer_listsize"></a><a name="size"></a>initializer_list::boyut

Listedeki öğe sayısını verir.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Listedeki öğe sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)
