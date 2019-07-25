---
title: initializer_list sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: acd11f3b3a3bf0ba17e34a802cc8988410e17b12
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455356"
---
# <a name="initializerlist-class"></a>initializer_list sınıfı

Her üyenin belirtilen türde olduğu öğe dizisine erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|İçinde depolanacak öğe veri türü `initializer_list`.|

## <a name="remarks"></a>Açıklamalar

Bir `initializer_list` , bir örgü Başlatıcı listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici, bir `initializer_list` `initializer_list`işlev imzası için gereken her seferinde, homojen Başlatıcı listelerini homojen öğesi ile dönüştürür. Kullanma `initializer_list`hakkında daha fazla bilgi için bkz. [Tekdüzen başlatma ve temsilci oluşturucuları](../cpp/uniform-initialization-and-delegating-constructors.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](../standard-library/forward-list-class.md#forward_list)|Türünde `initializer_list`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|value_type|İçindeki öğelerin türü `initializer_list`.|
|reference|İçindeki bir öğeye başvuru sağlayan bir tür `initializer_list`.|
|const_reference|İçindeki bir öğeye sabit başvuru sağlayan bir tür `initializer_list`.|
|size_type|İçindeki öğe sayısını temsil eden bir tür `initializer_list`.|
|iterator|İçin Yineleyici sağlayan bir tür `initializer_list`.|
|const_iterator|İçin sabit bir yineleyici sağlayan bir tür `initializer_list`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|İçindeki ilk öğeye bir işaretçi döndürür `initializer_list`.|
|[erer](#end)|İçindeki son öğeden sonraki bir işaretçiyi döndürür `initializer_list`.|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `initializer_list`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<initializer_list >

**Ad alanı:** std

## <a name="begin"></a>initializer_list:: Begin

İçindeki ilk öğeye bir işaretçi döndürür `initializer_list`.

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Öğesinin ilk öğesine `initializer_list`yönelik bir işaretçi. Liste boşsa, işaretçi listenin başında ve sonunda aynı olur.

### <a name="remarks"></a>Açıklamalar

## <a name="end"></a>initializer_list:: End

İçindeki son öğeden sonraki bir işaretçiyi döndürür `initializer list`.

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki son öğeden bir geçen bir işaretçi. Liste boşsa, bu, listedeki ilk öğeye yönelik işaretçiyle aynıdır.

## <a name="initializer_list"></a>initializer_list::initializer_list

Türünde `initializer_list`bir nesne oluşturur.

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Adı*|Kopyalanacak öğe aralığındaki ilk öğenin konumu.|
|*Soyadına*|Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.|

### <a name="remarks"></a>Açıklamalar

`initializer_list` , Belirtilen türdeki nesne dizisini temel alır. Kopyalama bir `initializer_list` listenin, aynı nesnelere işaret eden ikinci bir örneğini oluşturur; temeldeki nesneler kopyalanmaz.

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

## <a name="size"></a>initializer_list:: size

Listedeki öğe sayısını döndürür.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)
