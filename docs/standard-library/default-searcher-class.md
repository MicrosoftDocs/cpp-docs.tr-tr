---
title: default_searcher sınıfı
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: f2b1fe83b5223bbb60e9e32149c101e6379f93c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "68268002"
---
# <a name="default_searcher-class"></a>default_searcher sınıfı

`default_searcher` , Nesne oluşturucusunda belirtilen bir diziyi Arayıcı işlemler için bir işlev nesnesi türüdür. Arama, nesnenin işlev çağrısı işlecine belirtilen başka bir sıra içinde yapılır. Aramayı gerçekleştirmek için [std:: Search](algorithm-functions.md#search) çağırır.`default_searcher`

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
| **Constructor** | |
| [default_searcher](#default-searcher-constructor) | |
| **İşleçler** | |
| [operator()](#operator-call) | |

## <a name="default-searcher-constructor"></a>default_searcher Oluşturucusu

Aranacak diziyi `default_searcher` ve bir eşitlik koşulunu kullanarak bir işlev nesnesi oluşturur.

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
Dizi öğeleri için isteğe bağlı eşitlik karşılaştırma koşulu. Bir eşitlik karşılaştırma türü belirtilmemişse, varsayılan olur `std::equal_to`.

### <a name="remarks"></a>Açıklamalar

*BinaryPredicate* veya *ForwardIterator* türlerinin kopya Oluşturucusu tarafından oluşturulan özel durumu oluşturur.

Bu sınıf C++ 17 ' de yenidir. C++ 20 Oluşturucu `constexpr`yaptı.

## <a name="operator-call"></a>operator ()

İşlev işlecinin Call işleci. Oluşturucuya belirtilen dizi için bağımsız `[first, last)` değişken sırası içinde arar.

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

İkilinin ikinci yineleyicisi *en son* *bir*. Aksi takdirde, bunun etkili sonucu:

`std::next( i, std::distance( pat_first, pat_last ))`.

Bu sınıf C++ 17 ' de yenidir. C++ 20 çağrı işlecini `constexpr`yaptı.

## <a name="see-also"></a>Ayrıca bkz.

[\<işlevsel >](functional.md)\
[algoritma işlevleri](algorithm-functions.md)\
[std:: arama](algorithm-functions.md#search)
