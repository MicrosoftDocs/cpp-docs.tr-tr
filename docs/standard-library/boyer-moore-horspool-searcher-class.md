---
title: boyer_moore_horspool_searcher sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: a6b08e65419f002b7176e41131770e1b79493ae1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268140"
---
# <a name="boyermoorehorspoolsearcher-class"></a>boyer_moore_horspool_searcher sınıfı

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RandomAccessIterator1,
    class Hash = hash<typename iterator_traits<RandomAccessIterator1>::value_type>,
class BinaryPredicate = equal_to<>>
    class boyer_moore_horspool_searcher {
        boyer_moore_horspool_searcher(RandomAccessIterator1 pat_first,
            RandomAccessIterator1 pat_last,
            Hash hf = Hash(),
            BinaryPredicate pred = BinaryPredicate());
        template <class RandomAccessIterator2>
        pair<RandomAccessIterator2, RandomAccessIterator2>
            operator()(RandomAccessIterator2 first, RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[boyer_moore_horspool_searcher]()||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator()]()||
