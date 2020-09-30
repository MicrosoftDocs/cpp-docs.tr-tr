---
title: initializer_list sınıfı
description: C++ standart kitaplığı 'nda, Visual Studio 'da Microsoft tarafından uygulanan initializer_list sınıfı için bir başvuru.
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
ms.openlocfilehash: 232855fbcac1e4df9af7cf956fda80201326a401
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504629"
---
# <a name="initializer_list-class"></a>initializer_list sınıfı

Her üyenin belirtilen türde olduğu öğe dizisine erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class initializer_list
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
İçinde depolanacak öğe veri türü `initializer_list` .

## <a name="remarks"></a>Açıklamalar

Bir `initializer_list` , bir örgü Başlatıcı listesi kullanılarak oluşturulabilir:

```cpp
initializer_list<int> i1{ 1, 2, 3, 4 };
```

Derleyici, `initializer_list` bir işlev imzası için gereken her seferinde, homojen Başlatıcı listelerini homojen öğesi ile dönüştürür `initializer_list` . Kullanma hakkında daha fazla bilgi için `initializer_list` bkz. [Tekdüzen başlatma ve temsilci oluşturucuları](../cpp/initializing-classes-and-structs-without-constructors-cpp.md)

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[initializer_list](#initializer_list)|Türünde bir nesne oluşturur `initializer_list` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|`value_type`|İçindeki öğelerin türü `initializer_list` .|
|`reference`|İçindeki bir öğeye başvuru sağlayan bir tür `initializer_list` .|
|`const_reference`|İçindeki bir öğeye sabit başvuru sağlayan bir tür `initializer_list` .|
|`size_type`|İçindeki öğe sayısını temsil eden bir tür `initializer_list` .|
|`iterator`|İçin Yineleyici sağlayan bir tür `initializer_list` .|
|`const_iterator`|İçin sabit bir yineleyici sağlayan bir tür `initializer_list` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|İçindeki ilk öğeye bir işaretçi döndürür `initializer_list` .|
|[erer](#end)|İçindeki son öğeden sonraki bir işaretçiyi döndürür `initializer_list` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `initializer_list` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<initializer_list>

**Ad alanı:** std

## <a name="initializer_listbegin"></a><a name="begin"></a> initializer_list:: Begin

İçindeki ilk öğeye bir işaretçi döndürür `initializer_list` .

```cpp
constexpr const InputIterator* begin() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Öğesinin ilk öğesine yönelik bir işaretçi `initializer_list` . Liste boşsa, işaretçi listenin başında ve sonunda aynı olur.

## <a name="initializer_listend"></a><a name="end"></a> initializer_list:: End

İçindeki son öğeden sonraki bir işaretçiyi döndürür `initializer list` .

```cpp
constexpr const InputIterator* end() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Listedeki son öğeden bir geçen bir işaretçi. Liste boşsa, listedeki ilk öğeye yönelik işaretçiyle aynı olur.

## <a name="initializer_listinitializer_list"></a><a name="initializer_list"></a> initializer_list:: initializer_list

Türünde bir nesne oluşturur `initializer_list` .

```cpp
constexpr initializer_list() noexcept;
initializer_list(const InputIterator First, const InputIterator Last);
```

### <a name="parameters"></a>Parametreler

*Adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

`initializer_list`, Belirtilen türdeki nesne dizisini temel alır. Kopyalama bir `initializer_list` listenin, aynı nesnelere işaret eden ikinci bir örneğini oluşturur; temeldeki nesneler kopyalanmaz.

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

## <a name="initializer_listsize"></a><a name="size"></a> initializer_list:: size

Listedeki öğe sayısını döndürür.

```cpp
constexpr size_t size() const noexcept;
```

### <a name="return-value"></a>Döndürülen değer

Listedeki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)
