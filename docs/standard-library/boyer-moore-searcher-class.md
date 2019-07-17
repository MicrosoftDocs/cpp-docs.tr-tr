---
title: boyer_moore_searcher sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::boyer_moore_searcher
helpviewer_keywords:
- std::boyer_moore_searcher [C++]
ms.openlocfilehash: 690897fd0932ea2ccb92c630d5e15cd539d63889
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268020"
---
# <a name="boyermooresearcher-class"></a>boyer_moore_searcher sınıfı

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RandomAccessIterator1,
    class Hash = hash<typename iterator_traits<RandomAccessIterator1>::value_type>,
class BinaryPredicate = equal_to<>>
    class boyer_moore_searcher {
        boyer_moore_searcher(RandomAccessIterator1 pat_first,
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
|[boyer_moore_searcher]()||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator()]()||
