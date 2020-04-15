---
title: boyer_moore_horspool_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: 4d404b414ad632e02be5f4e9fad0e22cefb86ce2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366786"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcher sınıfı

Sınıf, `boyer_moore_horspool_searcher` nesnenin oluşturucusunda belirtilen bir sırayı aramak için Boyer-Moore-Horspool algoritmasını kullanan bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrı işlecine sağlanan başka bir sıra içinde yapılır. Bu sınıf std aşırı yükleri birine bir parametre olarak [geçirilir::search](algorithm-functions.md#search).

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    class RandomAccessIterator,
    class Hash = hash<typename iterator_traits<RandomAccessIterator>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_horspool_searcher
{
    boyer_moore_horspool_searcher(
        RandomAccessIterator pat_first,
        RandomAccessIterator pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>Üyeler

| | |
| - | - |
| **Oluşturucu** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **İşleçler** | |
| [işleç()](#operator-call) | |

## <a name="boyer_moore_horspool_searcher-constructor"></a><a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher yapıcı

Aramak için `boyer_moore_horspool_searcher` sırayı, karma işlev nesnesini ve eşitlik yüklemini kullanarak bir işlev nesnesi oluşturuyor.

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parametreler

*pat_first*\
Aranacak dizinin ilk öğesi.

*pat_last*\
Aranacak dizinin sonu.

*Hf*\
Sıra öğelerini karmalamak için kullanılan çağrılabilir bir nesne.

*Pred*\
Sıra öğeleri için isteğe bağlı eşitlik karşılaştırma yüklemi. Eşitlik karşılaştırma türü belirtilmemişse, varsayılan `std::equal_to`değer.

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate,* *Hash*veya *RandomAccessIterator* türlerinin kopya oluşturucusu veya *BinaryPredicate* veya *Hash'ın*çağrı operatörü tarafından atılan herhangi bir özel durum atar.

Bu sınıf C++17'de yenidir.

## <a name="operator"></a><a name="operator-call"></a>işleç()

İşlev nesnesinin çağrı işleci. Oluşturucuya belirtilen `[first, last)` sırayı bağımsız değişken dizisi içinde arar.

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dizinin içinde aramak için ilk öğesi.

*Son*\
İçinde aramak için sıranın sonu.

### <a name="remarks"></a>Açıklamalar

Arama deseni `[pat_first, pat_last)` boşsa, döndürür. `make_pair(first, first)` Arama deseni bulunmazsa, döndürür. `make_pair(last, last)` Aksi takdirde, bir çift yineleyiciyi yüklem `[first, last)` `[pat_first, pat_last)` *pred'ine*göre eşit olan bir dizinin başına ve sonuna döndürür.

Bu sınıf C++17'de yenidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<fonksiyonel>](functional.md)\
[algoritma fonksiyonları](algorithm-functions.md)\
[boyer_moore_searcher sınıfı](boyer-moore-searcher-class.md)\
[std::arama](algorithm-functions.md#search)
