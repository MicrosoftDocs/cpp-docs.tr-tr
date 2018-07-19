---
title: initializer_list sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- initializer_list/std::initializer_list::initializer_list
- initializer_list/std::initializer_list::begin
- initializer_list/std::initializer_list::end
- initializer_list/std::initializer_list::size
dev_langs:
- C++
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::initializer_list::initializer_list
- std::initializer_list::begin
- std::initializer_list::end
- std::initializer_list::size
ms.workload:
- cplusplus
ms.openlocfilehash: 11014748dcbfa105d111e9e2a8d83fc57d0cb405
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954060"
---
# <a name="initializerlist-class"></a>initializer_list sınıfı

Öğeleri her üyenin belirtilen tür olduğu bir dizi erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Türü*|İçinde depolanacak öğe veri türü `initializer_list`.|


## <a name="remarks"></a>Açıklamalar

Bir `initializer_list` bir küme ayracıyla belirtilen başlatıcı listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici homojen öğelerle küme ayracıyla belirtilen Başlatıcı Listeleri dönüştüren bir `initializer_list` her işlev imzası gerektiren bir `initializer_list`. Kullanma hakkında daha fazla ayrıntı için `initializer_list`, bkz: [tek düzen başlatma ve oluşturucuları temsilci olarak görevlendirme](../cpp/uniform-initialization-and-delegating-constructors.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](../standard-library/forward-list-class.md#forward_list)|Türünde bir nesne oluşturur `initializer_list`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|value_type|Öğelerin türünü `initializer_list`.|
|reference|İçinde bir öğeye başvuru sağlayan bir tür `initializer_list`.|
|const_reference|Bir öğe için sabit bir başvuru sağlayan bir tür `initializer_list`.|
|size_type|İçindeki öğelerin sayısını temsil eden bir tür `initializer_list`.|
|iterator|İçin bir yineleyici sağlayan tür `initializer_list`.|
|const_iterator|İçin sabit bir yineleyici sağlayan tür `initializer_list`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|İçindeki ilk öğeye bir işaretçi döndüren bir `initializer_list`.|
|[Son](#end)|Son öğeden bir öncekine işaretçi döndüren bir `initializer_list`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `initializer_list`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<initializer_list >

**Namespace:** std

## <a name="begin"></a>  initializer_list::Begin

İçindeki ilk öğeye bir işaretçi döndüren bir `initializer_list`.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Öğesinin ilk öğesinin işaretçisi `initializer_list`. Liste boş ise, işaretçi başlangıcını ve bitişini listesinin için aynıdır.

### <a name="remarks"></a>Açıklamalar

## <a name="end"></a>  initializer_list::End

Son öğeden bir öncekine işaretçi döndüren bir `initializer list`.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki son öğeden bir öncekine bir işaretçi. Liste boşsa, bu listedeki ilk öğeye işaretçi aynıdır.

## <a name="initializer_list"></a>  initializer_list::initializer_list

Türünde bir nesne oluşturur `initializer_list`.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ilk*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Son*|Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.|

### <a name="remarks"></a>Açıklamalar

Bir `initializer_list` belirtilen türün nesne dizisini temel alır. Kopyalama bir `initializer_list` aynı nesneleri gösteren bir listenin ikinci bir örneğini oluşturur temel nesneler kopyalanmaz.

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

    cout << "c4 =";
    for (auto c : c4)
        cout << " " << c;
    cout << endl;

    cout << "c5 =";
    for (auto c : c5)
        cout << " " << c;
    cout << endl;
}
```

```Output
c1 = 3c2 = 5 4 3 2 1c3 = 5 4 3 2 1c4 = 5 4c5 = 5 4
```

## <a name="size"></a>  initializer_list::size

Listedeki öğe sayısını döndürür.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)<br/>
