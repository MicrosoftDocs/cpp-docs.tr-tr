---
title: default_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 307fc6da3b383690e0b65bff2a72f386a37d6711
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039696"
---
# <a name="default_searcher-class"></a>default_searcher sınıfı

, `default_searcher` Nesne oluşturucusunda belirtilen bir diziyi Arayıcı işlemler için bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrısı işlecine belirtilen başka bir sıra içinde yapılır. `default_searcher`Aramayı gerçekleştirmek için [std:: Search](algorithm-functions.md#search) çağırır.

## <a name="syntax"></a>Syntax

```cpp
template <class ForwardIterator, class BinaryPredicate = equal_to<>>
class default_searcher
{
    default_searcher(
        ForwardIterator pat_first,
        ForwardIterator pat_last,
        BinaryPredicate pred = BinaryPredicate());

    template <class ForwardIterator2>
    pair<ForwardIterator2, ForwardIterator2> operator()(
        ForwardIterator2 first,
        ForwardIterator2 last) const;
};
```

## <a name="members"></a>Üyeler

| Üye | Description |
| - | - |
| **Oluşturucu** | |
| [default_searcher](#default-searcher-constructor) | Bir Arayıcının örneği oluşturur. |
| **İşleçler** | |
| [operator ()](#operator-call) | İşlemi sırayla çağırır. |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a> default_searcher Oluşturucusu

`default_searcher`Aranacak diziyi ve bir eşitlik koşulunu kullanarak bir işlev nesnesi oluşturur.

```cpp
default_searcher(                   // C++17
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());

constexpr default_searcher(         // C++20
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parametreler

*pat_first*\
Arama yapılacak dizinin ilk öğesi.

*pat_last*\
Aranacak dizinin sonu.

*pred*\
Dizi öğeleri için isteğe bağlı eşitlik karşılaştırma koşulu. Bir eşitlik karşılaştırma türü belirtilmemişse, varsayılan olur `std::equal_to` .

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate* veya *ForwardIterator* türlerinin kopya Oluşturucusu tarafından oluşturulan özel durumu oluşturur.

Bu sınıf C++ 17 ' de yenidir. C++ 20 Oluşturucu yaptı **`constexpr`** .

## <a name="operator"></a><a name="operator-call"></a> operator ()

İşlev işlecinin Call işleci. Oluşturucuya belirtilen dizi için bağımsız değişken sırası içinde arar `[first, last)` .

```cpp
template <class ForwardIterator2>   // C++17
pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;

template <class ForwardIterator2>   // C++20
constexpr pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
İçinde arama yapılacak dizinin ilk öğesi.

*soyadına*\
İçinde arama yapılacak dizinin sonu.

### <a name="remarks"></a>Açıklamalar

Yineleyicilerin bir çiftini döndürür. İlk *Yineleyici, öğesinin etkili* sonucudur:

`std::search( first, last, pat_first, pat_last, pred )`.

İkilinin ikinci yineleyicisi *en son* *bir*. *i* Aksi takdirde, bunun etkili sonucu:

`std::next( i, std::distance( pat_first, pat_last ))`.

Bu sınıf C++ 17 ' de yenidir. C++ 20 çağrı işlecini yaptı **`constexpr`** .

## <a name="see-also"></a>Ayrıca bkz.

[\<functional>](functional.md)\
[algoritma işlevleri](algorithm-functions.md)\
[std:: arama](algorithm-functions.md#search)
