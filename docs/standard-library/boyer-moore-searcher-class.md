---
title: boyer_moore_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_searcher
helpviewer_keywords:
- std::boyer_moore_searcher [C++]
ms.openlocfilehash: 3a6741a8ee9988a9842dea691a4ef01254872ed1
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957139"
---
# <a name="boyer_moore_searcher-class"></a>boyer_moore_searcher sınıfı

`boyer_moore_searcher` Sınıfı, nesne oluşturucusunda belirtilen bir diziyi aramak için Boyer-Moore algoritmasını kullanan bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrısı işlecine belirtilen başka bir sıra içinde yapılır. Bu sınıf, [std:: Search](algorithm-functions.md#search)'ün aşırı yüklemelerinin birine bir parametre olarak geçirilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    class RandomAccessIterator1,
    class Hash = hash<typename iterator_traits<RandomAccessIterator1>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_searcher
{
    boyer_moore_searcher(
        RandomAccessIterator1 pat_first,
        RandomAccessIterator1 pat_last,
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
| **Constructor** | |
|[boyer_moore_searcher](#boyer-moore-searcher-constructor)||
| **İşleçler** | |
| [operator()](#operator-call) | |

## <a name="boyer-moore-searcher-constructor"></a>boyer_moore_searcher Oluşturucusu

, Bir `boyer_moore_searcher` karma işlev nesnesi ve bir eşitlik koşulu aramak için diziyi kullanarak bir işlev nesnesi oluşturur.

```cpp
boyer_moore_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>Parametreler

*pat_first*\
Arama yapılacak dizinin ilk öğesi.

*pat_last*\
Aranacak dizinin sonu.

*HF*\
Dizi öğelerini karma hale almak için kullanılan çağrılabilir nesne.

*pred*\
Dizi öğeleri için isteğe bağlı eşitlik karşılaştırma koşulu. Bir eşitlik karşılaştırma türü belirtilmemişse, varsayılan olur `std::equal_to`.

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate*, *hash*veya *Randomaccessıterator* türlerinin kopya Oluşturucusu tarafından oluşturulan özel durumları ya da *BinaryPredicate* veya *hash*çağrı işlecini oluşturur.

Bu sınıf C++ 17 ' de yenidir.

## <a name="operator-call"></a>operator ()

İşlev nesnesinin Call işleci. Oluşturucuya belirtilen dizi için bağımsız `[first, last)` değişken sırası içinde arar.

```cpp
template <class ForwardIterator2>
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
İçinde arama yapılacak dizinin ilk öğesi.

*soyadına*\
İçinde arama yapılacak dizinin sonu.

### <a name="remarks"></a>Açıklamalar

Arama deseninin `[pat_first, pat_last)` boş olması halinde döndürür `make_pair(first, first)`. Arama deseninin bulunamaması halinde döndürür `make_pair(last, last)`. Aksi takdirde, `[first, last)` *Pred* `[pat_first, pat_last)` değerine göre eşit olan bir dizinin başlangıcına ve sonuna kadar yineleyiciler çifti döndürür.

Bu sınıf C++ 17 ' de yenidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<işlevsel >](functional.md)\
[algoritma işlevleri](algorithm-functions.md)\
[boyer_moore_horspool_searcher sınıfı](boyer-moore-horspool-searcher-class.md)\
[std:: arama](algorithm-functions.md#search)
