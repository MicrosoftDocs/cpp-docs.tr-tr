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
ms.openlocfilehash: a3941464c80d254b6675e1982dac952c3f29a0f9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="initializerlist-class"></a>initializer_list sınıfı

Her üye belirtilen türde olduğu öğeleri dizisi erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Type`|Öğenin veri türü depolanmasına `initializer_list`.|


## <a name="remarks"></a>Açıklamalar

Bir `initializer_list` küme ayracı içine alınan başlatıcı listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici homojen elemanlara ile küme ayracı içine alınan Başlatıcı Listeleri dönüştüren bir `initializer_list` her işlev imzası gerektiren bir `initializer_list`. Kullanma hakkında daha fazla ayrıntı için `initializer_list`, bkz: [tek düzen başlatma ve oluşturucuları temsilci seçme](../cpp/uniform-initialization-and-delegating-constructors.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](../standard-library/forward-list-class.md#forward_list)|Türünde bir nesne oluşturur `initializer_list`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|value_type|Öğelerin türü `initializer_list`.|
|reference|Bir öğedeki başvuru sağlayan bir türü `initializer_list`.|
|const_reference|Bir öğedeki sabit başvuru sağlayan bir türü `initializer_list`.|
|size_type|Öğe sayısını temsil eden bir tür `initializer_list`.|
|iterator|Yineleyici için sağlayan bir türü `initializer_list`.|
|const_iterator|İçin sabit bir yineleyici sağlayan bir türü `initializer_list`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Başlangıç](#begin)|İlk öğe için bir işaretçi döndüren bir `initializer_list`.|
|[Bitiş](#end)|Bir son öğesi geçmiş işaretçi döndüren bir `initializer_list`.|
|[Boyutu](#size)|Öğelerin sayısını döndürür `initializer_list`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<initializer_list >

**Namespace:** std

## <a name="begin"></a>  initializer_list::Begin

İlk öğe için bir işaretçi döndüren bir `initializer_list`.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğesi için bir işaretçi `initializer_list`. Liste boşsa, işaretçi başlangıcını ve bitişini listesinin aynıdır.

### <a name="remarks"></a>Açıklamalar

## <a name="end"></a>  initializer_list::End

Bir son öğesi geçmiş işaretçi döndüren bir `initializer list`.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir listenin son öğesi geçmiş. Liste boşsa, bu listede ilk öğe işaretçisine aynıdır.

## <a name="initializer_list"></a>  initializer_list::initializer_list

Türünde bir nesne oluşturur `initializer_list`.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|

### <a name="remarks"></a>Açıklamalar

Bir `initializer_list` belirtilen türdeki nesneleri dizisi üzerinde temel alır. Kopyalama bir `initializer_list` aynı nesnelere; işaret eden bir liste ikinci bir örneğini oluşturur arka plandaki nesneleri kopyalanmadı.

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
