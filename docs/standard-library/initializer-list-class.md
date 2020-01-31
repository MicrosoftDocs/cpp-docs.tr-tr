---
title: initializer_list sınıfı
description: C++ Standart kitaplıkta, Visual Studio 'da Microsoft tarafından uygulanan initializer_list sınıfı için bir başvuru.
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
ms.openlocfilehash: 6be51835958a07162ce22ff9d619fb793102669f
ms.sourcegitcommit: 684181561490e0d1955cf601d222f67f09af6d00
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2020
ms.locfileid: "76894339"
---
# <a name="initializer_list-class"></a>initializer_list sınıfı

Her üyenin belirtilen türde olduğu öğe dizisine erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

*Tür*\
`initializer_list`depolanacak öğe veri türü.

## <a name="remarks"></a>Açıklamalar

Bir `initializer_list`, bir örgü Başlatıcı listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici, işlev imzası bir `initializer_list`gerektirdiğinde, homo, homojen Başlatıcı listelerini `initializer_list` olarak dönüştürür. `initializer_list`kullanma hakkında daha fazla bilgi için bkz. [Tekdüzen başlatma ve temsilci oluşturucuları](../cpp/uniform-initialization-and-delegating-constructors.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](#initializer_list)|`initializer_list`türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|`value_type`|`initializer_list`öğelerin türü.|
|`reference`|`initializer_list`bir öğeye başvuru sağlayan bir tür.|
|`const_reference`|`initializer_list`bir öğeye sabit başvuru sağlayan bir tür.|
|`size_type`|`initializer_list`öğe sayısını temsil eden bir tür.|
|`iterator`|`initializer_list`için Yineleyici sağlayan bir tür.|
|`const_iterator`|`initializer_list`için sabit bir yineleyici sağlayan bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|`initializer_list`ilk öğeye yönelik bir işaretçi döndürür.|
|[erer](#end)|Bir `initializer_list`son öğeden geçmiş bir işaretçi döndürür.|
|[boyutla](#size)|`initializer_list`öğe sayısını döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<initializer_list >

**Ad alanı:** std

## <a name="begin"></a>initializer_list:: Begin

`initializer_list`ilk öğeye yönelik bir işaretçi döndürür.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Dönüş değeri

`initializer_list`ilk öğesine yönelik bir işaretçi. Liste boşsa, işaretçi listenin başında ve sonunda aynı olur.

## <a name="end"></a>initializer_list:: End

Bir `initializer list`son öğeden geçmiş bir işaretçi döndürür.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Dönüş değeri

Listedeki son öğeden bir geçen bir işaretçi. Liste boşsa, listedeki ilk öğeye yönelik işaretçiyle aynı olur.

## <a name="initializer_list"></a>initializer_list:: initializer_list

`initializer_list`türünde bir nesne oluşturur.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*İlk*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Son*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

`initializer_list`, belirtilen türdeki nesne dizisini temel alır. `initializer_list` kopyalama, aynı nesnelere işaret eden bir listenin ikinci bir örneğini oluşturur; temel alınan nesneler kopyalanmaz.

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

## <a name="size"></a>initializer_list:: size

Listedeki öğe sayısını döndürür.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Dönüş değeri

Listedeki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)
