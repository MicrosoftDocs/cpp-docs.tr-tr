---
title: default_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 2c8b93b83b271f787c993f789e1a68f84a60f016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368921"
---
# <a name="default_searcher-class"></a>default_searcher Sınıfı

A, `default_searcher` nesnenin oluşturucusunda belirtilen bir sırayı arayan işlemler için bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrı işlecine sağlanan başka bir sıra içinde yapılır. Çağırır `default_searcher` [std::arama](algorithm-functions.md#search) gerçekleştirmek için arama.

## <a name="syntax"></a>Sözdizimi

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

| | |
| - | - |
| **Oluşturucu** | |
| [default_searcher](#default-searcher-constructor) | |
| **İşleçler** | |
| [işleç()](#operator-call) | |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a>default_searcher yapıcı

Aramak için `default_searcher` sırayı ve eşitlik yüklemini kullanarak bir işlev nesnesi oluşturuyor.

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
Aranacak dizinin ilk öğesi.

*pat_last*\
Aranacak dizinin sonu.

*Pred*\
Sıra öğeleri için isteğe bağlı eşitlik karşılaştırma yüklemi. Eşitlik karşılaştırma türü belirtilmemişse, varsayılan `std::equal_to`değer.

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate* veya *ForwardIterator* türlerinin kopya oluşturucusu tarafından atılan herhangi bir özel durum atar.

Bu sınıf C++17'de yenidir. C++20 yapıcı `constexpr`yaptı.

## <a name="operator"></a><a name="operator-call"></a>işleç()

İşlev işlecinin çağrı işleci. Oluşturucuya belirtilen `[first, last)` sırayı bağımsız değişken dizisi içinde arar.

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

*Ilk*\
Dizinin içinde aramak için ilk öğesi.

*Son*\
İçinde aramak için sıranın sonu.

### <a name="remarks"></a>Açıklamalar

Yineleyicilerin bir çiftini döndürür. İlk yineleyici *i* etkili bir sonucudur:

`std::search( first, last, pat_first, pat_last, pred )`.

Çiftin ikinci *yineleyicisi i** *son*ise *sondur.* Aksi takdirde, etkili bir sonucu:

`std::next( i, std::distance( pat_first, pat_last ))`.

Bu sınıf C++17'de yenidir. C++20 arama işleci `constexpr`yaptı.

## <a name="see-also"></a>Ayrıca bkz.

[\<fonksiyonel>](functional.md)\
[algoritma fonksiyonları](algorithm-functions.md)\
[std::arama](algorithm-functions.md#search)
