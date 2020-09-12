---
title: boyer_moore_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_searcher
helpviewer_keywords:
- std::boyer_moore_searcher [C++]
ms.openlocfilehash: d6fa4dd203336107614ca3431f38846f0c3c89af
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039826"
---
# <a name="boyer_moore_searcher-class"></a>boyer_moore_searcher sınıfı

`boyer_moore_searcher`Sınıfı, nesne oluşturucusunda belirtilen bir diziyi aramak Için Boyer-Moore algoritmasını kullanan bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrısı işlecine belirtilen başka bir sıra içinde yapılır. Bu sınıf, [std:: Search](algorithm-functions.md#search)'ün aşırı yüklemelerinin birine bir parametre olarak geçirilir.

## <a name="syntax"></a>Syntax

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

| Üye | Description |
| - | - |
| **Oluşturucu** | |
| [boyer_moore_searcher](#boyer-moore-searcher-constructor) | Bir Arayıcının örneği oluşturur. |
| **İşleçler** | |
| [operator ()](#operator-call) | İşlemi sırayla çağırır. |

## <a name="boyer_moore_searcher-constructor"></a><a name="boyer-moore-searcher-constructor"></a> boyer_moore_searcher Oluşturucusu

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
Dizi öğeleri için isteğe bağlı eşitlik karşılaştırma koşulu. Bir eşitlik karşılaştırma türü belirtilmemişse, varsayılan olur `std::equal_to` .

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate*, *hash*veya *Randomaccessıterator* türlerinin kopya Oluşturucusu tarafından oluşturulan özel durumları ya da *BinaryPredicate* veya *hash*çağrı işlecini oluşturur.

Bu sınıf C++ 17 ' de yenidir.

## <a name="operator"></a><a name="operator-call"></a> operator ()

İşlev nesnesinin Call işleci. Oluşturucuya belirtilen dizi için bağımsız değişken sırası içinde arar `[first, last)` .

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

Arama deseninin `[pat_first, pat_last)` boş olması halinde döndürür `make_pair(first, first)` . Arama deseninin bulunamaması halinde döndürür `make_pair(last, last)` . Aksi takdirde, `[first, last)` Pred değerine göre eşit olan bir dizinin başlangıcına ve sonuna kadar yineleyiciler çifti döndürür `[pat_first, pat_last)` . *pred*

Bu sınıf C++ 17 ' de yenidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<functional>](functional.md)\
[algoritma işlevleri](algorithm-functions.md)\
[boyer_moore_horspool_searcher sınıfı](boyer-moore-horspool-searcher-class.md)\
[std:: arama](algorithm-functions.md#search)
