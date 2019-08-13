---
title: boyer_moore_horspool_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: c7d24fee4a47fc588b00e527594682f1c4aadf76
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957168"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcher sınıfı

`boyer_moore_horspool_searcher` Sınıfı, nesne oluşturucusunda belirtilen bir diziyi aramak için Boyer-Moore-horspool algoritmasını kullanan bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrısı işlecine belirtilen başka bir sıra içinde yapılır. Bu sınıf, [std:: Search](algorithm-functions.md#search)'ün aşırı yüklemelerinin birine bir parametre olarak geçirilir.

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
| **Constructor** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **İşleçler** | |
| [operator()](#operator-call) | |

## <a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher Oluşturucusu

, Bir `boyer_moore_horspool_searcher` karma işlev nesnesi ve bir eşitlik koşulu aramak için diziyi kullanarak bir işlev nesnesi oluşturur.

```cpp
boyer_moore_horspool_searcher(
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
template <class ForwardIterator2>   // C++17
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
[boyer_moore_searcher sınıfı](boyer-moore-searcher-class.md)\
[std:: arama](algorithm-functions.md#search)
