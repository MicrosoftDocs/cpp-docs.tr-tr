---
title: algoritma (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
- cliext::adjacent_find
- cliext::binary_search
- cliext::copy
- cliext::copy_backward
- cliext::count
- cliext::count_if
- cliext::equal
- cliext::equal_range
- cliext::fill
- cliext::fill_n
- cliext::find
- cliext::find_end
- cliext::find_first_of
- cliext::find_if
- cliext::for_each
- cliext::generate
- cliext::generate_n
- cliext::includes
- cliext::inplace_merge
- cliext::iter_swap
- cliext::lexicographical_compare
- cliext::lower_bound
- cliext::make_heap
- cliext::max
- cliext::max_element
- cliext::merge
- cliext::min
- cliext::min_element
- cliext::mismatch
- cliext::next_permutation
- cliext::nth_element
- cliext::partial_sort
- cliext::partial_sort_copy
- cliext::partition
- cliext::pop_heap
- cliext::prev_permutation
- cliext::push_heap
- cliext::random_shuffle
- cliext::remove
- cliext::remove_copy
- cliext::remove_copy_if
- cliext::remove_if
- cliext::replace
- cliext::replace_copy
- cliext::replace_copy_if
- cliext::replace_if
- cliext::reverse
- cliext::reverse_copy
- cliext::rotate
- cliext::rotate_copy
- cliext::search
- cliext::search_n
- cliext::set_difference
- cliext::set_intersection
- cliext::set_symmetric_difference
- cliext::set_union
- cliext::sort
- cliext::sort_heap
- cliext::stable_partition
- cliext::stable_sort
- cliext::swap
- cliext::swap_ranges
- cliext::transform
- cliext::unique
- cliext::unique_copy
- cliext::upper_bound
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
- adjacent_find function
- binary_search function [STL/CLR]
- copy function [STL/CLR]
- copy_backward function [STL/CLR]
- count function [STL/CLR]
- count_if function [STL/CLR]
- equal function [STL/CLR]
- equal_range function [STL/CLR]
- fill function
- fill_n function
- find function [STL/CLR]
- find_end function [STL/CLR]
- find_first_of function [STL/CLR]
- find_if function [STL/CLR]
- for_each function [STL/CLR]
- generate function [STL/CLR]
- generate_n function [STL/CLR]
- includes function [STL/CLR]
- inplace_merge function [STL/CLR]
- iter_swap function [STL/CLR]
- lexicographical_compare function [STL/CLR]
- lower_bound function [STL/CLR]
- make_heap function [STL/CLR]
- max function [STL/CLR]
- max_element function [STL/CLR]
- merge function [STL/CLR]
- min function [STL/CLR]
- min_element function [STL/CLR]
- mismatch function [STL/CLR]
- next_permutation function [STL/CLR]
- nth_element function [STL/CLR]
- partial_sort function [STL/CLR]
- partial_sort_copy function [STL/CLR]
- partition function [STL/CLR]
- pop_heap function [STL/CLR]
- prev_permutation function [STL/CLR]
- push_heap function [STL/CLR]
- random_shuffle function [STL/CLR]
- remove function [STL/CLR]
- remove_copy function [STL/CLR]
- remove_copy_if function [STL/CLR]
- remove_if function [STL/CLR]
- replace function [STL/CLR]
- replace_copy function [STL/CLR]
- replace_copy_if function [STL/CLR]
- replace_if function [STL/CLR]
- reverse function [STL/CLR]
- reverse_copy function [STL/CLR]
- rotate function [STL/CLR]
- rotate_copy function [STL/CLR]
- search function [STL/CLR]
- search_n function [STL/CLR]
- set_difference function [STL/CLR]
- set_intersection function [STL/CLR]
- set_symmetric_difference function [STL/CLR]
- set_union function [STL/CLR]
- sort function [STL/CLR]
- sort_heap function [STL/CLR]
- stable_partition function [STL/CLR]
- stable_sort function [STL/CLR]
- swap function [STL/CLR]
- swap_ranges function [STL/CLR]
- transform function [STL/CLR]
- unique function [STL/CLR]
- unique_copy function [STL/CLR]
- upper_bound function [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
ms.openlocfilehash: 6011aad0ef86bc0e633687a6d8e017e9b12771c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528732"
---
# <a name="algorithm-stlclr"></a>algoritma (STL/CLR)

Algoritmalar gerçekleştiren STL/CLR kapsayıcı şablon işlevini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cliext/algorithm>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cliext/algoritma >

**Namespace:** cliext

## <a name="declarations"></a>Bildirimler

|İşlev|Açıklama|
|--------------|-----------------|
|[adjacent_find (STL/CLR)](#adjacent_find)|Eşit olan iki bitişik öğeyi arar.|
|[binary_search (STL/CLR)](#binary_search)|Sıralı bir dizi belirli bir değeri içerip içermediğini test eder.|
|[copy (STL/CLR)](#copy)|Yineleme İleri yönde bir hedef aralığına kopyalar değerleri bir kaynak aralıktan.|
|[copy_backward (STL/CLR)](#copy_backward)|Yineleme geri yönde bir hedef aralığına kopyalar değerleri bir kaynak aralıktan.|
|[count (STL/CLR)](#count)|Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[count_if (STL/CLR)](#count_if)|Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[equal (STL/CLR)](#equal)|İki aralığı, öğe öğe karşılaştırır.|
|[equal_range (STL/CLR)](#equal_range)|Sıralı değerler arar ve belirli bir öğeye eşit tüm değerlerin bir alt dizi sınırlandırmak iki konumlarını döndürür.|
|[fill (STL/CLR)](#fill)|Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.|
|[fill_n (STL/CLR)](#fill_n)|Belirli bir öğeyle başlayan bir aralıktaki öğeleri belirtilen sayıda yeni bir değer atar.|
|[find (STL/CLR)](#find)|Belirli bir değerin ilk geçtiği konumu döndürür.|
|[find_end (STL/CLR)](#find_end)|Belirtilen bir diziye özdeş bir aralıktaki son dizi döndürür.|
|[find_first_of (STL/CLR)](#find_first_of)|Bir aralık öğelerin belirli bir aralığını herhangi birinin ilk geçtiği yeri arar.|
|[find_if (STL/CLR)](#find_if)|İlk öğenin konumunu burada öğe belirtilen bir koşulu karşılayan değerler dizisi döndürür.|
|[for_each (STL/CLR)](#for_each)|Değerlerin bir dizideki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.|
|[generate (STL/CLR)](#generate)|Değerlerin bir dizideki her öğe için bir işlev nesnesi tarafından oluşturulan değerleri atar.|
|[generate_n (STL/CLR)](#generate_n)|Belirtilen sayıda öğeyi bir işlev nesnesi tarafından oluşturulan değerleri atar.|
|[includes (STL/CLR)](#includes)|Sıralanmış bir aralığın ikinci bir sıralanmış aralıktaki tüm öğeleri içerip içermediğini test eder.|
|[inplace_merge (STL/CLR)](#inplace_merge)|Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir.|
|[iter_swap (STL/CLR)](#iter_swap)|Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.|
|[lexicographical_compare (STL/CLR)](#lexicographical_compare)|İki sıranın, hangi ikisinden küçük olanı sırasıdır tanımlayan öğeye göre karşılaştırır.|
|[lower_bound (STL/CLR)](#lower_bound)|Belirtilen bir değerine eşit veya daha büyük bir değere sahip sıralı bir dizi değer ilk öğenin konumunu bulur.|
|[make_heap (STL/CLR)](#make_heap)|Öğeleri belirtilen bir aralıktaki ilk öğeyi yığındaki en büyük olduğu bir yığına dönüştürür.|
|[en fazla (STL/CLR)](#max))|İki nesneyi karşılaştırır ve iki büyük döndürür.|
|[max_element (STL/CLR)](#max_element)|Değerlerin belirtilen sırada en büyük öğeyi bulur.|
|[Merge (STL/CLR)](#merge))|İki sıralanmış kaynak aralıktaki tüm öğeleri tek, sıralanmış bir aralığa birleştirir.|
|[min (STL/CLR)](#min)|İki nesneyi karşılaştırır ve ikisinden küçük olanı döndürür.|
|[min_element (STL/CLR)](#min_element)|Değerlerin belirtilen sırada en küçük öğeyi bulur.|
|[mismatch (STL/CLR)](#mismatch)|İki aralığı öğe öğe karşılaştırır ve farkın oluştuğu ilk konumunu döndürür.|
|[next_permutation (STL/CLR)](#next_permutation)|Bir aralıktaki öğeleri yeniden sıralar, böylece varsa özgün sıralama sözlüksel sonraki permütasyon ile değiştirilir.|
|[nth_element (STL/CLR)](#nth_element)|Doğru şekilde bularak öğelerin bir dizisi bölümleri `n`öğedeki sırası önündeki tüm öğeler değerden küçük veya eşit olacak ve bunu izleyen tüm öğeler büyüktür veya ona eşittir.|
|[partial_sort (STL/CLR)](#partial_sort)|Bir aralıktaki daha küçük öğelerin belirtilen sayıda azalmayan düzenler.|
|[partial_sort_copy (STL/CLR)](#partial_sort_copy)|Sağlayacak şekilde kaynak aralığındaki öğelerin öğelerini bir kaynak aralıktan bir hedef aralığına kopyalar.|
|[partition (STL/CLR)](#partition)|Bir aralıktaki öğeleri, karşılamada birli koşulu karşılayan bu öğelerin önünde gibi ayarlar.|
|[pop_heap (STL/CLR)](#pop_heap)|En büyük öğeyi bir yığının önünden sonuna taşır ve ardından kalan öğelerden yeni bir yığın oluşturur.|
|[prev_permutation (STL/CLR)](#prev_permutation)|Varsa özgün sıralama sözlüksel önceki permütasyon ile değiştirilir, böylece bir dizi öğeleri yeniden sıralar.|
|[push_heap (STL/CLR)](#push_heap)|Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.|
|[random_shuffle (STL/CLR)](#random_shuffle)|Bir dizi düzenlemelerinin `N` birine bir aralıktaki öğeleri `N`! olası düzenlemeleri rastgele seçilmiş.|
|[remove (STL/CLR)](#remove)|Kalan öğelerin sırasını bozmadan belirtilen bir değeri belirtilen bir aralıktan siler ve yeni bir aralık için belirtilen değer boş sonunu döndürür.|
|[remove_copy (STL/CLR)](#remove_copy)|Belirtilen değerin, kalan öğelerin sırasını bozmadan kopyalanmaz dışında öğeleri bir kaynak aralıktan bir hedef aralığına kopyalar.|
|[remove_copy_if (STL/CLR)](#remove_copy_if)|Öğeleri bir kaynak aralıktan hariç, kalan öğelerin sırasını bozmadan bir koşulu karşılayan bir hedef aralığına kopyalar.|
|[remove_if (STL/CLR)](#remove_if)|Kalan öğelerin sırasını bozmadan verili aralıktaki bir koşulu karşılayan öğeleri siler. biçimindeki telefon numarasıdır.|
|[replace (STL/CLR)](#replace)|Yeni bir değer belirli bir değerle eşleşen bir aralıktaki öğeleri değiştirir.|
|[replace_copy (STL/CLR)](#replace_copy)|Yeni bir değer belirli bir değerle eşleşen öğeleri değiştirerek bir hedef aralığına kopyalar öğeleri bir kaynak aralıktan.|
|[replace_copy_if (STL/CLR)](#replace_copy_if)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.|
|[replace_if (STL/CLR)](#replace_if)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.|
|[reverse (STL/CLR)](#reverse)|Bir aralık içindeki öğelerin sırasını tersine çevirir.|
|[reverse_copy (STL/CLR)](#reverse_copy)|Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine.|
|[rotate (STL/CLR)](#rotate)|İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.|
|[rotate_copy (STL/CLR)](#rotate_copy)|Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.|
|[search (STL/CLR)](#search_)|Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.|
|[search_n (STL/CLR)](#search_n)|Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.|
|[set_difference (STL/CLR)](#set_difference)|Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[set_intersection (STL/CLR)](#set_intersection)|Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_symmetric_difference (STL/CLR)](#set_symmetric_difference)|İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_union (STL/CLR)](#set_union))|İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[sort (STL/CLR)](#sort)|Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[sort_heap (STL/CLR)](#sort_heap)|Bir yığını sıralanmış bir aralığa dönüştürür.|
|[stable_partition (STL/CLR)](#stable_partition)|Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|
|[stable_sort (STL/CLR)](#stable_sort)|Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[swap (STL/CLR)](#swap)|İlk nesnenin içeriğini ikinci nesneye ve ikinci nesneni içeriğini birinciye atayarak, nesnelerin iki türü arasındaki öğelerin değerlerini birbiriyle değiştirir.|
|[swap_ranges (STL/CLR)](#swap_ranges)|Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.|
|[transform (STL/CLR)](#transform)|Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.|
|[unique (STL/CLR)](#unique)|Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.|
|[unique_copy (STL/CLR)](#unique_copy)|Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.|
|[upper_bound (STL/CLR)](#upper_bound)|Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|

## <a name="members"></a>Üyeler

## <a name="adjacent_find"></a> adjacent_find (STL/CLR)

Eşit ya da belirli bir koşulu karşılayan iki bitişik öğeyi arar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt> inline
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `adjacent_find`. Daha fazla bilgi için [adjacent_find](../standard-library/algorithm-functions.md#adjacent_find).

## <a name="binary_search"></a> binary_search (STL/CLR)

Belirtilen değere eşit sıralanmış bir aralıkta bir öğe olup olmadığını ya da bir ikili koşula göre belirtilen anlamda ona eşdeğer bir öğe olup olmadığını sınar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    bool binary_search(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    bool binary_search(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `binary_search`. Daha fazla bilgi için [binary_search](../standard-library/algorithm-functions.md#binary_search).

## <a name="copy"></a> Kopyala (STL/CLR)

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına ileri yönde atar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt copy(_InIt _First, _InIt _Last, _OutIt _Dest);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `copy`. Daha fazla bilgi için [kopyalama](../standard-library/algorithm-functions.md#copy).

## <a name="copy_backward"></a> copy_backward (STL/CLR)

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt1, class _BidIt2> inline
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,
        _BidIt2 _Dest);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `copy_backward`. Daha fazla bilgi için [copy_backward](../standard-library/algorithm-functions.md#copy_backward).

## <a name="count"></a> Count (STL/CLR)

Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Ty> inline
    typename iterator_traits<_InIt>::difference_type
        count(_InIt _First, _InIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `count`. Daha fazla bilgi için [sayısı](../standard-library/algorithm-functions.md#count).

## <a name="count_if"></a> count_if (STL/CLR)

Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Pr> inline
    typename iterator_traits<_InIt>::difference_type
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `count_if`. Daha fazla bilgi için [count_if](../standard-library/algorithm-functions.md#count_if).

## <a name="equal"></a> eşit (STL/CLR)

Bir ikili koşula göre belirtilen anlamda eşitlik ya da denklik için iki aralık öğesini öğeye göre karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2> inline
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `equal`. Daha fazla bilgi için [eşit](../standard-library/algorithm-functions.md#equal).

## <a name="equal_range"></a> equal_range (STL/CLR)

Sıralanmış aralıktaki konumların çiftini bulur, birinci belirtilen bir öğenin konumundan küçük veya ona eşittir ve ikinci öğenin konumundan büyüktür, burada dizideki konumlar oluşturmak için kullanılan denkliğin veya sıralamanın anlamı bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `equal_range`. Daha fazla bilgi için [equal_range](../standard-library/algorithm-functions.md#equal_range).

## <a name="fill"></a> Doldur (STL/CLR)

Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `fill`. Daha fazla bilgi için [dolgu](../standard-library/algorithm-functions.md#fill).

## <a name="fill_n"></a> fill_n (STL/CLR)

Belirli bir öğeyle başlayan bir aralıktaki öğeleri belirtilen sayıda yeni bir değer atar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _OutIt, class _Diff, class _Ty> inline
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `fill_n`. Daha fazla bilgi için [fill_n](../standard-library/algorithm-functions.md#fill_n).

## <a name="find"></a> Bul (STL/CLR)

Bir öğenin belirli bir değere sahip olan aralıktaki ilk geçtiği konumu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Ty> inline
    _InIt find(_InIt _First, _InIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `find`. Daha fazla bilgi için [Bul](../standard-library/algorithm-functions.md#find).

## <a name="find_end"></a> find_end (STL/CLR)

Belirli bir diziye özdeş veya bir ikili koşula göre belirtildiği şekilde denk olan son dizi için bir aralık arar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 find_end(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `find_end`. Daha fazla bilgi için [find_end](../standard-library/algorithm-functions.md#find_end).

## <a name="find_first_of"></a> find_first_of (STL/CLR)

Bir hedef aralığındaki çeşitli değerlerden herhangi birinin ilk geçtiği yeri veya bir ikili koşula göre belirtilen bir öğeler kümesine belirtildiği şekilde denk olan çeşitli öğelerin geçtiği ilk yeri arar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `find_first_of`. Daha fazla bilgi için [find_first_of](../standard-library/algorithm-functions.md#find_first_of).

## <a name="find_if"></a> find_if (STL/CLR)

Bir öğenin belirli bir koşulu karşıladığı aralıktaki ilk geçtiği konumu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Pr> inline
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `find_if`. Daha fazla bilgi için [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="for_each"></a> for_each (STL/CLR)

Bir aralıktaki ileriye doğru sıradaki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _Fn1> inline
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `for_each`. Daha fazla bilgi için [for_each](../standard-library/algorithm-functions.md#for_each).

## <a name="generate"></a> (STL/CLR) oluştur

Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki her öğeye atar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Fn0> inline
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `generate`. Daha fazla bilgi için [oluşturmak](../standard-library/algorithm-functions.md#generate).

## <a name="generate_n"></a> generate_n (STL/CLR)

Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki belirtilen öğe sayısına atar ve birinin son atanan değere geçirdiği konuma döner.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _OutIt, class _Diff, class _Fn0> inline
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `generate_n`. Daha fazla bilgi için [generate_n](../standard-library/algorithm-functions.md#generate_n).

## <a name="includes"></a> içerir (STL/CLR)

Sıralanmış bir aralığın ikinci bir sıralanmış aralıkta kapsanan tüm öğeleri içerip içermediğini sınar, burada öğeler arasındaki sıralama veya denklik ölçütü bir ikili koşula göre belirlenebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2> inline
    bool includes(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool includes(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `includes`. Daha fazla bilgi için [içerir](../standard-library/algorithm-functions.md#includes).

## <a name="inplace_merge"></a> inplace_merge (STL/CLR)

Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt> inline
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `inplace_merge` daha fazla bilgi için [inplace_merge](../standard-library/algorithm-functions.md#inplace_merge).

## <a name="iter_swap"></a> iter_swap (STL/CLR)

Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `iter_swap`. Daha fazla bilgi için [iter_swap](../standard-library/algorithm-functions.md#iter_swap).

## <a name="lexicographical_compare"></a> lexicographical_compare (STL/CLR)

Daha küçük olanı belirlemek için iki diziyi öğe öğe karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2> inline
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2);
template<class _InIt1, class _InIt2, class _Pr> inline
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `lexicographical_compare`. Daha fazla bilgi için [lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare).

## <a name="lower_bound"></a> lower_bound (STL/CLR)

Belirtilen değere, burada sıralama ölçütü bir ikili koşula göre belirtilebilir küçük veya buna eşdeğer bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `lower_bound`. Daha fazla bilgi için [lower_bound](../standard-library/algorithm-functions.md#lower_bound).

## <a name="make_heap"></a> make_heap (STL/CLR)

Belirtilen bir aralıktaki öğeleri ilk öğenin en büyük olduğu ve onun için bir ikili koşula sahip bir sıralama ölçütünün belirtilebildiği bir yığına dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void make_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `make_heap`. Daha fazla bilgi için [make_heap](../standard-library/algorithm-functions.md#make_heap).

## <a name="max"></a> en fazla (STL/CLR)

İki nesneyi karşılaştırır ve ikisinden büyük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _Ty> inline
    const _Ty max(const _Ty% _Left, const _Ty% _Right);
template<class _Ty, class _Pr> inline
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `max`. Daha fazla bilgi için [max](../standard-library/algorithm-functions.md#max).

## <a name="max_element"></a> max_element (STL/CLR)

Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt> inline
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `max_element`. Daha fazla bilgi için [max_element](../standard-library/algorithm-functions.md#max_element).

## <a name="merge"></a> Merge (STL/CLR)

İki sıralanmış kaynak aralıktaki tüm öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `merge`. Daha fazla bilgi için [birleştirme](../standard-library/algorithm-functions.md#merge).

## <a name="min"></a> Min (STL/CLR)

İki nesneyi karşılaştırır ve ikisinden küçük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _Ty> inline
    const _Ty min(const _Ty% _Left, const _Ty% _Right);
template<class _Ty, class _Pr> inline
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `min`. Daha fazla bilgi için [min](../standard-library/algorithm-functions.md#min).

## <a name="min_element"></a> min_element (STL/CLR)

Belirtilen bir aralıktaki en küçük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt> inline
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `min_element`. Daha fazla bilgi için [min_element](../standard-library/algorithm-functions.md#min_element).

## <a name="mismatch"></a> Uyumsuzluk (STL/CLR)

Eşitlik ya da denklik için ikili bir koşul tarafından belirtildiği şekilde iki aralığı öğe öğe karşılaştırır ve farkın oluştuğu ilk yeri bulur.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2> inline
    _PAIR_TYPE(_InIt1)
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);
template<class _InIt1, class _InIt2, class _Pr> inline
    _PAIR_TYPE(_InIt1)
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
            _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `mismatch`. Daha fazla bilgi için [uyuşmazlığı](../standard-library/algorithm-functions.md#mismatch).

## <a name="next_permutation"></a> next_permutation (STL/CLR)

Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt> inline
    bool next_permutation(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `next_permutation`. Daha fazla bilgi için [next_permutation](../standard-library/algorithm-functions.md#next_permutation).

## <a name="nth_element"></a> nth_element (STL/CLR)

Doğru şekilde bularak öğelerin bir aralığını bölümler `n`öğedeki aralığındaki dizinin önündeki tüm öğeler ona eşit veya ve sırayla izleyen tüm öğeler, böylece büyük veya ona eşittir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `nth_element`. Daha fazla bilgi için [nth_element](../standard-library/algorithm-functions.md#nth_element).

## <a name="partial_sort"></a> partial_sort (STL/CLR)

Bir aralıktaki daha küçük öğelerin belirtilen sayısını azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `partial_sort`. Daha fazla bilgi için [partial_sort](../standard-library/algorithm-functions.md#partial_sort).

## <a name="partial_sort_copy"></a> partial_sort_copy (STL/CLR)

Öğeleri bir kaynak aralığından bir hedef aralığa kopyalar, burada kaynak öğeleri daha küçük olana ya da belirtilen başka bir ikili koşula göre sıralanır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _RanIt> inline
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,
        _RanIt _First2, _RanIt _Last2);
template<class _InIt, class _RanIt, class _Pr> inline
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `partial_sort_copy`. Daha fazla bilgi için [partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy).

## <a name="partition"></a> Bölüm (STL/CLR)

Bir aralıktaki öğeleri, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt, class _Pr> inline
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `partition`. Daha fazla bilgi için [bölüm](../standard-library/algorithm-functions.md#partition).

## <a name="pop_heap"></a> pop_heap (STL/CLR)

En büyük öğeyi bir yığının önünden aralıktaki bir sonraki son konuma kaldırır ve ardından kalan öğelerden yeni bir yığın oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void pop_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `pop_heap`. Daha fazla bilgi için [pop_heap](../standard-library/algorithm-functions.md#pop_heap).

## <a name="prev_permutation"></a> prev_permutation (STL/CLR)

Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt> inline
    bool prev_permutation(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `prev_permutation`. Daha fazla bilgi için [prev_permutation](../standard-library/algorithm-functions.md#prev_permutation).

## <a name="push_heap"></a> push_heap (STL/CLR)

Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void push_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `push_heap`. Daha fazla bilgi için [push_heap](../standard-library/algorithm-functions.md#push_heap).

## <a name="random_shuffle"></a> random_shuffle (STL/CLR)

Bir dizi düzenlemelerinin `N` birine bir aralıktaki öğeleri `N`! olası düzenlemeleri rastgele seçilmiş.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void random_shuffle(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Fn1> inline
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `random_shuffle`. Daha fazla bilgi için [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle).

## <a name="remove"></a> Kaldır (STL/CLR)

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki belirtilen bir değeri ortadan kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `remove`. Daha fazla bilgi için [Kaldır](../standard-library/algorithm-functions.md#remove).

## <a name="remove_copy"></a> remove_copy (STL/CLR)

Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt, class _Ty> inline
    _OutIt remove_copy(_InIt _First, _InIt _Last,
        _OutIt _Dest, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `remove_copy`. Daha fazla bilgi için [remove_copy](../standard-library/algorithm-functions.md#remove_copy).

## <a name="remove_copy_if"></a> remove_copy_if (STL/CLR)

Öğeleri, bir koşulu karşılayan kopyalanmayan öğeler hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt, class _Pr> inline
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `remove_copy_if`. Daha fazla bilgi için [remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if).

## <a name="remove_if"></a> remove_if (STL/CLR)

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki bir koşulu karşılayan öğeleri ortadan kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Pr> inline
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `remove_if`. Daha fazla bilgi için [remove_if](../standard-library/algorithm-functions.md#remove_if).

## <a name="replace"></a> replace (STL/CLR)

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir değerle eşleşiyorsa değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    void replace(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Oldval, const _Ty% _Newval);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `replace`. Daha fazla bilgi için [değiştirin](../standard-library/algorithm-functions.md#replace).

## <a name="replace_copy"></a> replace_copy (STL/CLR)

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt, class _Ty> inline
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,
        const _Ty% _Oldval, const _Ty% _Newval);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `replace_copy`. Daha fazla bilgi için [replace_copy](../standard-library/algorithm-functions.md#replace_copy).

## <a name="replace_copy_if"></a> replace_copy_if (STL/CLR)

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred, const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `replace_copy_if`. Daha fazla bilgi için [replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if).

## <a name="replace_if"></a> replace_if (STL/CLR)

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Pr, class _Ty> inline
    void replace_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred,
        const _Ty% _Val);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `replace_if`. Daha fazla bilgi için [replace_if](../standard-library/algorithm-functions.md#replace_if).

## <a name="reverse"></a> reverse (STL/CLR)

Bir aralık içindeki öğelerin sırasını tersine çevirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt> inline
    void reverse(_BidIt _First, _BidIt _Last);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `reverse`. Daha fazla bilgi için [ters](../standard-library/algorithm-functions.md#reverse).

## <a name="reverse_copy"></a> reverse_copy (STL/CLR)

Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt, class _OutIt> inline
    _OutIt reverse_copy(_BidIt _First, _BidIt _Last, _OutIt _Dest);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `reverse_copy`. Daha fazla bilgi için [reverse_copy](../standard-library/algorithm-functions.md#reverse_copy).

## <a name="rotate"></a> Döndür (STL/CLR)

İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt> inline
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `rotate`. Daha fazla bilgi için [döndürme](../standard-library/algorithm-functions.md#rotate).

## <a name="rotate_copy"></a> rotate_copy (STL/CLR)

Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _OutIt> inline
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,
        _OutIt _Dest);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `rotate_copy`. Daha fazla bilgi için [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy).

## <a name="search_"></a> Arama (STL/CLR)

Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2);
template<class _FwdIt1, class _FwdIt2, class _Pr> inline
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `search`. Daha fazla bilgi için [arama](../standard-library/algorithm-functions.md#search).

## <a name="search_n"></a> search_n (STL/CLR)

Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _Diff2, class _Ty> inline
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,
        _Diff2 _Count, const _Ty& _Val);
template<class _FwdIt1, class _Diff2, class _Ty, class _Pr> inline
    _FwdIt1 search_n(_FwdIt1 _First1, _FwdIt1 _Last1,
        _Diff2 _Count, const _Ty& _Val, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `search_n`. Daha fazla bilgi için [search_n](../standard-library/algorithm-functions.md#search_n).

## <a name="set_difference"></a> set_difference (STL/CLR)

Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `set_difference`. Daha fazla bilgi için [set_difference](../standard-library/algorithm-functions.md#set_difference).

## <a name="set_intersection"></a> set_intersection (STL/CLR)

Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `set_intersection`. Daha fazla bilgi için [set_intersection](../standard-library/algorithm-functions.md#set_intersection).

## <a name="set_symmetric_difference"></a> set_symmetric_difference (STL/CLR)

İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_symmetric_difference(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `set_symmetric_difference`. Daha fazla bilgi için [set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference).

## <a name="set_union"></a> set_union (STL/CLR)

İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt1, class _InIt2, class _OutIt> inline
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `set_union`. Daha fazla bilgi için [set_union](../standard-library/algorithm-functions.md#set_union).

## <a name="sort"></a> Sırala (STL/CLR)

Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void sort(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `sort`. Daha fazla bilgi için [sıralama](../mfc/reference/cmfclistctrl-class.md#sort).

## <a name="sort_heap"></a> sort_heap (STL/CLR)

Bir yığını sıralanmış bir aralığa dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _RanIt> inline
    void sort_heap(_RanIt _First, _RanIt _Last);
template<class _RanIt, class _Pr> inline
    void sort_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `sort_heap`. Daha fazla bilgi için [sort_heap](../standard-library/algorithm-functions.md#sort_heap).

## <a name="stable_partition"></a> stable_partition (STL/CLR)

Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt, class _Pr> inline
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `stable_partition`. Daha fazla bilgi için [stable_partition](../standard-library/algorithm-functions.md#stable_partition).

## <a name="stable_sort"></a> stable_sort (STL/CLR)

Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _BidIt> inline
    void stable_sort(_BidIt _First, _BidIt _Last);
template<class _BidIt, class _Pr> inline
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `stable_sort`. Daha fazla bilgi için [stable_sort](../standard-library/algorithm-functions.md#stable_sort).

## <a name="swap"></a> takas (STL/CLR)

İlk nesnenin içeriğini ikinci nesneye ve ikinci nesneni içeriğini birinciye atayarak, nesnelerin iki türü arasındaki öğelerin değerlerini birbiriyle değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
<class _Ty> inline
    void swap(_Ty% _Left, _Ty% _Right);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `swap`. Daha fazla bilgi için [takas](../standard-library/algorithm-functions.md#swap).

## <a name="swap_ranges"></a> swap_ranges (STL/CLR)

Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt1, class _FwdIt2> inline
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,
        _FwdIt2 _First2);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `swap_ranges`. Daha fazla bilgi için [swap_ranges](../standard-library/algorithm-functions.md#swap_ranges).

## <a name="transform"></a> Dönüşüm (STL/CLR)

Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt, class _Fn1> inline
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Fn1 _Func);
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,
        _OutIt _Dest, _Fn2 _Func);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `transform`. Daha fazla bilgi için [dönüştürme](../standard-library/algorithm-functions.md#transform).

## <a name="unique"></a> benzersiz (STL/CLR)

Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt> inline
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);
template<class _FwdIt, class _Pr> inline
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `unique`. Daha fazla bilgi için [benzersiz](../standard-library/algorithm-functions.md#unique).

## <a name="unique_copy"></a> unique_copy (STL/CLR)

Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _InIt, class _OutIt> inline
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);
template<class _InIt, class _OutIt, class _Pr> inline
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,
        _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `unique_copy`. Daha fazla bilgi için [unique_copy](../standard-library/algorithm-functions.md#unique_copy).

## <a name="upper_bound"></a> upper_bound (STL/CLR)

Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

### <a name="syntax"></a>Sözdizimi

```cpp
template<class _FwdIt, class _Ty> inline
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);
template<class _FwdIt, class _Ty, class _Pr> inline
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,
        const _Ty% _Val, _Pr _Pred);
```

### <a name="remarks"></a>Açıklamalar

Bu işlev C++ Standart Kitaplığı işlevi gibi davranır `upper_bound`. Daha fazla bilgi için [upper_bound](../standard-library/algorithm-functions.md#upper_bound).