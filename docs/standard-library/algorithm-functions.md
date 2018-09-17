---
title: '&lt;algoritma&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- algorithm/std::adjacent_find
- algorithm/std::all_of
- algorithm/std::any_of
- algorithm/std::binary_search
- algorithm/std::copy
- algorithm/std::copy_backward
- algorithm/std::copy_if
- algorithm/std::copy_n
- algorithm/std::equal
- algorithm/std::equal_range
- algorithm/std::fill
- algorithm/std::fill_n
- algorithm/std::find
- algorithm/std::find_end
- algorithm/std::find_first_of
- algorithm/std::find_if
- algorithm/std::find_if_not
- algorithm/std::for_each
- algorithm/std::generate
- algorithm/std::generate_n
- algorithm/std::includes
- algorithm/std::inplace_merge
- algorithm/std::is_heap
- algorithm/std::is_heap_until
- algorithm/std::is_partitioned
- algorithm/std::is_permutation
- algorithm/std::is_sorted
- algorithm/std::is_sorted_until
- algorithm/std::iter_swap
- algorithm/std::lexicographical_compare
- algorithm/std::lower_bound
- algorithm/std::make_heap
- algorithm/std::max
- algorithm/std::max_element
- algorithm/std::merge
- algorithm/std::min
- algorithm/std::minmax
- algorithm/std::minmax_element
- algorithm/std::min_element
- algorithm/std::mismatch
- algorithm/std::move
- algorithm/std::move_backward
- algorithm/std::next_permutation
- algorithm/std::none_of
- algorithm/std::nth_element
- algorithm/std::partial_sort
- algorithm/std::partial_sort_copy
- algorithm/std::partition
- algorithm/std::partition_point
- algorithm/std::pop_heap
- algorithm/std::prev_permutation
- algorithm/std::push_heap
- algorithm/std::random_shuffle
- algorithm/std::remove
- algorithm/std::remove_copy
- algorithm/std::remove_copy_if
- algorithm/std::remove_if
- algorithm/std::replace
- algorithm/std::replace_copy
- algorithm/std::replace_copy_if
- algorithm/std::replace_if
- algorithm/std::reverse
- algorithm/std::reverse_copy
- algorithm/std::rotate
- algorithm/std::rotate_copy
- algorithm/std::search
- algorithm/std::search_n
- algorithm/std::set_difference
- algorithm/std::set_intersection
- algorithm/std::set_symmetric_difference
- algorithm/std::set_union
- algorithm/std::shuffle
- algorithm/std::sort
- algorithm/std::sort_heap
- algorithm/std::stable_partition
- algorithm/std::stable_sort
- algorithm/std::swap_ranges
- algorithm/std::transform
- algorithm/std::unique
- algorithm/std::unique_copy
- algorithm/std::upper_bound
- xutility/std::copy
- xutility/std::copy_backward
- xutility/std::copy_n
- xutility/std::count
- xutility/std::equal
- xutility/std::fill
- xutility/std::fill_n
- xutility/std::find
- xutility/std::is_permutation
- xutility/std::lexicographical_compare
- xutility/std::move
- xutility/std::move_backward
- xutility/std::reverse
- xutility/std::rotate
- algorithm/std::count_if
- algorithm/std::partition_copy
- algorithm/std::swap
dev_langs:
- C++
ms.assetid: c10b0c65-410c-4c83-abf8-8b7f61bba8d0
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::adjacent_find [C++]
- std::all_of [C++]
- std::any_of [C++]
- std::binary_search [C++]
- std::copy [C++]
- std::copy_backward [C++]
- std::copy_if [C++]
- std::copy_n [C++]
- std::equal [C++]
- std::equal_range [C++]
- std::fill [C++]
- std::fill_n [C++]
- std::find [C++]
- std::find_end [C++]
- std::find_first_of [C++]
- std::find_if [C++]
- std::find_if_not [C++]
- std::for_each [C++]
- std::generate [C++]
- std::generate_n [C++]
- std::includes [C++]
- std::inplace_merge [C++]
- std::is_heap [C++]
- std::is_heap_until [C++]
- std::is_partitioned [C++]
- std::is_permutation [C++]
- std::is_sorted [C++]
- std::is_sorted_until [C++]
- std::iter_swap [C++]
- std::lexicographical_compare [C++]
- std::lower_bound [C++]
- std::make_heap [C++]
- std::max [C++]
- std::max_element [C++]
- std::merge [C++]
- std::min [C++]
- std::minmax [C++]
- std::minmax_element [C++]
- std::min_element [C++]
- std::mismatch [C++]
- std::move [C++]
- std::move_backward [C++]
- std::next_permutation [C++]
- std::none_of [C++]
- std::nth_element [C++]
- std::partial_sort [C++]
- std::partial_sort_copy [C++]
- std::partition [C++]
- std::partition_point [C++]
- std::pop_heap [C++]
- std::prev_permutation [C++]
- std::push_heap [C++]
- std::random_shuffle [C++]
- std::remove [C++]
- std::remove_copy [C++]
- std::remove_copy_if [C++]
- std::remove_if [C++]
- std::replace [C++]
- std::replace_copy [C++]
- std::replace_copy_if [C++]
- std::replace_if [C++]
- std::reverse [C++]
- std::reverse_copy [C++]
- std::rotate [C++]
- std::rotate_copy [C++]
- std::search [C++]
- std::search_n [C++]
- std::set_difference [C++]
- std::set_intersection [C++]
- std::set_symmetric_difference [C++]
- std::set_union [C++]
- std::shuffle [C++]
- std::sort [C++]
- std::sort_heap [C++]
- std::stable_partition [C++]
- std::stable_sort [C++]
- std::swap_ranges [C++]
- std::transform [C++]
- std::unique [C++]
- std::unique_copy [C++]
- std::upper_bound [C++]
- std::copy [C++]
- std::copy_backward [C++]
- std::copy_n [C++]
- std::count [C++]
- std::equal [C++]
- std::fill [C++]
- std::fill_n [C++]
- std::find [C++]
- std::is_permutation [C++]
- std::lexicographical_compare [C++]
- std::move [C++]
- std::move_backward [C++]
- std::reverse [C++]
- std::rotate [C++]
- std::count_if [C++]
- std::partition_copy [C++]
- std::swap [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: 7c2e2e6e4ce39d74142891c5e539b8cc4d028753
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726849"
---
# <a name="ltalgorithmgt-functions"></a>&lt;algoritma&gt; işlevleri

||||
|-|-|-|
|[Taşıma](#alg_move)|[adjacent_find](#adjacent_find)|[all_of](#all_of)|
|[any_of](#any_of)|[binary_search](#binary_search)|[kopyalama](#copy)|
|[copy_backward](#copy_backward)|[copy_if](#copy_if)|[copy_n](#copy_n)|
|[Sayısı](#count)|[count_if](#count_if)|[eşittir](#equal)|
|[equal_range](#equal_range)|[Dolgu](#fill)|[fill_n](#fill_n)|
|[Bul](#find)|[find_end](#find_end)|[find_first_of](#find_first_of)|
|[find_if](#find_if)|[find_if_not](#find_if_not)|[for_each](#for_each)|
|[Oluştur](#generate)|[generate_n](#generate_n)|[içerir](#includes)|
|[inplace_merge](#inplace_merge)|[is_heap](#is_heap)|[is_heap_until](#is_heap_until)|
|[is_partitioned](#is_partitioned)|[is_permutation](#is_permutation)|[is_sorted](#is_sorted)|
|[is_sorted_until](#is_sorted_until)|[iter_swap](#iter_swap)|[lexicographical_compare](#lexicographical_compare)|
|[lower_bound](#lower_bound)|[make_heap](#make_heap)|[en fazla](#max)|
|[max_element](#max_element)|[Birleştirme](#merge)|[Min](#min)|
|[min_element](#min_element)|[minmax](#minmax)|[minmax_element](#minmax_element)|
|[uyuşmazlığı](#mismatch)|[move_backward](#move_backward)|[next_permutation](#next_permutation)|
|[none_of](#none_of)|[nth_element](#nth_element)|[partial_sort](#partial_sort)|
|[partial_sort_copy](#partial_sort_copy)|[Bölüm](#partition)|[partition_copy](#partition_copy)|
|[partition_point](#partition_point)|[pop_heap](#pop_heap)|[prev_permutation](#prev_permutation)|
|[push_heap](#push_heap)|[random_shuffle](#random_shuffle)|[remove](#remove)|
|[remove_copy](#remove_copy)|[remove_copy_if](#remove_copy_if)|[remove_if](#remove_if)|
|[Değiştir](#replace)|[replace_copy](#replace_copy)|[replace_copy_if](#replace_copy_if)|
|[replace_if](#replace_if)|[geriye doğru](#reverse)|[reverse_copy](#reverse_copy)|
|[Döndürme](#rotate)|[rotate_copy](#rotate_copy)|[Arama](#search)|
|[search_n](#search_n)|[set_difference](#set_difference)|[set_intersection](#set_intersection)|
|[set_symmetric_difference](#set_symmetric_difference)|[set_union](#set_union)|[Sıralama](#sort)|
|[sort_heap](#sort_heap)|[stable_partition](#stable_partition)|[stable_sort](#stable_sort)|
|[karışık](#shuffle)|[değiştirme](#swap)|[swap_ranges](#swap_ranges)|
|[transform](#transform)|[benzersiz](#unique)|[unique_copy](#unique_copy)|
|[upper_bound](#upper_bound)|

## <a name="adjacent_find"></a>  adjacent_find

Eşit ya da belirli bir koşulu karşılayan iki bitişik öğeyi arar.

```cpp
template<class ForwardIterator>
ForwardIterator adjacent_find(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator , class BinaryPredicate>
ForwardIterator adjacent_find(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*Comp*<br/>
Aranacak aralıktaki bitişik öğelerin değerlerinin tarafından karşılanması koşul vererek ikili koşul.

### <a name="return-value"></a>Dönüş Değeri

İlk öğeye (ilk sürüm içinde) birbirine eşit olan veya koşuluyla bu tür bir çift öğeleri bulunamadı (sürümünde ikinci), ikili koşul tarafından belirtilen koşulu karşılayan bitişik çiftinin ileriye doğru yineleyici. Aksi halde gösteren bir yineleyici *son* döndürülür.

### <a name="remarks"></a>Açıklamalar

`adjacent_find` Nonmutating sıralı algoritma algoritmasıdır. Aranacak aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve son konuma ilk konumdan erişilebilmelidir. Zaman algoritmanın karmaşıklığı, doğrusal aralığında yer alan öğelerin sayısı.

`operator==` Eşleşen öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

### <a name="example"></a>Örnek

```cpp
// alg_adj_fnd.cpp
// compile with: /EHsc
#include <list>
#include <algorithm>
#include <iostream>

// Returns whether second element is twice the first
bool twice (int elem1, int elem2 )
{
   return elem1 * 2 == elem2;
}

int main()
{
   using namespace std;
   list <int> L;
   list <int>::iterator Iter;
   list <int>::iterator result1, result2;

   L.push_back( 50 );
   L.push_back( 40 );
   L.push_back( 10 );
   L.push_back( 20 );
   L.push_back( 20 );

   cout << "L = ( " ;
   for ( Iter = L.begin( ) ; Iter != L.end( ) ; Iter++ )
      cout << *Iter << " ";
   cout << ")" << endl;

   result1 = adjacent_find( L.begin( ), L.end( ) );
   if ( result1 == L.end( ) )
      cout << "There are not two adjacent elements that are equal."
           << endl;
   else
      cout << "There are two adjacent elements that are equal."
           << "\n They have a value of "
           <<  *( result1 ) << "." << endl;

   result2 = adjacent_find( L.begin( ), L.end( ), twice );
   if ( result2 == L.end( ) )
      cout << "There are not two adjacent elements where the "
           << " second is twice the first." << endl;
   else
      cout << "There are two adjacent elements where "
           << "the second is twice the first."
           << "\n They have values of " << *(result2++);
      cout << " & " << *result2 << "." << endl;
}
```

```Output
L = ( 50 40 10 20 20 )
There are two adjacent elements that are equal.
They have a value of 20.
There are two adjacent elements where the second is twice the first.
They have values of 10 & 20.
```

## <a name="all_of"></a>  all_of

Döndürür **true** koşul olduğunda verilen aralıktaki her bir öğede yok.

```cpp
template<class InputIterator, class Predicate>
bool all_of(
    InputIterator first,
    InputIterator last,
    BinaryPredicatecomp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Koşulu denetlemek başlangıç noktası gösteren bir giriş yineleyici. Yineleyici öğelerini başlatır çeşitli yerlerde işaretler.

*Son*<br/>
Bir koşulu denetleyen öğelerin aralığının sonunu gösteren bir giriş yineleyici.

*Comp*<br/>
Test etmek için bir koşul. Denetlenen bir öğe tarafından karşılanması koşul tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi budur. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** Belirtilen aralıktaki her bir öğede koşul algılanırsa ve **false** koşul en az bir kez algılanmazsa.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü **true** her biri için yalnızca Eğer `N` aralığında `[0,Last - first)`, koşul `comp(*(_First + N))` olduğu **true**.

## <a name="any_of"></a>  any_of

Döndürür **true** koşul olduğunda en az bir kez öğelerin belirtilen aralığında mevcut.

```cpp
template<class InputIterator, class UnaryPredicate>
bool any_of(
    InputIterator first,
    InputIterator last,
    UnaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri bir koşul için bir dizi denetimi başlatmak yeri belirten bir giriş yineleyici.

*Son*<br/>
Bir koşulu denetleyen öğelerin aralığının sonunu gösteren bir giriş yineleyici.

*Comp*<br/>
Test etmek için bir koşul. Bu, bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Test edilen öğe tarafından karşılanması koşul koşulu tanımlar. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** koşul belirtilen aralığında en az bir kez algılanırsa **false** koşulu hiçbir zaman algılanması durumunda.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü **true** yalnızca şu durumlarda, bazı `N` aralığında

`[0, last - first)`, koşul `comp(*(first + N))` geçerlidir.

## <a name="binary_search"></a>  binary_search

Belirtilen değere eşit sıralanmış bir aralıkta bir öğe olup olmadığını ya da bir ikili koşula göre belirtilen anlamda ona eşdeğer bir öğe olup olmadığını sınar.

```cpp
template<class ForwardIterator, class Type>
bool binary_search(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ForwardIterator,  class Type,  class BinaryPredicate>
bool binary_search(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*value*<br/>
Değeri öğe değeriyle eşleşmesi gereken veya ikili koşul tarafından belirtilen öğe değeri ile koşula uyması gerekir.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**doğru** eşit veya belirtilen değere eşdeğer; Aksi takdirde aralıktaki bir öğe bulunursa **false**.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Sıralanan aralık her uygulama için bir önkoşul olarak düzenlenmelidir `binary_search` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak.

Kaynak aralıkları tarafından değiştirilmez `binary_search`.

İleriye doğru Yineleyicilerin değer türlerinin daha küçük olması gerekir-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu bir sıralamaya neden olur öğeler arasında neden olur

Algoritmanın karmaşıklığı, rasgele erişim yineleyicileri için logaritmik ve doğrusal Aksi takdirde doğrusaldır adım sayısı ile (`last` - `first`).

### <a name="example"></a>Örnek

```cpp
// alg_bin_srch.cpp
// compile with: /EHsc
#include <list>
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if (elem1 < 0)
        elem1 = - elem1;
    if (elem2 < 0)
        elem2 = - elem2;
    return elem1 < elem2;
}

int main()
{
    using namespace std;

    list <int> List1;

    List1.push_back( 50 );
    List1.push_back( 10 );
    List1.push_back( 30 );
    List1.push_back( 20 );
    List1.push_back( 25 );
    List1.push_back( 5 );

    List1.sort();

    cout << "List1 = ( " ;
    for ( auto Iter : List1 )
        cout << Iter << " ";
    cout << ")" << endl;

    // default binary search for 10
    if ( binary_search(List1.begin(), List1.end(), 10) )
        cout << "There is an element in list List1 with a value equal to 10."
        << endl;
    else
        cout << "There is no element in list List1 with a value equal to 10."
        << endl;

    // a binary_search under the binary predicate greater
    List1.sort(greater<int>());
    if ( binary_search(List1.begin(), List1.end(), 10, greater<int>()) )
        cout << "There is an element in list List1 with a value greater than 10 "
        << "under greater than." << endl;
    else
        cout << "No element in list List1 with a value greater than 10 "
        << "under greater than." << endl;

    // a binary_search under the user-defined binary predicate mod_lesser
    vector<int> v1;

    for ( auto i = -2; i <= 4; ++i )
    {
        v1.push_back(i);
    }

    sort(v1.begin(), v1.end(), mod_lesser);

    cout << "Ordered using mod_lesser, vector v1 = ( " ;
    for ( auto Iter : v1 )
        cout << Iter << " ";
    cout << ")" << endl;

    if ( binary_search(v1.begin(), v1.end(), -3, mod_lesser) )
        cout << "There is an element with a value equivalent to -3 "
        << "under mod_lesser." << endl;
    else
        cout << "There is not an element with a value equivalent to -3 "
        << "under mod_lesser." << endl;
}
```

## <a name="copy"></a>  kopyalama

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına ileri yönde atar.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator copy(
    InputIterator first,
    InputIterator last,
    OutputIterator destBeg);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kaynak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*Son*<br/>
Kaynak aralıktaki son öğeden bir öncekine olan konumu ele alan giriş yineleyici.

*destBeg*<br/>
Hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedef aralıktaki son öğeden bir öncekine yani konumu belirleyen çıktı Yineleyici, yineleyici `result` + (*son* - *ilk*).

### <a name="remarks"></a>Açıklamalar

Kaynak aralığının geçerli olması gerekir ve hedefte, kopyalanmakta olan tüm öğeleri tutmak için yeterli alan olmalıdır.

Algoritma, ilk öğe ile başlayan sıraya öre kaynak öğeleri kopyaladığı için hedef aralığı kaynak aralığı ile örtüşebilir *son* kaynak aralığı konumunu yer almıyor hedefte Aralık. `copy` Kaynak ve hedef aralıklar arasında örtüşme olmadıkça, öğeleri sola ancak değil sağa kaydırmak için kullanılabilir. Herhangi bir sayıda konumları sağa kaydırmak için [copy_backward](../standard-library/algorithm-functions.md#copy_backward) algoritması.

`copy` Algoritması, yalnızca hedef aralıktaki öğelere yeni değerler atayarak yineleyiciler tarafından gösterilen değerleri değiştirir. Yeni öğe oluşturmak için kullanılamaz ve öğeleri boş bir kapsayıcıya doğrudan ekleyemez.

### <a name="example"></a>Örnek

```cpp
// alg_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1.push_back( 10 * i );

   int ii;
   for ( ii = 0 ; ii <= 10 ; ii++ )
      v2.push_back( 3 * ii );

   cout << "v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To copy the first 3 elements of v1 into the middle of v2
   copy( v1.begin( ), v1.begin( ) + 3, v2.begin( ) + 4 );

   cout << "v2 with v1 insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To shift the elements inserted into v2 two positions
   // to the left
   copy( v2.begin( )+4, v2.begin( ) + 7, v2.begin( ) + 2 );

   cout << "v2 with shifted insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

```Output
v1 = ( 0 10 20 30 40 50 )
v2 = ( 0 3 6 9 12 15 18 21 24 27 30 )
v2 with v1 insert = ( 0 3 6 9 0 10 20 21 24 27 30 )
v2 with shifted insert = ( 0 3 0 10 20 10 20 21 24 27 30 )
```

## <a name="copy_backward"></a>  copy_backward

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
BidirectionalIterator2 copy_backward(
    BidirectionalIterator1 first,
    BidirectionalIterator1 last,
    BidirectionalIterator2 destEnd);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kaynak aralıktaki ilk öğenin konumunu belirleyen çift yönlü yineleyici.

*Son*<br/>
Kaynak aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

*destEnd*<br/>
Hedef aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedef aralıktaki son öğeden bir öncekine yani konumu belirleyen çıktı Yineleyici, yineleyici *destEnd* -(*son* - *ilk*).

### <a name="remarks"></a>Açıklamalar

Kaynak aralığının geçerli olması gerekir ve hedefte, kopyalanmakta olan tüm öğeleri tutmak için yeterli alan olmalıdır.

`copy_backward` Algoritması daha katı gereksinimler uygular kopyalama algoritması. Hem giriş hem de çıkış yineleyicileri çift yönlü olmalıdır.

`copy_backward` Ve [move_backward](../standard-library/algorithm-functions.md#move_backward) algoritmaları, çıktı aralığını hedef aralığın sonuna işaret eden bir yineleyici ile belirleme yalnızca C++ Standart Kitaplığı algoritmalar şunlardır.

Algoritma son öğe ile başlayan sıraya öre kaynak öğeleri kopyaladığı için hedef aralığı kaynak aralığı ile örtüşebilir *ilk* kaynak aralığı konumunu yer almıyor hedefte Aralık. `copy_backward` Kaynak ve hedef aralıklar arasında örtüşme olmadıkça, öğeleri sola değil ancak sağa kaydırmak için kullanılabilir. Konumlar herhangi bir sayıda sola kaydırmak için [kopyalama](../standard-library/algorithm-functions.md#copy) algoritması.

`copy_backward` Algoritması, yalnızca hedef aralıktaki öğelere yeni değerler atayarak yineleyiciler tarafından gösterilen değerleri değiştirir. Yeni öğe oluşturmak için kullanılamaz ve öğeleri boş bir kapsayıcıya doğrudan ekleyemez.

### <a name="example"></a>Örnek

```cpp
// alg_copy_bkwd.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 5 ; ++i )
      v1.push_back( 10 * i );

   int ii;
   for ( ii = 0 ; ii <= 10 ; ++ii )
      v2.push_back( 3 * ii );

   cout << "v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; ++Iter1 )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To copy_backward the first 3 elements of v1 into the middle of v2
   copy_backward( v1.begin( ), v1.begin( ) + 3, v2.begin( ) + 7 );

   cout << "v2 with v1 insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // To shift the elements inserted into v2 two positions
   // to the right
   copy_backward( v2.begin( )+4, v2.begin( ) + 7, v2.begin( ) + 9 );

   cout << "v2 with shifted insert = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

## <a name="copy_if"></a>  copy_if

Öğelerin bir aralıktaki öğeleri kopyalar **true** belirtilen koşulu için.

```cpp
template<class InputIterator, class OutputIterator, class BinaryPredicate>
OutputIterator copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator dest,
    Predicate pred);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Koşulu denetlemek için bir aralık başlangıcını gösteren bir giriş yineleyici.

*Son*<br/>
Aralığın sonunu gösteren bir giriş yineleyici.

*Hedef*<br/>
Hedef kopyalanan öğeleri gösteren bir çıkış yineleyici.

*_Pred*<br/>
Koşul aralıktaki her öğeye karşı test edilmiştir. Bu durum, bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Bir koşulu, bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Eşittir bir çıkış yineleyici *dest* her öğe için koşulu karşılayan sonra artar. Diğer bir deyişle, dönüş değeri eksi *dest* kopyalanan öğelerin sayısına eşittir.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi değerlendirir

`if (pred(*_First + N)) * dest++ = *(_First + N))`

her biri için bir kez `N` aralığında `[0, last - first)`, öğesinin artan değerleri için `N` en düşük değerden başlayarak. Varsa *dest* ve *ilk* depolama bölgelerini belirlemek *dest* aralığında olmamalıdır `[ first, last )`.

## <a name="copy_n"></a>  copy_n

Belirtilen sayıda öğeyi kopyalar.

```cpp
template<class InputIterator, class Size, class OutputIterator>
OutputIterator copy_n(
    InputIterator first,
    Size count,
    OutputIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Nereye kopyalanacağını öğeleri gösteren bir giriş yineleyici.

*Sayısı*<br/>
Kopyalanacak öğe sayısını belirten bir işaretli veya işaretsiz tamsayı türü.

*Hedef*<br/>
Öğelere kopyalamak yeri belirten bir çıkış yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri kopyaladınız olduğu bir çıkış yineleyici döndürür. Üçüncü parametresi, döndürülen değeri aynı olan *dest*.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi değerlendirir `*(dest + N) = *(first + N))` her biri için bir kez `N` aralığında `[0, count)`, öğesinin artan değerleri için `N` en düşük değerden başlayarak. Ardından döndürür `dest + N`. Varsa *dest* ve *ilk* depolama bölgelerini belirlemek *dest* aralığında olmamalıdır `[first, last)`.

## <a name="count"></a>  Sayısı

Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.

```cpp
template<class InputIterator, class Type>
typename iterator_traits<InputIterator>::difference_type count(
    InputIterator first,
    InputIterator last,
    const Type& val);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Geçmesi için aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Son*<br/>
Geçmesi için bir son öğeden aralığındaki konumu ele alan bir giriş yineleyici.

*VAL*<br/>
Sayılacak öğelerin değeri.

### <a name="return-value"></a>Dönüş Değeri

Fark türünü `InputIterator` , aralıktaki öğeleri sayar [ *ilk*, *son* ) değere sahip *val*.

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Bu algoritma şablon işlevi ile herhangi bir koşulu karşılayan öğeleri saymak için genelleştirilmiş [count_if](../standard-library/algorithm-functions.md#count_if).

### <a name="example"></a>Örnek

```cpp
// alg_count.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(10);
    v1.push_back(40);
    v1.push_back(10);

    cout << "v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result;
    result = count(v1.begin(), v1.end(), 10);
    cout << "The number of 10s in v2 is: " << result << "." << endl;
}
```

```Output
v1 = ( 10 20 10 40 10 )
The number of 10s in v2 is: 3.
```

## <a name="count_if"></a>  count_if

Değerleri, belirli bir koşulu karşılayan bir aralıktaki öğelerin sayısını döndürür.

```cpp
template<class InputIterator, class Predicate>
typename iterator_traits<InputIterator>::difference_type count_if(
    InputIterator first,
    InputIterator last,
    Predicate pred);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Son*<br/>
Aranacak bir son öğeden aralığındaki konumu ele alan bir giriş yineleyici.

*_Pred*<br/>
Bir öğe sayılacak ise karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Koşul tarafından belirtilen koşulu karşılayan bir öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu şablonu işlev algoritmasının Genelleştirme, [sayısı](../standard-library/algorithm-functions.md#count), koşul değiştirme "eşit belirli bir değeri" ile herhangi bir koşul.

### <a name="example"></a>Örnek

```cpp
// alg_count_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater10(int value)
{
    return value > 10;
}

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter;

    v1.push_back(10);
    v1.push_back(20);
    v1.push_back(10);
    v1.push_back(40);
    v1.push_back(10);

    cout << "v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(), greater10);
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;
}
```

```Output
v1 = ( 10 20 10 40 10 )
The number of elements in v1 greater than 10 is: 2.
```

## <a name="equal"></a>  eşittir

İki aralığı öğe öğe için eşitlik ya da bir ikili koşula göre belirtilen anlamda denklik karşılaştırır.

Kullanım `std::equal` farklı kapsayıcı türlerinde öğeleri karşılaştırırken (örneğin `vector` ve `list`) veya farklı bir öğe türleri karşılaştırırken ya da alt kapsayıcıları aralıklarına karşılaştırmak gerektiğinde. Aksi takdirde aynı kapsayıcı türü aynı türdeki öğeleri karşılaştırırken üye olmayan kullanın `operator==` her kapsayıcı için sağlanır.

İkinci aralığı için tek bir yineleyici yalnızca aşırı farklar algılamaz ikinci aralığın ilk aralığından daha uzun ve ikinci aralığı kısaysa tanımsız davranışlara neden çünkü çift aralıklı C ++ 14 kodda aşırı yüklemeleri kullanın ilk aralığından daha.

```cpp
template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    BinaryPredicate Comp); // C++14

template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    InputIterator2  Last2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1  First1,
    InputIterator1  Last1,
    InputIterator2  First2,
    InputIterator2  Last2,
    BinaryPredicate Comp);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Test edilecek ilk aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*last1*<br/>
Test edilecek ilk aralığın son öğesinde geçmiş konumu ele alan bir giriş yineleyici.

*first2*<br/>
Test edilecek ikinci aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*first2*<br/>
Test edilecek ikinci aralıktaki son öğeden bir öncekine konumu ele alan bir giriş yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**doğru** aynı veya eşdeğer karşılaştırıldığında öğeye göre; Aksi takdirde ikili koşul altında aralıkları ve yalnızca, **false**.

### <a name="remarks"></a>Açıklamalar

Aranacak aralık geçerli olmalı; Tüm yineleyiciler tekrar başvurulabilir olmalı ve son konuma ilk konumdan erişilebilmelidir.

Eşit uzunluktaki iki aralık varsa zaman algoritmanın karmaşıklığı, doğrusal aralığında yer alan öğelerin sayısı. İşlevi hemen döndürür **false**.

Ne `operator==` ya da kullanıcı tanımlı koşul, bir eşdeğerlik ilişkisi bu simetrik, yansıma ve işlenenleri arasındaki geçişli dayatmak için gereklidir.

### <a name="example"></a>Örnek

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main()
{
    vector<int> v1 { 0, 5, 10, 15, 20, 25 };
    vector<int> v2 { 0, 5, 10, 15, 20, 25 };
    vector<int> v3 { 0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50 };

    // Using range-and-a-half equal:
    bool b = equal(v1.begin(), v1.end(), v2.begin());
    cout << "v1 and v2 are equal: "
       << b << endl; // true, as expected

    b = equal(v1.begin(), v1.end(), v3.begin());
    cout << "v1 and v3 are equal: "
       << b << endl; // true, surprisingly

    // Using dual-range equal:
    b = equal(v1.begin(), v1.end(), v3.begin(), v3.end());
    cout << "v1 and v3 are equal with dual-range overload: "
       << b << endl; // false

    return 0;
}

```

## <a name="equal_range"></a>  equal_range

Belirli bir sıralanmış aralıktaki tüm öğeleri belirli bir değere eşdeğer alt aralığı bulur.

```cpp
template<class ForwardIterator, class Type>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val);

template<class ForwardIterator, class Type, class Predicate>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val,
    Predicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*VAL*<br/>
Sıralanan aralıkta Aranan değer.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Tüm öğeleri olduğu eşdeğer Aranan aralığın içerdiği alt ileriye doğru Yineleyicilerin bir çiftini *val* kullanılan ikili koşul tarafından tanımlanan anlamında (ya da *comp* Varsayılan, daha az-daha).

Aralıktaki hiçbir öğe eşit değilse *val*, döndürülen İleri yineleyici çifti eşit ve noktasını belirtmek burada *val* aralığın sırasını bozmadan araya eklenebileceği.

### <a name="remarks"></a>Açıklamalar

Algoritmaya göre döndürülen çiftin ilk yineleyici [lower_bound](../standard-library/algorithm-functions.md#lower_bound), ikinci yineleyicisi ise [upper_bound](../standard-library/algorithm-functions.md#upper_bound).

Aralığın öğesine sağlanan koşula göre sıralanmalıdır `equal_range`. Örneğin, büyük-tahminden daha aralık azalan düzende sıralanmalıdır.

Tarafından döndürülen yineleyici çifti tarafından tanımlanan muhtemelen boş alt öğeleri `equal_range` eşdeğer olacaktır *val* kullanılan koşul tarafından tanımlanan içinde.

Algoritmanın karmaşıklığı, rasgele erişim yineleyicileri için logaritmik ve doğrusal Aksi takdirde doğrusaldır adım sayısı ile (*son* - *ilk*).

### <a name="example"></a>Örnek

```cpp
// alg_equal_range.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>()
#include <iostream>
#include <string>
using namespace std;

template<class T> void dump_vector( const vector<T>& v, pair<typename vector<T>::iterator, typename vector<T>::iterator> range )
{
    // prints vector v with range delimited by [ and ]

    for ( typename vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        if ( i == range.first )
        {
            cout << "[ ";
        }
        if ( i == range.second )
        {
            cout << "] ";
        }

        cout << *i << " ";
    }
    cout << endl;
}

template<class T> void equal_range_demo( const vector<T>& original_vector, T val )
{
    vector<T> v(original_vector);

    sort( v.begin(), v.end() );
    cout << "Vector sorted by the default binary predicate <:" << endl << '\t';
    for ( vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        cout << *i << " ";
    }
    cout << endl << endl;

    pair<vector<T>::iterator, vector<T>::iterator> result
        = equal_range( v.begin(), v.end(), val );

    cout << "Result of equal_range with val = " << val << ":" << endl << '\t';
    dump_vector( v, result );
    cout << endl;
}

template<class T, class F> void equal_range_demo( const vector<T>& original_vector, T val, F pred, string predname )
{
    vector<T> v(original_vector);

    sort( v.begin(), v.end(), pred );
    cout << "Vector sorted by the binary predicate " << predname << ":" << endl << '\t';
    for ( typename vector<T>::const_iterator i = v.begin(); i != v.end(); ++i )
    {
        cout << *i << " ";
    }
    cout << endl << endl;

    pair<typename vector<T>::iterator, typename vector<T>::iterator> result
        = equal_range( v.begin(), v.end(), val, pred );

    cout << "Result of equal_range with val = " << val << ":" << endl << '\t';
    dump_vector( v, result );
    cout << endl;
}

// Return whether absolute value of elem1 is less than absolute value of elem2
bool abs_lesser( int elem1, int elem2 )
{
    return abs(elem1) < abs(elem2);
}

// Return whether string l is shorter than string r
bool shorter_than(const string& l, const string& r)
{
    return l.size() < r.size();
}

int main()
{
    vector<int> v1;

    // Constructing vector v1 with default less than ordering
    for ( int i = -1; i <= 4; ++i )
    {
        v1.push_back(i);
    }

    for ( int i =-3; i <= 0; ++i )
    {
        v1.push_back( i );
    }

    equal_range_demo( v1, 3 );
    equal_range_demo( v1, 3, greater<int>(), "greater" );
    equal_range_demo( v1, 3, abs_lesser, "abs_lesser" );

    vector<string> v2;

    v2.push_back("cute");
    v2.push_back("fluffy");
    v2.push_back("kittens");
    v2.push_back("fun");
    v2.push_back("meowmeowmeow");
    v2.push_back("blah");

    equal_range_demo<string>( v2, "fred" );
    equal_range_demo<string>( v2, "fred", shorter_than, "shorter_than" );
}

```

## <a name="fill"></a>  Dolgu

Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.

```cpp
template<class ForwardIterator, class Type>
void fill(
    ForwardIterator first,
    ForwardIterator last,
    const Type& val);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Geçmesi için aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Geçmesi için konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*VAL*<br/>
Aralığı içindeki öğelere atanmış değer [ *ilk*, *son*).

### <a name="remarks"></a>Açıklamalar

Hedef aralığı geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve son konuma ilk konumdan erişilebilmelidir. Karmaşıklık aralığı boyutu ile doğrusaldır.

### <a name="example"></a>Örnek

```cpp
// alg_fill.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Fill the last 5 positions with a value of 2
   fill( v1.begin( ) + 5, v1.end( ), 2 );

   cout << "Modified v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 30 35 40 45 )
Modified v1 = ( 0 5 10 15 20 2 2 2 2 2 )
```

## <a name="fill_n"></a>  fill_n

Belirli bir öğeyle başlayan bir aralıktaki öğeleri belirtilen sayıda yeni bir değer atar.

```cpp
template<class OutputIterator, class Size, class Type>
OutputIterator fill_n(
    OutputIterator First,
    Size Count,
    const Type& Val);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Değeri atanacak aralıktaki ilk öğenin konumunu bulan çıktı yineleyici *Val*.

*Sayısı*<br/>
Değerin atanacağı öğe sayısını belirten bir işaretli veya işaretsiz tamsayı türü.

*VAL*<br/>
Aralığı içindeki öğelere atanmış değer [ *ilk*, *First + Count*).

### <a name="return-value"></a>Dönüş Değeri

Son öğeyi izleyen öğe için bir yineleyici doldurulmuş varsa *sayısı* > sıfır, aksi takdirde ilk öğe.

### <a name="remarks"></a>Açıklamalar

Hedef aralığı geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve son konuma ilk konumdan erişilebilmelidir. Karmaşıklık aralığı boyutu ile doğrusaldır.

### <a name="example"></a>Örnek

```cpp
// alg_fill_n.cpp
// compile using /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector <int> v;

    for ( auto i = 0 ; i < 9 ; ++i )
        v.push_back( 0 );

    cout << "  vector v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the first 3 positions with a value of 1, saving position.
    auto pos = fill_n( v.begin(), 3, 1 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the next 3 positions with a value of 2, using last position.
    fill_n( pos, 3, 2 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;

    // Fill the last 3 positions with a value of 3, using relative math.
    fill_n( v.end()-3, 3, 3 );

    cout << "modified v = ( " ;
    for ( const auto &w : v )
        cout << w << " ";
    cout << ")" << endl;
}

```

## <a name="find"></a>  Bul

Bir öğenin belirli bir değere sahip olan aralıktaki ilk geçtiği konumu bulur.

```cpp
template<class InputIterator, class T>
InputIterator find(
    InputIterator first,
    InputIterator last,
    const T& val);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
İçin belirtilen değer aranacak aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Son*<br/>
İçin belirtilen değer aranacak aralıktaki son öğeden sonraki birinci konum ele alan bir giriş yineleyici.

*VAL*<br/>
Aranacak değer.

### <a name="return-value"></a>Dönüş Değeri

Aranacak aralıktaki belirtilen değeri ilk oluşum ele alan giriş yineleyici. Eşdeğer bir değer ile herhangi bir öğe bulunursa döndürür *son*.

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Örnek kodu kullanarak `find()`, bkz: [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="find_end"></a>  find_end

Belirli bir diziye özdeş veya bir ikili koşula göre belirtildiği şekilde denk olan son dizi için bir aralık arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_end(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class Pred>
ForwardIterator1 find_end(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2,
    Pred Comp);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*last1*<br/>
Aranacak bir önceki öğenin konumunu son öğeyi aralıktaki ileriye doğru yineleyici.

*first2*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Soyadı2*<br/>
Aramak için bir önceki öğenin konumunu son öğeyi aralıktaki ileriye doğru yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Son dizi içinde ilk öğenin konumunu bulan ileriye doğru yineleyici [First1, Last1) [First2, Soyadı2). belirtilen sıralamadaki eşleşen

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her bir dizisi içinde son konuma ilk konumdan erişilebilmelidir.

### <a name="example"></a>Örnek

```cpp
// alg_find_end.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main()
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for a match to L1 under identity
   vector <int>::iterator result1;
   result1 = find_end ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a match of L1 in v1 that begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = find_end ( v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent to those\n in v2 under the binary "
           << "predicate twice and that begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 5 10 15 20 )
Vector v2 = ( 20 30 40 )
There is a match of L1 in v1 that begins at position 7.
There is a sequence of elements in v1 that are equivalent to those
in v2 under the binary predicate twice and that begins at position 8.
```

## <a name="find_first_of"></a>  find_first_of

Bir hedef aralığındaki çeşitli değerlerden herhangi birinin ilk geçtiği yeri veya bir ikili koşula göre belirtilen bir öğeler kümesine belirtildiği şekilde denk olan çeşitli öğelerin geçtiği ilk yeri arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_first_of(
    ForwardIterator1  first1,
    ForwardIterator1 Last1,
    ForwardIterator2  first2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 find_first_of(
    ForwardIterator1  first1,
    ForwardIterator1 Last1,
    ForwardIterator2  first2,
    ForwardIterator2 Last2,
    BinaryPredicate  comp);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*last1*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*first2*<br/>
Eşleştirilecek aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Soyadı2*<br/>
Eşleştirilecek konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sıra veya eşleşen ilk diziyi ilk öğenin konumunu bulan ileriye doğru yineleyici bir ikili koşula göre belirtilen anlamda eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her bir dizisi içinde son konuma ilk konumdan erişilebilmelidir.

### <a name="example"></a>Örnek

```cpp
// alg_find_first_of.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main()
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 3 ; ii <= 4 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for first match to L1 under identity
   vector <int>::iterator result1;
   result1 = find_first_of ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is at least one match of L1 in v1"
           << "\n and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = find_first_of ( v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent\n to those in v2 under the binary "
           << "predicate twice\n and the first one begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 15 20 )
Vector v2 = ( 20 30 40 )
There is at least one match of L1 in v1
and the first one begins at position 3.
There is a sequence of elements in v1 that are equivalent
to those in v2 under the binary predicate twice
and the first one begins at position 2.
```

## <a name="find_if"></a>  find_if

Bir öğenin belirli bir koşulu karşıladığı aralıktaki ilk geçtiği konumu bulur.

```cpp
template<class InputIterator, class Predicate>
InputIterator find_if(
    InputIterator first,
    InputIterator last,
    Predicate pred);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Son*<br/>
Aranacak bir son öğeden aralığındaki konumu ele alan bir giriş yineleyici.

*Pred*<br/>
Kullanıcı tanımlı işlevin doğrulama nesnesi veya [lambda ifadesi](../cpp/lambda-expressions-in-cpp.md) Aranan öğesi tarafından karşılanması koşul tanımlar. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** (memnun) veya **false** (karşılanmadı). İmzası *pred* etkin olmalıdır `bool pred(const T& arg);`burada `T` bir tür olan `InputIterator` başvurusu kaldırıldığında örtük olarak dönüştürülebilir. **Const** anahtar sözcüğü, yalnızca işlev nesnesi veya lambda bağımsız değişken değiştirmemelisiniz olduğunu göstermek için gösterilir.

### <a name="return-value"></a>Dönüş Değeri

Koşul tarafından belirtilen bir koşulu karşıladığı aralıktaki ilk öğeyi gösteren bir giriş yineleyici (koşul sonuçlanıyor **true**). Koşul karşılamak için hiçbir öğe bulunamazsa döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Bu şablonu işlev algoritmasının Genelleştirme, [Bul](../standard-library/algorithm-functions.md#find), koşul değiştirme "eşit belirli bir değeri" ile herhangi bir koşul. Mantıksal (Bul koşulu karşılamayan ilk öğeyi), ters görmek için [find_if_not](../standard-library/algorithm-functions.md#find_if_not).

### <a name="example"></a>Örnek

```cpp
// cl.exe /W4 /nologo /EHsc /MTd
#include <vector>
#include <algorithm>
#include <iostream>
#include <string>

using namespace std;

template <typename S> void print(const S& s) {
for (const auto& p : s) {
        cout << "(" << p << ") ";
    }
    cout << endl;
}

// Test std::find()
template <class InputIterator, class T>
void find_print_result(InputIterator first, InputIterator last, const T& value) {

    // call <algorithm> std::find()
    auto p = find(first, last, value);

    cout << "value " << value;
    if (p == last) {
        cout << " not found." << endl;
    } else {
        cout << " found." << endl;
    }
}

// Test std::find_if()
template <class InputIterator, class Predicate>
void find_if_print_result(InputIterator first, InputIterator last,
    Predicate Pred, const string& Str) {

    // call <algorithm> std::find_if()
    auto p = find_if(first, last, Pred);

    if (p == last) {
        cout << Str << " not found." << endl;
    } else {
        cout << "first " << Str << " found: " << *p << endl;
    }
}

// Function to use as the UnaryPredicate argument to find_if() in this example
bool is_odd_int(int i) {
    return ((i % 2) != 0);
}

int main()
{
    // Test using a plain old array.
    const int x[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    cout << "array x[] contents: ";
    print(x);
    // Using non-member std::begin()/std::end() to get input iterators for the plain old array.
    cout << "Test std::find() with array..." << endl;
    find_print_result(begin(x), end(x), 10);
    find_print_result(begin(x), end(x), 42);
    cout << "Test std::find_if() with array..." << endl;
    find_if_print_result(begin(x), end(x), is_odd_int, "odd integer"); // function name
    find_if_print_result(begin(x), end(x), // lambda
        [](int i){ return ((i % 2) == 0); }, "even integer");

    // Test using a vector.
    vector<int> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back((i + 1) * 10);
    }
    cout << endl << "vector v contents: ";
    print(v);
    cout << "Test std::find() with vector..." << endl;
    find_print_result(v.begin(), v.end(), 20);
    find_print_result(v.begin(), v.end(), 12);
    cout << "Test std::find_if() with vector..." << endl;
    find_if_print_result(v.begin(), v.end(), is_odd_int, "odd integer");
    find_if_print_result(v.begin(), v.end(), // lambda
        [](int i){ return ((i % 2) == 0); }, "even integer");
}

```

## <a name="find_if_not"></a>  find_if_not

Bir koşulu karşılamayan belirtilen aralıktaki ilk öğeyi döndürür.

```cpp
template<class InputIterator, class Predicate>
InputIterator find_if_not(
    InputIterator first,
    InputIterator last,
    Predicate pred);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Son*<br/>
Aranacak bir son öğeden aralığındaki konumu ele alan bir giriş yineleyici.

*Pred*<br/>
Kullanıcı tanımlı işlevin doğrulama nesnesi veya [lambda ifadesi](../cpp/lambda-expressions-in-cpp.md) Aranan öğesi tarafından karşılanması değil koşulu tanımlar. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** (memnun) veya **false** (karşılanmadı). İmzası *pred* etkin olmalıdır `bool pred(const T& arg);`burada `T` bir tür olan `InputIterator` başvurusu kaldırıldığında örtük olarak dönüştürülebilir. **Const** anahtar sözcüğü, yalnızca işlev nesnesi veya lambda bağımsız değişken değiştirmemelisiniz olduğunu göstermek için gösterilir.

### <a name="return-value"></a>Dönüş Değeri

Koşul tarafından belirtilen koşulu karşılamayan aralıktaki ilk öğeyi gösteren bir giriş yineleyici (koşul sonuçlanıyor **false**). Tüm öğeler koşulu karşılaması durumunda (koşul sonuçlanıyor **true** her öğe için), döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Bu şablonu işlev algoritmasının Genelleştirme, [Bul](../standard-library/algorithm-functions.md#find), koşul değiştirme "eşit belirli bir değeri" ile herhangi bir koşul. Mantıksal (Bul koşulu karşılayan ilk öğeyi), ters görmek için [find_if](../standard-library/algorithm-functions.md#find_if).

Bir kolayca uyarlanabilir kod örneği için `find_if_not()`, bkz: [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="for_each"></a>  for_each

Bir aralıktaki ileriye doğru sıradaki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.

```cpp
template<class InputIterator, class Function>
Function for_each(
    InputIterator first,
    InputIterator last,
    Function func);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Üzerinde yapılacak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*Son*<br/>
İşlenemeyen bir son öğeden aralığındaki konumu ele alan giriş yineleyici.

*_Func*<br/>
Aralıktaki her öğeye uygulanan kullanıcı tanımlı işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Aralıktaki tüm öğeleri için uygulandıktan sonra işlev nesnesi bir kopyası.

### <a name="remarks"></a>Açıklamalar

Algoritma `for_each` değişikliği bir aralıktaki her bir öğenin farklı, kullanıcı tarafından belirtilen şekilde izin vermek çok esnektir. Şablonlaştırılmış işlevleri farklı parametreler geçirerek değiştirilmiş bir biçimde yeniden. Kullanıcı tanımlı işlevleri algoritması aralıktaki tüm öğeleri işledikten sonra döndürebileceği bir iç durum içerisinde bilgileri birikebilir.

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Karmaşıklığı en fazla ile doğrusal ( *son* -  *ilk*) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_for_each.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

// The function object multiplies an element by a Factor
template <class Type>
class MultValue
{
private:
   Type Factor;   // The value to multiply by
public:
   // Constructor initializes the value to multiply by
   MultValue ( const Type& val ) : Factor ( val ) {
   }

   // The function call for the element to be multiplied
   void operator( ) ( Type& elem ) const
   {
      elem *= Factor;
   }
};

// The function object to determine the average
class Average
{
private:
   long num;      // The number of elements
   long sum;      // The sum of the elements
public:
   // Constructor initializes the value to multiply by
   Average( ) : num ( 0 ) , sum ( 0 )
   {
   }

   // The function call to process the next elment
   void operator( ) ( int elem ) \
   {
      num++;      // Increment the element count
      sum += elem;   // Add the value to the partial sum
   }

   // return Average
   operator double( )
   {
      return  static_cast <double> (sum) /
      static_cast <double> (num);
   }
};

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   // Constructing vector v1
   int i;
   for ( i = -4 ; i <= 2 ; i++ )
   {
      v1.push_back(  i );
   }

   cout << "Original vector  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Using for_each to multiply each element by a Factor
   for_each ( v1.begin( ), v1.end( ), MultValue<int> ( -2 ) );

   cout << "Multiplying the elements of the vector v1\n "
        <<  "by the factor -2 gives:\n v1mod1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // The function object is templatized and so can be
   // used again on the elements with a different Factor
   for_each (v1.begin( ), v1.end( ), MultValue<int> (5 ) );

   cout << "Multiplying the elements of the vector v1mod\n "
        <<  "by the factor 5 gives:\n v1mod2 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // The local state of a function object can accumulate
   // information about a sequence of actions that the
   // return value can make available, here the Average
   double avemod2 = for_each ( v1.begin( ), v1.end( ),
      Average( ) );
   cout << "The average of the elements of v1 is:\n Average ( v1mod2 ) = "
        << avemod2 << "." << endl;
}
```

```Output
Original vector  v1 = ( -4 -3 -2 -1 0 1 2 ).
Multiplying the elements of the vector v1
by the factor -2 gives:
v1mod1 = ( 8 6 4 2 0 -2 -4 ).
Multiplying the elements of the vector v1mod
by the factor 5 gives:
v1mod2 = ( 40 30 20 10 0 -10 -20 ).
The average of the elements of v1 is:
Average ( v1mod2 ) = 10.
```

## <a name="generate"></a>  Oluştur

Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki her öğeye atar.

```cpp
template<class ForwardIterator, class Generator>
void generate(
    ForwardIterator first,
    ForwardIterator last,
    Generator _Gen);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kendisine atanan değerler aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Kendisine atanan değerler aralıktaki son öğeden sonraki birinci konum ele alan ileriye doğru yineleyici.

*_Gen*<br/>
Aralığındaki öğelerin her biri için atanacak değerleri oluşturmak için kullanılan bağımsız değişken olmadan çağrılan bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi bir aralıktaki her öğe için çağrılır ve her çağrıldığında aynı değeri döndürmesi gerekmez. , Örneğin, bir dosyadan okunan veya başvurmak ve bir yerel durumunu değiştir. Üreticinin sonuç türü aralığı için ileriye doğru Yineleyicilerin değer türüne dönüştürülebilir olmalıdır.

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Tam olarak karmaşıklığı ile doğrusal ( `last`  -   `first`) gerektiği Oluşturucu çağrıları.

### <a name="example"></a>Örnek

```cpp
// alg_generate.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

int main()
{
   using namespace std;

   // Assigning random values to vector integer elements
   vector <int> v1 ( 5 );
   vector <int>::iterator Iter1;
   deque <int> deq1 ( 5 );
   deque <int>::iterator d1_Iter;

   generate ( v1.begin( ), v1.end( ), rand );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Assigning random values to deque integer elements
   generate ( deq1.begin( ), deq1.end( ), rand );

   cout << "Deque deq1 is ( " ;
   for ( d1_Iter = deq1.begin( ) ; d1_Iter != deq1.end( ) ; d1_Iter++ )
      cout << *d1_Iter << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 41 18467 6334 26500 19169 ).
Deque deq1 is ( 15724 11478 29358 26962 24464 ).
```

## <a name="generate_n"></a>  generate_n

Belirtilen bir aralıktaki öğelerin sayısı bir işlev nesnesi tarafından oluşturulan değerleri atar ve bir önceki öğenin son atanan değere konumunu döndürür.

```cpp
template<class OutputIterator, class Diff, class Generator>
void generate_n(
    OutputIterator First,
    Diff Count,
    Generator Gen);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kendisine atanan değerler aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*Sayısı*<br/>
Oluşturucu işlevi tarafından bir değerin atanacağı öğe sayısını belirten bir işaretli veya işaretsiz tamsayı türü.

*Genel*<br/>
Aralığındaki öğelerin her biri için atanacak değerleri oluşturmak için kullanılan bağımsız değişken olmadan çağrılan bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi bir aralıktaki her öğe için çağrılır ve her çağrıldığında aynı değeri döndürmesi gerekmez. , Örneğin, bir dosyadan okunan veya başvurmak ve bir yerel durumunu değiştir. Üreticinin sonuç türü aralığı için ileriye doğru Yineleyicilerin değer türüne dönüştürülebilir olmalıdır.

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Tam olarak karmaşıklığı ile doğrusal `Count` çağrıları için gerekli Oluşturucu.

### <a name="example"></a>Örnek

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <vector>
#include <deque>
#include <iostream>
#include <string>
#include <algorithm>
#include <random>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    const int elemcount = 5;
    vector<int> v(elemcount);
    deque<int> dq(elemcount);

    // Set up random number distribution
    random_device rd;
    mt19937 engine(rd());
    uniform_int_distribution<int> dist(-9, 9);

    // Call generate_n, using a lambda for the third parameter
    generate_n(v.begin(), elemcount, [&](){ return dist(engine); });
    print("vector v is: ", v);

    generate_n(dq.begin(), elemcount, [&](){ return dist(engine); });
    print("deque dq is: ", dq);
}

```

## <a name="includes"></a>  içerir

Sıralanmış bir aralığın ikinci bir sıralanmış aralıkta kapsanan tüm öğeleri içerip içermediğini sınar, burada öğeler arasındaki sıralama veya denklik ölçütü bir ikili koşula göre belirlenebilir.

```cpp
template<class InputIterator1, class InputIterator2>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
İkinci tüm öğelerinin ilk olup içerdiği için test edilecek ilk iki sıralanmış kaynak aralıktaki ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
İkinci tüm öğelerinin ilk olup içerdiği için test edilecek bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa, ele alan bir giriş yineleyici.

*first2*<br/>
Kaynak aralıktaki ilk ikinci tüm öğelerini olup içerdiği için test edilecek art arda iki saniye içinde ilk öğenin konumunu ele alan giriş yineleyici sıralanır.

*Soyadı2*<br/>
İkinci tüm öğelerinin ilk olup içerdiği için test edilecek iki ardışık sıralanmış kaynak aralık saniye içinde bir son öğeden önceki öğenin konumunu ele alan giriş yineleyici.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilk sıralanmış aralıkta ikinci sıralanmış aralıktaki; tüm öğeler içeriyorsa, aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu test etmeniz gereken başka bir, ikinci aralığın bir alt kümesini ilk kaynak aralığı olup olmadığını belirledi yoludur.

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her bir dizisi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak önkoşul algoritmasının uygulamaya aynı olarak sıralama uygun olarak içerdiğinden aralıkları her düzenlenmelidir sıralanmış kaynak var.

Kaynak aralıkları algoritması tarafından değiştirilmez `merge`.

Giriş Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Belirtilen bir ikili koşul altında ilk sıralanmış aralıktaki tüm öğeleri bu ikinci bir sıralanmış aralıkta eşdeğer sıralamaya sahip olup olmadığını algoritması daha kesin bir şekilde test eder.

Algoritmanın karmaşıklığı, en fazla 2 ile doğrusal \* (( *last1 - first1*)-(* Soyadı2 - first2 *)) - 1 karşılaştırmalar için boş olmayan kaynak aralık.

### <a name="example"></a>Örnek

```cpp
// alg_includes.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1a, v1b;
   vector <int>::iterator Iter1a,  Iter1b;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -2 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-2 ; ii <= 3 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        << "binary predicate less than is v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b );
   vector <int>::iterator Iter2a,  Iter2b;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );
   v2a.pop_back( );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is v2a = ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is v2b = ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ;
   vector <int>::iterator Iter3a, Iter3b;
   reverse (v3a.begin( ), v3a.end( ) );
   v3a.pop_back( );
   v3a.pop_back( );
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3a = ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3b = ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To test for inclusion under an asscending order
   // with the default binary predicate less <int>( )
   bool Result1;
   Result1 = includes ( v1a.begin( ), v1a.end( ),
      v1b.begin( ), v1b.end( ) );
   if ( Result1 )
      cout << "All the elements in vector v1b are "
           << "contained in vector v1a." << endl;
   else
      cout << "At least one of the elements in vector v1b "
           << "is not contained in vector v1a." << endl;

   // To test for inclusion under descending
   // order specify binary predicate greater<int>( )
   bool Result2;
   Result2 = includes ( v2a.begin( ), v2a.end( ),
      v2b.begin( ), v2b.end( ), greater <int>( ) );
   if ( Result2 )
      cout << "All the elements in vector v2b are "
           << "contained in vector v2a." << endl;
   else
      cout << "At least one of the elements in vector v2b "
           << "is not contained in vector v2a." << endl;

   // To test for inclusion under a user
   // defined binary predicate mod_lesser
   bool Result3;
   Result3 = includes ( v3a.begin( ), v3a.end( ),
      v3b.begin( ), v3b.end( ), mod_lesser );
   if ( Result3 )
      cout << "All the elements in vector v3b are "
           << "contained under mod_lesser in vector v3a."
           << endl;
   else
      cout << "At least one of the elements in vector v3b is "
           << " not contained under mod_lesser in vector v3a."
           << endl;
}
```

```Output
Original vector v1a with range sorted by the
binary predicate less than is v1a = ( -2 -1 0 1 2 3 4 ).
Original vector v1b with range sorted by the
binary predicate less than is v1b = ( -2 -1 0 1 2 3 ).
Original vector v2a with range sorted by the
binary predicate greater is v2a = ( 4 3 2 1 0 -1 ).
Original vector v2b with range sorted by the
binary predicate greater is v2b = ( 3 2 1 0 -1 -2 ).
Original vector v3a with range sorted by the
binary predicate mod_lesser is v3a = ( 0 1 2 3 4 ).
Original vector v3b with range sorted by the
binary predicate mod_lesser is v3b = ( 0 -1 1 -2 2 3 ).
All the elements in vector v1b are contained in vector v1a.
At least one of the elements in vector v2b is not contained in vector v2a.
At least one of the elements in vector v3b is  not contained under mod_lesser in vector v3a.
```

## <a name="inplace_merge"></a>  inplace_merge

Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class BidirectionalIterator>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last);

template<class BidirectionalIterator, class Predicate>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last,
    Predicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
İlk iki ardışık ilk öğenin konumunu bulan çift yönlü bir yineleyici aralıklarını birleştirilir ve tek bir aralığa sıralanmış sıralanır.

*Orta*<br/>
Art arda iki saniye içinde ilk öğenin konumunu bulan çift yönlü yineleyici aralıklarını birleştirilir ve tek bir aralığa sıralanmış sıralanır.

*Son*<br/>
Konum, ardışık iki saniye içinde geçen son öğe adresleme çift yönlü bir yineleyici aralıklarını birleştirilir ve tek bir aralığa sıralanmış sıralanır.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış ardışık aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her bir dizisi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Sıralanmış ardışık aralıktaki her uygulama için bir önkoşul olarak düzenlenmelidir `inplace_merge` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak. Her aralık içindeki öğelerin göreli sırasını korunduğu kalıcı bir işlemdir. Her iki kaynak aralıklardaki eşdeğer öğelerin olduğunda, aralığın ilk birleşik aralığında ikinci öğesi önündeki öğesidir.

Algoritma geçici bir arabelleğe bellek ayırır gibi kullanılabilir belleğe karmaşıklığına bağlıdır. Yeterli bellek varsa, en iyi durum ile doğrusal (* - Soyadı *) - 1 karşılaştırmalar; yardımcı bellek varsa, en kötü durumda *N* günlük *(N)* burada  *N* = (* - Soyadı*).

### <a name="example"></a>Örnek

```cpp
// alg_inplace_merge.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      //For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2, Iter3;

   // Constructing vector v1 with default less-than ordering
   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =-5 ; ii <= 0 ; ii++ )
   {
      v1.push_back(  ii  );
   }

   cout << "Original vector v1 with subranges sorted by the\n "
        <<  "binary predicate less than is  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Constructing vector v2 with ranges sorted by greater
   vector <int> v2 ( v1 );
   vector <int>::iterator break2;
   break2 = find ( v2.begin( ), v2.end( ), -5 );
   sort ( v2.begin( ), break2 , greater<int>( ) );
   sort ( break2 , v2.end( ), greater<int>( ) );
   cout << "Original vector v2 with subranges sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Constructing vector v3 with ranges sorted by mod_lesser
   vector <int> v3 ( v1 );
   vector <int>::iterator break3;
   break3 = find ( v3.begin( ), v3.end( ), -5 );
   sort ( v3.begin( ), break3 , mod_lesser );
   sort ( break3 , v3.end( ), mod_lesser );
   cout << "Original vector v3 with subranges sorted by the\n "
        << "binary predicate mod_lesser is v3 = ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;

   vector <int>::iterator break1;
   break1 = find (v1.begin( ), v1.end( ), -5 );
   inplace_merge ( v1.begin( ), break1, v1.end( ) );
   cout << "Merged inplace with default order,\n vector v1mod = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To merge inplace in descending order, specify binary
   // predicate greater<int>( )
   inplace_merge ( v2.begin( ), break2 , v2.end( ) , greater<int>( ) );
   cout << "Merged inplace with binary predicate greater specified,\n "
        << "vector v2mod = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Applying a user defined (UD) binary predicate mod_lesser
   inplace_merge ( v3.begin( ), break3, v3.end( ), mod_lesser );
   cout << "Merged inplace with binary predicate mod_lesser specified,\n "
        << "vector v3mod = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 with subranges sorted by the
binary predicate less than is  v1 = ( 0 1 2 3 4 5 -5 -4 -3 -2 -1 0 )
Original vector v2 with subranges sorted by the
binary predicate greater is v2 = ( 5 4 3 2 1 0 0 -1 -2 -3 -4 -5 )
Original vector v3 with subranges sorted by the
binary predicate mod_lesser is v3 = ( 0 1 2 3 4 5 0 -1 -2 -3 -4 -5 )
Merged inplace with default order,
vector v1mod = ( -5 -4 -3 -2 -1 0 0 1 2 3 4 5 )
Merged inplace with binary predicate greater specified,
vector v2mod = ( 5 4 3 2 1 0 0 -1 -2 -3 -4 -5 )
Merged inplace with binary predicate mod_lesser specified,
vector v3mod = ( 0 0 1 -1 2 -2 3 -3 4 -4 5 -5 )
```

## <a name="is_heap"></a>  is_heap

Döndürür **true** Belirtilen aralıktaki öğeler bir yığın biçimlendiriyorsa.

```cpp
template<class RandomAccessIterator>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bir yığın için denetlemek için bir aralık başlangıcını gösteren bir rastgele erişim yineleyicisi.

*Son*<br/>
Bir aralığın sonunu gösteren bir rastgele erişim yineleyicisi.

*Comp*<br/>
Sipariş öğelerine test etmek için bir koşul. İkili koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** Belirtilen aralıktaki öğeler bir yığın biçimlendiriyorsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevinin döndürdüğü [is_heap_until](../standard-library/algorithm-functions.md#is_heap_until)`(first , last) == last`.

İkinci şablon işlevi döndürür

`is_heap_until(first, last, comp) == last`.

## <a name="is_heap_until"></a>  is_heap_until

Aralıktaki ilk öğeyi adresindeki konumlandırılmış bir yineleyici döndürür [ `begin`, `end`) koşulu,'sıralama yığın karşılamıyor veya *son* aralığın bir yığın biçimlendiriyorsa.

```cpp
template<class RandomAccessIterator>
RandomAccessIterator is_heap_until(
    RandomAccessIterator begin,
    RandomAccessIterator end);

template<class RandomAccessIterator, class BinaryPredicate>
RandomAccessIterator is_heap_until(
    RandomAccessIterator begin,
    RandomAccessIterator end,
    BinaryPredicate compare);
```

### <a name="parameters"></a>Parametreler

*başlayın*<br/>
Bir yığın için denetlenecek aralığının ilk öğeyi belirten bir rastgele erişim yineleyicisi.

*Son*<br/>
Bir yığın için denetlenecek aralığın sonuna belirten bir rastgele erişim yineleyicisi.

*Karşılaştırma*<br/>
Koşul, sıralama katı zayıf belirten bir ikili koşul, bir yığın tanımlar. Varsayılan koşul *karşılaştırma* belirtilmemiş olan `std::less<>`.

### <a name="return-value"></a>Dönüş Değeri

Döndürür *son* Belirtilen aralıktaki bir yığın oluşturur ya da bir veya daha az öğe içeriyor. Aksi takdirde, yığın koşulu karşılamayan ilk öğe için bir yineleyici bulunan döndürür.

### <a name="remarks"></a>Açıklamalar

Son yineleyici ilk şablon işlevinin döndürdüğü `next` içinde `[ begin , end ]` burada `[ begin , next)` işlev nesnesi tarafından sıralı bir yığın `std::less<>`. Varsa uzaklık `end - begin < 2`, işlev döndürür *son*.

Koşul kullanması hariç, ikinci şablon işlevi, ilk olarak davranır `compare` yerine `std::less<>` koşul sıralama yığın olarak.

## <a name="is_partitioned"></a>  is_partitioned

Döndürür **true** verili aralıktaki tüm öğeleri, test, **true** test herhangi bir öğeden önce gelen bir koşul için **false**.

```cpp
template<class InputIterator, class BinaryPredicate>
bool is_partitioned(
    InputIterator first,
    InputIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aralığı bir koşulu denetleyen başladığı gösteren bir giriş yineleyici.

*Son*<br/>
Bir aralığın sonunu gösteren bir giriş yineleyici.

*Comp*<br/>
Sınanacak koşulu. Bu öğe, aranan tarafından karşılanması koşul tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Doğru döndürür test tüm öğeleri verili aralıktaki **true** test herhangi bir öğeden önce gelen bir koşul için **false**, aksi takdirde döndüren **false**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü **true** yalnızca tüm öğeler `[` `first ,` `last )` göre bölümlenir *comp*; diğer bir deyişle, tüm öğeleri `X` içinde`[` `first ,` `last )` hangi `comp (X)` önce tüm öğeleri doğru ortaya olan `Y` kendisi için `comp (Y)` olduğu **false**.

## <a name="is_permutation"></a>  is_permutation

Öğeler aynı sırada olsun olmasın hem de aralık aynı öğeleri içeriyorsa true döndürür. İkinci aralığı için tek bir yineleyici yalnızca aşırı farklar algılamaz ikinci aralığın ilk aralığından daha uzun ve ikinci aralığı kısaysa tanımsız davranışlara neden çünkü çift aralıklı C ++ 14 kodda aşırı yüklemeleri kullanın ilk aralığından daha.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    Predicate Pred);

// C++14
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
bool is_permutation(
    ForwardIterator1 First1,
    ForwardIterator1 Last1,
    ForwardIterator2 First2,
    ForwardIterator2 Last2,
    Predicate Pred);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Aralığın ilk öğeye başvuran ileri doğru yineleyici.

*last1*<br/>
Aralığın son öğeden bir öncekine başvuran ileri doğru yineleyici.

*first2*<br/>
Karşılaştırma için kullanılan bir ikinci aralığının ilk öğeye başvuran ileri doğru yineleyici.

*Soyadı2*<br/>
Karşılaştırma için kullanılan bir ikinci aralığının son öğeden bir öncekine başvuran ileri doğru yineleyici.

*Pred*<br/>
Denklik için test eder ve döndüren bir koşul bir **bool**.

### <a name="return-value"></a>Dönüş Değeri

**doğru** zaman aralıkları karşılaştırıcı koşula göre aynı; Aksi takdirde olması için yeniden **false**.

### <a name="remarks"></a>Açıklamalar

`is_permutation` ikinci dereceden karmaşıklığı en kötü durumda sahiptir.

İlk şablon işlevi olduğunu kadar öğeleri de aralık başında varsayar *First2* olduğundan tarafından belirtilen aralıktaki [ `First1`, `Last1`). İkinci aralık içinde daha fazla öğe varsa, bunlar yoksayılır; varsa daha az, tanımsız davranış ortaya çıkar. Üçüncü şablon işlevi (C ++ 14 ve üzeri) Bu varsayım yapmaz.  İkisi de **true** tarafından belirlenen aralığındaki her öğeyi X için yalnızca Eğer [ `First1`, `Last1`) hangi X aralığında aynı sayıda öğe Y vardır olduğundan de aralık başında Y == *First2* veya [ `First2, Last2).` burada `operator==` işlenenleri arasındaki ikili karşılaştırma gerçekleştirmeniz gerekir.

Bunlar değiştirir dışında ikinci ve dördüncü bir şablon işlevleri aynı şekilde davranır `operator==(X, Y)` ile `Pred(X, Y)`. Koşul doğru şekilde davranmaz için simetrik, yansıma ve geçişli olması gerekir.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `is_permutation`:

```cpp
#include <vector>
#include <iostream>
#include <algorithm>
#include <string>

using namespace std;

int main()
{
    vector<int> vec_1{ 2, 3, 0, 1, 4, 5 };
    vector<int> vec_2{ 5, 4, 0, 3, 1, 2 };

    vector<int> vec_3{ 4, 9, 13, 3, 6, 5 };
    vector<int> vec_4{ 7, 4, 11, 9, 2, 1 };

    cout << "(1) Compare using built-in == operator: ";
    cout << boolalpha << is_permutation(vec_1.begin(), vec_1.end(),
        vec_2.begin(), vec_2.end()) << endl; // true

    cout << "(2) Compare after modifying vec_2: ";
    vec_2[0] = 6;
    cout << is_permutation(vec_1.begin(), vec_1.end(),
        vec_2.begin(), vec_2.end()) << endl; // false

    // Define equivalence as "both are odd or both are even"
    cout << "(3) vec_3 is a permutation of vec_4: ";
    cout << is_permutation(vec_3.begin(), vec_3.end(),
        vec_4.begin(), vec_4.end(),
        [](int lhs, int rhs) { return lhs % 2 == rhs % 2; }) << endl; // true

    // Initialize a vector using the 's' string literal to specify a std::string
    vector<string> animals_1{ "dog"s, "cat"s, "bird"s, "monkey"s };
    vector<string> animals_2{ "donkey"s, "bird"s, "meerkat"s, "cat"s };

    // Define equivalence as "first letters are equal":
    bool is_perm = is_permutation(animals_1.begin(), animals_1.end(), animals_2.begin(), animals_2.end(),
        [](const string& lhs, const string& rhs)
    {
        return lhs[0] == rhs[0]; //std::string guaranteed to have at least a null terminator
    });

    cout << "animals_2 is a permutation of animals_1: " << is_perm << endl; // true

    cout << "Press a letter" << endl;
    char c;
    cin >> c;

    return 0;
}

```

## <a name="is_sorted"></a>  is_sorted

Döndürür **true** sıralanmış olarak belirtilen aralıktaki öğeler varsa.

```cpp
template<class ForwardIterator>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class BinaryPredicate>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Denetlenecek aralık başladığı yeri gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Bir aralığın sonunu gösteren bir ileriye doğru yineleyici.

*Comp*<br/>
İki öğe arasındaki bir sırayı belirlemek için test edilecek koşul. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**. Bu aynı görevi gerçekleştirir `operator<`.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevinin döndürdüğü [is_sorted_until](#is_sorted_until)`( first, last ) == last`. `operator<` İşlevi sipariş karşılaştırma gerçekleştirir.

İkinci şablon işlevinin döndürdüğü `is_sorted_until( first, last , comp ) == last`. *Comp* koşul işlevi, sipariş karşılaştırma gerçekleştirir.

## <a name="is_sorted_until"></a>  is_sorted_until

Döndürür bir `ForwardIterator` kümesi son belirtilen bir aralıktan sıralanmış sırayla öğesi.

Dosyanın ikinci sürümü, sağlamanızı bir `BinaryPredicate` döndüren işlev **true** iki belirli öğeleri sıralanmış olarak olduğunda ve **false** Aksi takdirde.

```cpp
template<class ForwardIterator>
ForwardIterator is_sorted_until(
    ForwardIterator first,
    ForwardIterator last);
template<class ForwardIterator, class BinaryPredicate>
ForwardIterator is_sorted_until(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Denetlenecek aralık başladığı gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Bir aralığın sonunu gösteren bir ileriye doğru yineleyici.

*Comp*<br/>
İki öğe arasındaki bir sırayı belirlemek için test edilecek koşul. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `ForwardIterator` son öğesi sıralanmış olarak ayarlayın. Sıralanmış dizisi başlatılır *ilk*.

### <a name="remarks"></a>Açıklamalar

Son yineleyici ilk şablon işlevinin döndürdüğü `next` içinde `[` `first ,` `last ]` böylece `[` `first , next)` sıralı bir dizisi göre sıralanmış `operator<`. Varsa `distance()` `< 2` işlevi döndürür *son*.

Değiştirir dışında ikinci şablon işlevi aynı şekilde davranır `operator<(X, Y)` ile `comp (X, Y)`.

## <a name="iter_swap"></a>  iter_swap

Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
void iter_swap( ForwardIterator1 left, ForwardIterator2 right );

```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Değiştirilecek değeri olan ileriye doğru Yineleyicilerin biri.

*sağ*<br/>
Değiştirilecek değeri olan ileriye doğru Yineleyicilerin saniye.

### <a name="remarks"></a>Açıklamalar

`swap` preference için kullanılması gereken miyim **ter_swap**, geriye dönük uyumluluk için C++ standardında dahil. Varsa `Fit1` ve `Fit2` ileriye doğru Yineleyicilerin ardından olan `iter_swap` ( `Fit1`, `Fit2` ), eşdeğerdir `swap` ( \* `Fit1`, \* `Fit2` ).

Giriş ileriye doğru Yineleyicilerin değer türlerinin aynı değere sahip olmalıdır.

### <a name="example"></a>Örnek

```cpp
// alg_iter_swap.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) { m_nVal =
   rhs.m_nVal; return *this; }
   bool operator<( const CInt& rhs ) const
      { return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt(" << rhs.m_nVal << ")";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main()
{
   CInt c1 = 5, c2 = 1, c3 = 10;
   deque<CInt> deq1;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Exchanging first and last elements with iter_swap
   iter_swap ( deq1.begin( ), --deq1.end( ) );

   cout << "The deque of CInts with first & last elements swapped is:\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Swapping back first and last elements with swap
   swap ( *deq1.begin( ), *(deq1.end( ) -1 ) );

   cout << "The deque of CInts with first & last elements swapped back is:\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   // Swapping a vector element with a deque element
   vector <int> v1;
   vector <int>::iterator Iter1;
   deque <int> deq2;
   deque <int>::iterator d2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 4 ; ii <= 5 ; ii++ )
   {
      deq2.push_back( ii );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Deque deq2 is ( " ;
   for ( d2_Iter = deq2.begin( ) ; d2_Iter != deq2.end( ) ; d2_Iter++ )
      cout << *d2_Iter << " ";
   cout << ")." << endl;

   iter_swap ( v1.begin( ), deq2.begin( ) );

   cout << "After exchanging first elements,\n vector v1 is: v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << " & deque deq2 is: deq2 = ( ";
   for ( d2_Iter = deq2.begin( ) ; d2_Iter != deq2.end( ) ; d2_Iter++ )
      cout << *d2_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original deque of CInts is deq1 = ( CInt(5), CInt(1), CInt(10) ).
The deque of CInts with first & last elements swapped is:
deq1 = ( CInt(10), CInt(1), CInt(5) ).
The deque of CInts with first & last elements swapped back is:
deq1 = ( CInt(5), CInt(1), CInt(10) ).
Vector v1 is ( 0 1 2 3 ).
Deque deq2 is ( 4 5 ).
After exchanging first elements,
vector v1 is: v1 = ( 4 1 2 3 ).
& deque deq2 is: deq2 = ( 0 5 ).
```

## <a name="lexicographical_compare"></a>  lexicographical_compare

Daha küçük olanı belirlemek için iki diziyi öğe öğe karşılaştırır.

```cpp
template<class InputIterator1, class InputIterator2>
bool lexicographical_compare(
    InputIterator1  first1,
    InputIterator1 Last1,
    InputIterator2  first2,
    InputIterator2 Last2  );

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool lexicographical_compare(
    InputIterator1  first1,
    InputIterator1 Last1,
    InputIterator2  first2,
    InputIterator2 Last2,
    BinaryPredicate  comp  );

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Karşılaştırılacak ilk aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*last1*<br/>
Karşılaştırılacak ilk aralığın son öğesinde geçmiş konumu ele alan bir giriş yineleyici.

*first2*<br/>
Karşılaştırılacak ikinci aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Soyadı2*<br/>
Karşılaştırılacak ikinci aralığın son öğesinde geçmiş konumu ele alan bir giriş yineleyici.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilk aralığın ikinci aralığından; lexicographically daha az ise, aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Lexicographical karşılaştırma dizileri arasında bunları kadar öğeye göre karşılaştırılır:

- İki karşılık gelen öğelerle eşit bulur ve bunların karşılaştırma sonucu dizileri arasındaki Karşılaştırmanın sonucu olarak alınır.

- Hiçbir inequalities bulundu, ancak bir sıralı uzun dizisi'den küçük olan diğer ve daha kısa bir dizisi olarak kabul edilir çok daha fazla öğe vardır.

- Hiçbir inequalities bulundu ve öğeleri aynı sayıda dizileri sahiptir ve dizileri eşit şekilde ve Karşılaştırmanın sonucu false'tur.

### <a name="example"></a>Örnek

```cpp
// alg_lex_comp.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice ( int elem1, int elem2 )
{
   return 2 * elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   int ii;
   for ( ii = 0 ; ii <= 6 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Self lexicographical_comparison of v1 under identity
   bool result1;
   result1 = lexicographical_compare (v1.begin( ), v1.end( ),
                  v1.begin( ), v1.end( ) );
   if ( result1 )
      cout << "Vector v1 is lexicographically_less than v1." << endl;
   else
      cout << "Vector v1 is not lexicographically_less than v1." << endl;

   // lexicographical_comparison of v1 and L2 under identity
   bool result2;
   result2 = lexicographical_compare (v1.begin( ), v1.end( ),
                  L1.begin( ), L1.end( ) );
   if ( result2 )
      cout << "Vector v1 is lexicographically_less than L1." << endl;
   else
      cout << "Vector v1 is lexicographically_less than L1." << endl;

   bool result3;
   result3 = lexicographical_compare (v1.begin( ), v1.end( ),
                  v2.begin( ), v2.end( ), twice );
   if ( result3 )
      cout << "Vector v1 is lexicographically_less than v2 "
           << "under twice." << endl;
   else
      cout << "Vector v1 is not lexicographically_less than v2 "
           << "under twice." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 )
List L1 = ( 0 5 10 15 20 25 30 )
Vector v2 = ( 0 10 20 30 40 50 )
Vector v1 is not lexicographically_less than v1.
Vector v1 is lexicographically_less than L1.
Vector v1 is not lexicographically_less than v2 under twice.
```

## <a name="lower_bound"></a>  lower_bound

Sıralı bir aralıkta belirtilen değere eşit ya da daha büyük bir değere sahip ilk öğenin konumunu bulur, burada sıralama kriteri bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator, class Type>
ForwardIterator lower_bound(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value );

template<class ForwardIterator, class Type, class BinaryPredicate>
ForwardIterator lower_bound(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*value*<br/>
İlk konumu veya olası ilk konumu Sıralanan aralıkta Aranan değer.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Konumda denkliğin ikili tahminle burada belirtilen ilk öğenin belirtilen değere eşit veya daha büyük bir değere sahip sıralı bir aralıktaki ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalı; Tüm yineleyiciler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Bir sıralanmış aralıkta kullanmanın bir önkoşuludur `lower_bound` ve sıralama ile ikili koşul tarafından belirtildiği gibi aynı.

Aralığın algoritması tarafından değiştirilmez `lower_bound`.

İleriye doğru Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu bir sıralamaya neden olur öğeler arasında neden olur

Algoritmanın karmaşıklığı, rasgele erişim yineleyicileri için logaritmik ve doğrusal Aksi takdirde doğrusaldır adım sayısı ile (`last - first`).

### <a name="example"></a>Örnek

```cpp
// alg_lower_bound.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
}

int main()
{
    using namespace std;

    vector<int> v1;
    // Constructing vector v1 with default less-than ordering
    for ( auto i = -1 ; i <= 4 ; ++i )
    {
        v1.push_back(  i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back(  ii  );
    }

    cout << "Starting vector v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    sort(v1.begin(), v1.end());
    cout << "Original vector v1 with range sorted by the\n "
        << "binary predicate less than is v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vector v2 with range sorted by greater
    vector<int> v2(v1);

    sort(v2.begin(), v2.end(), greater<int>());

    cout << "Original vector v2 with range sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
    for (const auto &Iter : v2)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vectors v3 with range sorted by mod_lesser
    vector<int> v3(v1);
    sort(v3.begin(), v3.end(), mod_lesser);

    cout << "Original vector v3 with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3 = ( " ;
    for (const auto &Iter : v3)
        cout << Iter << " ";
    cout << ")." << endl;

    // Demonstrate lower_bound

    vector<int>::iterator Result;

    // lower_bound of 3 in v1 with default binary predicate less<int>()
    Result = lower_bound(v1.begin(), v1.end(), 3);
    cout << "The lower_bound in v1 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // lower_bound of 3 in v2 with the binary predicate greater<int>( )
    Result = lower_bound(v2.begin(), v2.end(), 3, greater<int>());
    cout << "The lower_bound in v2 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // lower_bound of 3 in v3 with the binary predicate  mod_lesser
    Result = lower_bound(v3.begin(), v3.end(), 3,  mod_lesser);
    cout << "The lower_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}

```

## <a name="make_heap"></a>  make_heap

Belirtilen bir aralıktaki öğeleri ilk öğenin en büyük olduğu ve onun için bir ikili koşula sahip bir sıralama ölçütünün belirtilebildiği bir yığına dönüştürür.

```cpp
template<class RandomAccessIterator>
void make_heap(
    RandomAccessIterator first,
    RandomAccessIterator last );

template<class RandomAccessIterator, class BinaryPredicate>
void make_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Yığına dönüştürülmesi aralıktaki ilk öğenin konumunu bulan bir rastgele erişim yineleyicisi.

*Son*<br/>
Yığına dönüştürülmesi aralığın son öğesinde geçmiş konumu ele alan bir rastgele erişim yineleyicisi.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Yığınlar iki özelliğe sahiptir:

- İlk öğe her zaman daha büyüktür.

- Öğeleri eklenebilir veya Logaritmik süre kaldırıldı.

Yığınlar öncelikli kuyruklardaki uygulamak için ideal bir yöntem olduğunu ve C++ Standart Kitaplığı kapsayıcı bağdaştırıcısı uygulamasında kullanılan [priority_queue sınıfı](../standard-library/priority-queue-class.md).

Karmaşıklığı 3 gerektiren doğrusal \* (* Soyadı - *) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_make_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with default less than ordering
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with greater than ordering
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater-than heaped version of v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="max"></a>  en fazla

İki nesneyi karşılaştırır ve ikisinden büyük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

```cpp
template<class Type>
constexpr Type& max(
    const Type& left,
    const Type& right);
template<class Type, class Pr>
constexpr Type& max(
    const Type& left,
    const Type& right,
    BinaryPredicate comp);
template<class Type>
constexpr Type& max (
    initializer_list<Type> );
template<class Type, class Pr>
constexpr Type& max(
    initializer_list<Type> ,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlk Karşılaştırılan iki nesne.

*sağ*<br/>
İkinci Karşılaştırılan iki nesne.

*Comp*<br/>
İki nesneleri karşılaştırmak için kullanılan bir ikili koşul.

*_IList*<br/>
Karşılaştırılacak nesneleri içeren bir başlatıcı listesi.

### <a name="return-value"></a>Dönüş Değeri

Hiçbiri büyük değilse iki büyük, nesneleri; Bu durumda, ilk iki nesne döndürür. Bir initializer_list söz konusu olduğunda, en büyük nesneleri listesinde döndürür.

### <a name="remarks"></a>Açıklamalar

`max` Algoritmasıdır parametre olarak geçirilen nesneleri etmeyle olağan dışı. Çoğu standart C++ Kitaplığı algoritmaları konumu parametre olarak geçirilen yineleyiciler tarafından belirtilen öğelerin bir aralığını üzerinde çalışır. Öğe aralığını üzerinde çalışan bir işlev ihtiyacınız varsa, [max_element](../standard-library/algorithm-functions.md#max_element) yerine. Visual Studio 2017 tanır **constexpr** bir initializer_list aşırı üzerinde.

### <a name="example"></a>Örnek

```cpp
// alg_max.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether absolute value of elem1 is greater than
// absolute value of elem2
bool abs_greater ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = -elem1;
   if ( elem2 < 0 )
      elem2 = -elem2;
   return elem1 < elem2;
};

int main()
{
   int a = 6, b = -7;
   // Return the integer with the larger absolute value
   const int& result1 = max(a, b, abs_greater);
   // Return the larger integer
   const int& result2 = max(a, b);

   cout << "Using integers 6 and -7..." << endl;
   cout << "The integer with the greater absolute value is: "
        << result1 << "." << endl;
   cout << "The integer with the greater value is: "
        << result2 << "." << endl;
   cout << endl;

// Comparing the members of an initializer_list
const int& result3 = max({ a, b });
const int& result4 = max({ a, b }, abs_greater);

cout << "Comparing the members of an initializer_list..." << endl;
cout << "The member with the greater value is: " << result3 << endl;
cout << "The integer with the greater absolute value is: " << result4 << endl;

   // Comparing set containers with elements of type CInt
   // using the max algorithm
   CInt c1 = 1, c2 = 2, c3 = 3;
   set<CInt> s1, s2, s3;
   set<CInt>::iterator s1_Iter, s2_Iter, s3_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s2.insert ( c2 );
   s2.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   cout << "s2 = (";
   for ( s2_Iter = s2.begin( ); s2_Iter != --s2.end( ); s2_Iter++ )
      cout << " " << *s2_Iter << ",";
   s2_Iter = --s2.end( );
   cout << " " << *s2_Iter << " )." << endl;

   s3 = max ( s1, s2 );
   cout << "s3 = max ( s1, s2 ) = (";
   for ( s3_Iter = s3.begin( ); s3_Iter != --s3.end( ); s3_Iter++ )
      cout << " " << *s3_Iter << ",";
   s3_Iter = --s3.end( );
   cout << " " << *s3_Iter << " )." << endl << endl;

   // Comparing vectors with integer elements using the max algorithm
   vector <int> v1, v2, v3, v4, v5;
   vector <int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

   int i;
   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 0 ; ii <= 2 ; ii++ )
   {
      v2.push_back( ii );
   }

   int iii;
   for ( iii = 0 ; iii <= 2 ; iii++ )
   {
      v3.push_back( 2 * iii );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   cout << "Vector v3 is ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;

   v4 = max ( v1, v2 );
   v5 = max ( v1, v3 );

   cout << "Vector v4 = max (v1,v2) is ( " ;
   for ( Iter4 = v4.begin( ) ; Iter4 != v4.end( ) ; Iter4++ )
      cout << *Iter4 << " ";
   cout << ")." << endl;

   cout << "Vector v5 = max (v1,v3) is ( " ;
   for ( Iter5 = v5.begin( ) ; Iter5 != v5.end( ) ; Iter5++ )
      cout << *Iter5 << " ";
   cout << ")." << endl;
}
```

```Output
Using integers 6 and -7...
The integer with the greater absolute value is: -7
The integer with the greater value is: 6.
Comparing the members of an initializer_list...The member with the greater value is: 6The integer wiht the greater absolute value is: -7
s1 = ( CInt( 1 ), CInt( 2 ) ).
s2 = ( CInt( 2 ), CInt( 3 ) ).
s3 = max ( s1, s2 ) = ( CInt( 2 ), CInt( 3 ) ).

Vector v1 is ( 0 1 2 ).
Vector v2 is ( 0 1 2 ).
Vector v3 is ( 0 2 4 ).
Vector v4 = max (v1,v2) is ( 0 1 2 ).
Vector v5 = max (v1,v3) is ( 0 2 4 ).
```

## <a name="max_element"></a>  max_element

Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator>
constexpr ForwardIterator max_element(ForwardIterator first, ForwardIterator last );

template<class ForwardIterator, class BinaryPredicate>
constexpr ForwardIterator max_element(ForwardIterator first, ForwardIterator last, BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
En büyük öğe için aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
En büyük öğe için aranacak aralıktaki son öğeden sonraki birinci konum ele alan ileriye doğru yineleyici.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Aralıktaki en büyük öğenin geçtiği ilk yeri konumunu bulan ileriye doğru yineleyici aranır.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklığı doğrusal: (`last` - `first`) - 1 karşılaştırmaları için boş bir aralık gereklidir.

### <a name="example"></a>Örnek

```cpp
// alg_max_element.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt& operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<(ostream& osIn, const CInt& rhs)
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is greater than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main()
{
   // Searching a set container with elements of type CInt
   // for the maximum element
   CInt c1 = 1, c2 = 2, c3 = -3;
   set<CInt> s1;
   set<CInt>::iterator s1_Iter, s1_R1_Iter, s1_R2_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s1.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   s1_R1_Iter = max_element ( s1.begin( ), s1.end( ) );

   cout << "The largest element in s1 is: " << *s1_R1_Iter << endl;
   cout << endl;

   // Searching a vector with elements of type int for the maximum
   // element under default less than & mod_lesser binary predicates
   vector <int> v1;
   vector <int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      v1.push_back( - 2 * ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << " ";
   cout << ")." << endl;

   v1_R1_Iter = max_element ( v1.begin( ), v1.end( ) );
   v1_R2_Iter = max_element ( v1.begin( ), v1.end( ), mod_lesser);

   cout << "The largest element in v1 is: " << *v1_R1_Iter << endl;
   cout << "The largest element in v1 under the mod_lesser"
        << "\n binary predicate is: " << *v1_R2_Iter << endl;
}
```

## <a name="merge"></a>  Birleştirme

İki sıralanmış kaynak aralıktaki tüm öğeleri, burada sıralama ölçütü bir ikili koşula göre belirtilebilir bir tek, sıralanmış aralıkta birleştirir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator merge(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator merge(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Birleştirilir ve tek bir aralığa sıralanmış için iki sıralanmış kaynak aralıktaki ilk ilk öğenin konumunu ele alan bir giriş yineleyici.

*last1*<br/>
Bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa birleştirilir ve tek bir aralığa sıralanmış için ele alan giriş yineleyici.

*first2*<br/>
Birleştirilir ve tek bir aralığa sıralanmış için iki ardışık sıralanmış kaynak aralığa saniye içinde ilk öğenin konumunu ele alan giriş yineleyici.

*Soyadı2*<br/>
Birleştirilir ve tek bir aralığa sıralanmış için iki ardışık sıralanmış kaynak aralığa saniye olarak geçen son öğe konumu ele alan bir giriş yineleyici.

*Sonuç*<br/>
Tek bir sıralanmış aralıkta birleştirilmek üzere iki kaynak aralıktaki olduğu hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Sıralanmış hedef aralığın son öğesinde geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Hedef aralığı ya da kaynak aralıkları çakışmamalı ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralığa her uygulama için bir önkoşul olarak düzenlenmelidir `merge` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak.

Her aralık içindeki öğelerin göreli sırasını hedef aralığı korunduğu kalıcı bir işlemdir. Kaynak aralıkları algoritması tarafından değiştirilmez `merge`.

Giriş Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Hem kaynak aralıklardaki eşdeğer öğelerin olduğunda, ilk aralıktaki öğeleri hedef aralığında ikinci aralığın öğelerden koyun.

Algoritmanın karmaşıklığı, en fazla ile doğrusal (* last1 - first1 *)-(* Soyadı2 - first2*) - 1 karşılaştırmalar.

[Listesinde sınıfı](../standard-library/list-class.md) bir üye işlev "iki listenin öğelerini birleştirmek için Birleştir" sağlar.

### <a name="example"></a>Örnek

```cpp
// alg_merge.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>   // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 ) {
   if (elem1 < 0)
      elem1 = - elem1;
   if (elem2 < 0)
      elem2 = - elem2;
   return elem1 < elem2;
}

int main() {
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1;

   // Constructing vector v1a and v1b with default less than ordering
   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1a.push_back(  i );

   int ii;
   for ( ii =-5 ; ii <= 0 ; ii++ )
      v1b.push_back(  ii  );

   cout << "Original vector v1a with range sorted by the\n "
        << "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        << "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vector v2 with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a,  Iter2b, Iter2;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vector v3 with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3;
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        << "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        << "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To merge inplace in ascending order with default binary
   // predicate less <int>( )
   merge ( v1a.begin( ), v1a.end( ), v1b.begin( ), v1b.end( ), v1.begin( ) );
   cout << "Merged inplace with default order,\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To merge inplace in descending order, specify binary
   // predicate greater<int>( )
   merge ( v2a.begin( ), v2a.end( ), v2b.begin( ), v2b.end( ),
       v2.begin( ),  greater <int>( ) );
   cout << "Merged inplace with binary predicate greater specified,\n "
        << "vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // Applying A user-defined (UD) binary predicate mod_lesser
   merge ( v3a.begin( ), v3a.end( ), v3b.begin( ), v3b.end( ),
       v3.begin( ),  mod_lesser );
   cout << "Merged inplace with binary predicate mod_lesser specified,\n "
        << "vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="min"></a>  Min

İki nesneyi karşılaştırır ve ikisinden küçük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

```cpp
template<class Type>
constexpr const Type& min(
    const Type& left,
    const Type& right);
template<class Type, class Pr>
constexpr const Type& min(
    const Type& left,
    const Type& right,
    BinaryPredicate comp);
template<class Type>
constexpr Type min(
    initializer_list<Type> );
template<class Type, class Pr>
constexpr Type min(
    initializer_list<Type>,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlk Karşılaştırılan iki nesne.

*sağ*<br/>
İkinci Karşılaştırılan iki nesne.

*Comp*<br/>
İki nesneleri karşılaştırmak için kullanılan bir ikili koşul.

*_IList*<br/>
Karşılaştırılacak üyeleri içeren initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Hiçbiri daha az olmadığı sürece ikisinden küçük olanı, nesneleri; Bu durumda, ilk iki nesne döndürür. Bir initializer_list söz konusu olduğunda, en az nesneleri listesinde döndürür.

### <a name="remarks"></a>Açıklamalar

`min` Algoritmasıdır parametre olarak geçirilen nesneleri etmeyle olağan dışı. Çoğu standart C++ Kitaplığı algoritmaları konumu parametre olarak geçirilen yineleyiciler tarafından belirtilen öğelerin bir aralığını üzerinde çalışır. Öğe aralığını kullanan bir işlev ihtiyacınız varsa, [min_element](../standard-library/algorithm-functions.md#min_element). [constexpr](../cpp/constexpr-cpp.md) üzerinde etkin `initializer_list` Visual Studio 2017'de aşırı yüklemeleri.

### <a name="example"></a>Örnek

```cpp
// alg_min.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
    CInt( int n = 0 ) : m_nVal( n ){}
    CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
    CInt& operator=( const CInt& rhs ) {m_nVal =
    rhs.m_nVal; return *this;}
    bool operator<( const CInt& rhs ) const
        {return ( m_nVal < rhs.m_nVal );}
    friend ostream& operator<<(ostream& osIn, const CInt& rhs);

private:
    int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
    osIn << "CInt( " << rhs.m_nVal << " )";
       return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
};

int main()
{
    // Comparing integers directly using the min algorithm with
    // binary predicate mod_lesser & with default less than
    int a = 6, b = -7, c = 7 ;
    const int& result1 = min ( a, b, mod_lesser );
    const int& result2 = min ( b, c );

    cout << "The mod_lesser of the integers 6 & -7 is: "
        << result1 << "." << endl;
    cout << "The lesser of the integers -7 & 7 is: "
        << result2 << "." << endl;
    cout << endl;

// Comparing the members of an initializer_list
    const int& result3 = min({ a, c });
    const int& result4 = min({ a, b }, mod_lesser);

    cout << "The lesser of the integers 6 & 7 is: "
        << result3 << "." << endl;
    cout << "The mod_lesser of the integers 6 & -7 is: "
        << result4 << "." << endl;
    cout << endl;

    // Comparing set containers with elements of type CInt
       // using the min algorithm
    CInt c1 = 1, c2 = 2, c3 = 3;
    set<CInt> s1, s2, s3;
    set<CInt>::iterator s1_Iter, s2_Iter, s3_Iter;

    s1.insert ( c1 );
    s1.insert ( c2 );
    s2.insert ( c2 );
    s2.insert ( c3 );

    cout << "s1 = (";
    for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
        cout << " " << *s1_Iter << ",";
    s1_Iter = --s1.end( );
        cout << " " << *s1_Iter << " )." << endl;

    cout << "s2 = (";
    for ( s2_Iter = s2.begin( ); s2_Iter != --s2.end( ); s2_Iter++ )
        cout << " " << *s2_Iter << ",";
    s2_Iter = --s2.end( );
    cout << " " << *s2_Iter << " )." << endl;

    s3 = min ( s1, s2 );
    cout << "s3 = min ( s1, s2 ) = (";
    for ( s3_Iter = s3.begin( ); s3_Iter != --s3.end( ); s3_Iter++ )
        cout << " " << *s3_Iter << ",";
    s3_Iter = --s3.end( );
    cout << " " << *s3_Iter << " )." << endl << endl;

    // Comparing vectors with integer elements using min algorithm
    vector <int> v1, v2, v3, v4, v5;
    vector <int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

    int i;
    for ( i = 0 ; i <= 2 ; i++ )
    {
        v1.push_back( i );
    }

    int ii;
    for ( ii = 0 ; ii <= 2 ; ii++ )
    {
        v2.push_back( ii );
    }

    int iii;
    for ( iii = 0 ; iii <= 2 ; iii++ )
    {
        v3.push_back( 2 * iii );
    }

    cout << "Vector v1 is ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    cout << "Vector v2 is ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    cout << "Vector v3 is ( " ;
    for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;

    v4 = min ( v1, v2 );
    v5 = min ( v1, v3 );

    cout << "Vector v4 = min ( v1,v2 ) is ( " ;
    for ( Iter4 = v4.begin( ) ; Iter4 != v4.end( ) ; Iter4++ )
        cout << *Iter4 << " ";
    cout << ")." << endl;

    cout << "Vector v5 = min ( v1,v3 ) is ( " ;
    for ( Iter5 = v5.begin( ) ; Iter5 != v5.end( ) ; Iter5++ )
        cout << *Iter5 << " ";
    cout << ")." << endl;
}
```

```Output
The mod_lesser of the integers 6 & -7 is: 6.
The lesser of the integers -7 & 7 is: -7.
The lesser of the integers 6 & 7 is: 6.The mod_lesser of the integers 6 & -7 is: 6.
s1 = ( CInt( 1 ), CInt( 2 ) ).
s2 = ( CInt( 2 ), CInt( 3 ) ).
s3 = min ( s1, s2 ) = ( CInt( 1 ), CInt( 2 ) ).

Vector v1 is ( 0 1 2 ).
Vector v2 is ( 0 1 2 ).
Vector v3 is ( 0 2 4 ).
Vector v4 = min ( v1,v2 ) is ( 0 1 2 ).
Vector v5 = min ( v1,v3 ) is ( 0 1 2 ).
```

## <a name="min_element"></a>  min_element

Belirtilen bir aralıktaki en küçük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator>
constexpr ForwardIterator min_element(ForwardIterator first, ForwardIterator last );

template<class ForwardIterator, class BinaryPredicate>
constexpr ForwardIterator min_element(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
En küçük öğe için aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
En küçük öğe için aranacak aralıktaki son öğeden sonraki birinci konum ele alan ileriye doğru yineleyici.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Aralıktaki en küçük öğenin geçtiği ilk yeri konumunu bulan ileriye doğru yineleyici aranır.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklığı doğrusal: (`last` - `first`) - 1 karşılaştırmaları için boş bir aralık gereklidir.

### <a name="example"></a>Örnek

```cpp
// alg_min_element.cpp
// compile with: /EHsc
#include <vector>
#include <set>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt& operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main()
{
   // Searching a set container with elements of type CInt
   // for the minimum element
   CInt c1 = 1, c2 = 2, c3 = -3;
   set<CInt> s1;
   set<CInt>::iterator s1_Iter, s1_R1_Iter, s1_R2_Iter;

   s1.insert ( c1 );
   s1.insert ( c2 );
   s1.insert ( c3 );

   cout << "s1 = (";
   for ( s1_Iter = s1.begin( ); s1_Iter != --s1.end( ); s1_Iter++ )
      cout << " " << *s1_Iter << ",";
   s1_Iter = --s1.end( );
   cout << " " << *s1_Iter << " )." << endl;

   s1_R1_Iter = min_element ( s1.begin( ), s1.end( ) );

   cout << "The smallest element in s1 is: " << *s1_R1_Iter << endl;
   cout << endl;

   // Searching a vector with elements of type int for the maximum
   // element under default less than & mod_lesser binary predicates
   vector <int> v1;
   vector <int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii = 1 ; ii <= 4 ; ii++ )
   {
      v1.push_back( - 2 * ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )
      cout << *v1_Iter << " ";
   cout << ")." << endl;

   v1_R1_Iter = min_element ( v1.begin( ), v1.end( ) );
   v1_R2_Iter = min_element ( v1.begin( ), v1.end( ), mod_lesser);

   cout << "The smallest element in v1 is: " << *v1_R1_Iter << endl;
   cout << "The smallest element in v1 under the mod_lesser"
        << "\n binary predicate is: " << *v1_R2_Iter << endl;
}
```

```Output
s1 = ( CInt( -3 ), CInt( 1 ), CInt( 2 ) ).
The smallest element in s1 is: CInt( -3 )

Vector v1 is ( 0 1 2 3 -2 -4 -6 -8 ).
The smallest element in v1 is: -8
The smallest element in v1 under the mod_lesser
binary predicate is: 0
```

## <a name="minmax_element"></a>  minmax_element

Tarafından gerçekleştirilen işi yapar `min_element` ve `max_element` tek bir çağrıdaki.

```cpp
template<class ForwardIterator>
constexpr pair<ForwardIterator, ForwardIterator> minmax_element(
    ForwardIterator first,
    ForwardIterator Last);
template<class ForwardIterator, class BinaryPredicate>
constexpr pair<ForwardIterator, ForwardIterator> minmax_element(
    ForwardIterator  first,
    ForwardIterator Last,
    BinaryPredicate  comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bir aralık başlangıcını gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Bir aralığın sonunu gösteren bir ileriye doğru yineleyici.

*Comp*<br/>
Sipariş öğeleri için kullanılan isteğe bağlı bir test.

### <a name="return-value"></a>Dönüş Değeri

Döndürür

`pair<ForwardIterator, ForwardIterator>`

`(` [min_element](../standard-library/algorithm-functions.md#min_element)`(first, last), `[max_element](../standard-library/algorithm-functions.md#max_element)`(first, last))`.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevi döndürür

`pair<ForwardIterator,ForwardIterator>`

`(min_element(_First,Last), max_element(_First,Last))`.

Değiştirir dışında ikinci şablon işlevi aynı şekilde davranır `operator<(X, Y)` ile `comp (X, Y)`.

İşlev sırası boş ise, en fazla gerçekleştirir `3 * (last - first - 1) / 2` karşılaştırmalar.

## <a name="minmax"></a>  minmax

İki giriş parametresini karşılaştırır ve bunları sırasına, bir çift olarak döndürür daha küçük.

```cpp
template<class Type>
constexpr pair<const Type&, const Type&> minmax(
    const Type& left,
    const Type& right);
template<class Type, class BinaryPredicate>
constexpr pair<const Type&, const Type&> minmax(
    const Type& left,
    const Type& right,
    BinaryPredicate comp);
template<class Type>
constexpr pair<Type&, Type&> minmax(
    initializer_list<Type> );
template<class Type, class BinaryPredicate>
constexpr pair<Type&, Type&> minmax(
    initializer_list<Type>,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlk Karşılaştırılan iki nesne.

*sağ*<br/>
İkinci Karşılaştırılan iki nesne.

*Comp*<br/>
İki nesneleri karşılaştırmak için kullanılan bir ikili koşul.

*_IList*<br/>
Karşılaştırılacak üyeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevinin döndürdüğü `pair<const Type&, const Type&>( right , left )` varsa *doğru* olduğu küçüktür *sol*. Aksi halde `pair<const Type&, const Type&>( left , right )`.

İkinci üye işlevi burada ilk öğeyi küçük olanı ve ikinci koşul tarafından karşılaştırıldığında büyük bir çiftini döndürür *comp*.

Bunlar değiştirir hariç, kalan şablon işlevleri aynı şekilde davranır *sol* ve *doğru* parametrelerle *_IList*.

İşlev tam olarak bir karşılaştırma gerçekleştirir.

## <a name="mismatch"></a>  uyuşmazlığı

İki aralığı öğe öğe karşılaştırır ve farkın oluştuğu ilk yeri bulur.

İkinci aralığı için tek bir yineleyici yalnızca aşırı farklar algılamaz ikinci aralığın ilk aralığından daha uzun ve ikinci aralığı kısaysa tanımsız davranışlara neden çünkü çift aralıklı C ++ 14 kodda aşırı yüklemeleri kullanın ilk aralığından daha.

```cpp
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 First1,
    InputIterator1 Last1,
    InputIterator2 First2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 First1,
    InputIterator1 Last1,
    InputIterator2 First2,
    BinaryPredicate Comp );

//C++14
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 First1,
    InputIterator1 Last1,
    InputIterator2 First2,
    InputIterator2 Last2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 First1,
    InputIterator1 Last1,
    InputIterator2 First2,
    InputIterator2 Last2,
    BinaryPredicate Comp);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Test edilecek ilk aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*last1*<br/>
Test edilecek ilk aralığın son öğesinde geçmiş konumu ele alan bir giriş yineleyici.

*first2*<br/>
Test edilecek ikinci aralıktaki ilk öğenin konumunu ele alan bir giriş yineleyici.

*Soyadı2*<br/>
Test edilecek ikinci aralıktaki son öğeden bir öncekine konumu ele alan bir giriş yineleyici.

*Comp*<br/>
Her aralığında geçerli öğe karşılaştırır ve eşdeğer olup olmadığını belirleyen kullanıcı tanımlı işlevin doğrulama nesnesi. Döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

İki aralığın uyuşmazlık, ilk bileşen yineleyici ilk aralığındaki konumu için ve ikinci aralığı konumuna ikinci bileşen yineleyici konumlarını adresleme Yineleyicilerin bir çifti. Karşılaştırıldığında aralıklardaki öğeler arasındaki fark varsa veya ikinci sürüm İkili koşulda iki aralıktaki tüm öğe çifti tarafından sağlanıyorsa, ardından ilk bileşen yineleyici konum son öğeden ilk işaret aralığı ve ikinci bileşen yineleyici son öğeden konuma ikinci aralığında test.

### <a name="remarks"></a>Açıklamalar

Olduğunu gibi birçok öğe olduğundan [first1 tarafından last1). Belirtilen aralıktaki first2 başlayan bir aralıktaki ilk şablon işlevi varsayar. Varsa ikinci aralığında daha fazla, bunlar yoksayılır; varsa daha az tanımsız davranışa neden olur.

Aranacak aralık geçerli olmalı; Tüm yineleyiciler tekrar başvurulabilir olmalı ve son konuma ilk konumdan erişilebilmelidir.

Zaman algoritmanın karmaşıklığı, doğrusal daha kısa bir aralık içinde yer alan öğelerin sayısı.

Kullanıcı tanımlı koşul eşdeğerlik ilişkisi, simetrik, yansıma ve işlenenleri arasındaki geçişli dayatmak için gerekli değildir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, uyuşmazlığı kullanmayı gösterir. C ++ 03 aşırı yalnızca beklenmeyen bir sonuç nasıl üretebileceği göstermek için gösterilir.

```cpp
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>
#include <string>
#include <utility>

using namespace std;

// Return whether first element is twice the second
// Note that this is not a symmetric, reflexive and transitive equivalence.
// mismatch and equal accept such predicates, but is_permutation does not.
bool twice(int elem1, int elem2)
{
    return elem1 == elem2 * 2;
}

void PrintResult(const string& msg, const pair<vector<int>::iterator, vector<int>::iterator>& result,
    const vector<int>& left, const vector<int>& right)
{
    // If either iterator stops before reaching the end of its container,
    // it means a mismatch was detected.
    if (result.first != left.end() || result.second != right.end())
    {
        string leftpos(result.first == left.end() ? "end" : to_string(*result.first));
        string rightpos(result.second == right.end() ? "end" : to_string(*result.second));
        cout << msg << "mismatch. Left iterator at " << leftpos
            << " right iterator at " << rightpos << endl;
    }
    else
    {
        cout << msg << " match." << endl;
    }
}

int main()
{

    vector<int> vec_1{ 0, 5, 10, 15, 20, 25 };
    vector<int> vec_2{ 0, 5, 10, 15, 20, 25, 30 };

    // Testing different length vectors for mismatch (C++03)
    auto match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin());
    bool is_mismatch = match_vecs.first != vec_1.end();
    cout << "C++03: vec_1 and vec_2 are a mismatch: " << boolalpha << is_mismatch << endl;

    // Using dual-range overloads:

    // Testing different length vectors for mismatch (C++14)
    match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin(), vec_2.end());
    PrintResult("C++14: vec_1 and vec_2: ", match_vecs, vec_1, vec_2);

    // Identify point of mismatch between vec_1 and modified vec_2.
    vec_2[3] = 42;
    match_vecs = mismatch(vec_1.begin(), vec_1.end(), vec_2.begin(), vec_2.end());
    PrintResult("C++14 vec_1 v. vec_2 modified: ", match_vecs, vec_1, vec_2);

    // Test vec_3 and vec_4 for mismatch under the binary predicate twice (C++14)
    vector<int> vec_3{ 10, 20, 30, 40, 50, 60 };
    vector<int> vec_4{ 5, 10, 15, 20, 25, 30 };
    match_vecs = mismatch(vec_3.begin(), vec_3.end(), vec_4.begin(), vec_4.end(), twice);
    PrintResult("vec_3 v. vec_4 with pred: ", match_vecs, vec_3, vec_4);

    vec_4[5] = 31;
    match_vecs = mismatch(vec_3.begin(), vec_3.end(), vec_4.begin(), vec_4.end(), twice);
    PrintResult("vec_3 v. modified vec_4 with pred: ", match_vecs, vec_3, vec_4);

    // Compare a vector<int> to a list<int>
    list<int> list_1{ 0, 5, 10, 15, 20, 25 };
    auto match_vec_list = mismatch(vec_1.begin(), vec_1.end(), list_1.begin(), list_1.end());
    is_mismatch = match_vec_list.first != vec_1.end() || match_vec_list.second != list_1.end();
    cout << "vec_1 and list_1 are a mismatch: " << boolalpha << is_mismatch << endl;

    char c;
    cout << "Press a key" << endl;
    cin >> c;

}

/*
Output:
C++03: vec_1 and vec_2 are a mismatch: false
C++14: vec_1 and vec_2: mismatch. Left iterator at end right iterator at 30
C++14 vec_1 v. vec_2 modified: mismatch. Left iterator at 15 right iterator at 42
C++14 vec_3 v. vec_4 with pred:  match.
C++14 vec_3 v. modified vec_4 with pred: mismatch. Left iterator at 60 right iterator at 31
C++14: vec_1 and list_1 are a mismatch: false
Press a key
*/

```

## <a name="alg_move"></a>  &lt;algoritma&gt; Taşı

Belirtilen aralıkla ilişkili öğeleri taşı.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator move(
    InputIterator first,
    InputIterator last,
    OutputIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Nereden başlayacağınızı taşımak için öğe aralığını gösteren bir giriş yineleyici.

*Son*<br/>
Taşıma öğelerin aralığının sonunu gösteren bir giriş yineleyici.

*Hedef*<br/>
Taşınan öğeleri içeren için çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi değerlendirir `*(dest + N) = move(*(first + N))` her biri için bir kez `N` aralığında `[0, last - first)`, öğesinin artan değerleri için `N` en düşük değerden başlayarak. Ardından döndürür `dest + N`. Varsa `dest` ve *ilk* depolama bölgelerini belirlemek *dest* aralığında olmamalıdır `[first, last)`.

## <a name="move_backward"></a>  move_backward

Bir yineleyicinin öğelerini diğerine taşır. Hareket belirli bir aralıktaki son öğeyle başlar ve söz konusu aralıktaki ilk öğeyle biter.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
   BidirectionalIterator2 move_backward(
       BidirectionalIterator1 first,
       BidirectionalIterator1 last,
       BidirectionalIterator2 destEnd);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri buradan taşımak amacıyla aralığın başlangıcını gösteren yineleyici.

*Son*<br/>
Öğeleri buradan taşımak amacıyla aralığın sonunu gösteren yineleyici. Bu öğe taşınmaz.

*destEnd*<br/>
Hedef aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi değerlendirir `*(destEnd - N - 1) = move(*(last - N - 1))` her biri için bir kez `N` aralığında `[0, last - first)`, öğesinin artan değerleri için `N` en düşük değerden başlayarak. Ardından döndürür `destEnd - (last - first)`. Varsa *destEnd* ve *ilk* depolama bölgelerini belirlemek *destEnd* aralığında olmamalıdır `[first, last)`.

`move` ve `move_backward` kullanmayla işlevsel olarak eşdeğerdir `copy` ve `copy_backward` taşıma yineleyicili.

## <a name="next_permutation"></a>  next_permutation

Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.

```cpp
template<class BidirectionalIterator>
bool next_permutation(BidirectionalIterator first, BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
bool next_permutation(BidirectionalIterator first, BidirectionalIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dizilmiş için aralıktaki ilk öğenin konumuna işaret eden bir çift yönlü yineleyici.

*Son*<br/>
Dizilmiş için bir son öğeden aralığındaki konumu işaret eden bir çift yönlü yineleyici.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**true** lexicographically sonraki permütasyon varsa ve aralığı; özgün sıralama değiştirilmiştir, aksi takdirde **false**, bu durumda sıralama sözlüksel en küçük dönüştürülür PERMÜTASYON.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Varsayılan ikili koşul küçüktür ve aralıktaki öğeleri sonraki permütasyon iyi tanımlanmış Sigortası küçüktür biçiminde karşılaştırılabilir olması gerekir.

Karmaşıklığı en fazla ile doğrusal (* Soyadı - *) / 2 değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_next_perm.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt
{
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      { return ( m_nVal < rhs.m_nVal );}
   friend   ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs )
{
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main()
{
   // Reordering the elements of type CInt in a deque
   // using the prev_permutation algorithm
   CInt c1 = 5, c2 = 1, c3 = 10;
   bool deq1Result;
   deque<CInt> deq1, deq2, deq3;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   deq1Result = next_permutation ( deq1.begin( ), deq1.end( ) );

   if ( deq1Result )
      cout << "The lexicographically next permutation "
           << "exists and has\nreplaced the original "
           << "ordering of the sequence in deq1." << endl;
   else
      cout << "The lexicographically next permutation doesn't "
           << "exist\n and the lexicographically "
           << "smallest permutation\n has replaced the "
           << "original ordering of the sequence in deq1." << endl;

   cout << "After one application of next_permutation,\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl << endl;

   // Permuting vector elements with binary function mod_lesser
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = -3 ; i <= 3 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   next_permutation ( v1.begin( ), v1.end( ), mod_lesser );

   cout << "After the first next_permutation, vector v1 is:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= 5 ) {
      next_permutation ( v1.begin( ), v1.end( ), mod_lesser );
      cout << "After another next_permutation of vector v1,\n v1 =   ( " ;
      for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ;Iter1 ++ )
         cout << *Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
The original deque of CInts is deq1 = ( CInt( 5 ), CInt( 1 ), CInt( 10 ) ).
The lexicographically next permutation exists and has
replaced the original ordering of the sequence in deq1.
After one application of next_permutation,
deq1 = ( CInt( 5 ), CInt( 10 ), CInt( 1 ) ).

Vector v1 is ( -3 -2 -1 0 1 2 3 ).
After the first next_permutation, vector v1 is:
v1 = ( -3 -2 -1 0 1 3 2 ).
After another next_permutation of vector v1,
v1 =   ( -3 -2 -1 0 2 1 3 ).
After another next_permutation of vector v1,
v1 =   ( -3 -2 -1 0 2 3 1 ).
After another next_permutation of vector v1,
v1 =   ( -3 -2 -1 0 3 1 2 ).
After another next_permutation of vector v1,
v1 =   ( -3 -2 -1 0 3 2 1 ).
After another next_permutation of vector v1,
v1 =   ( -3 -2 -1 1 0 2 3 ).
```

## <a name="nth_element"></a>  nth_element

Doğru şekilde bularak öğelerin bir aralığını bölümler *n*öğedeki aralığındaki dizinin önündeki tüm öğeler ona eşit veya ve sırayla izleyen tüm öğeler, böylece büyük th olan bir ya da ona eşit.

```cpp
template<class RandomAccessIterator>
void nth_element( RandomAccessIterator first, RandomAccessIterator _Nth, RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
void nth_element( RandomAccessIterator first, RandomAccessIterator _Nth, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bölümlenecek aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*_Nth*<br/>
Bölüm sınırında doğru sıralanmalıdır öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*Son*<br/>
Bölümlenecek aralığın son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

`nth_element` Algoritması alt aralıklara öğeleri ya da yan garantilemez, *n*öğedeki sıralanır. Bu nedenle daha az garantisi kolaylaştırır `partial_sort`, aşağıda seçilen öğeyi aralıktaki öğeleri sıralar ve daha hızlı alternatif olarak kullanılabilir `partial_sort` olduğunda alt aralığı sıralama gerekli değildir.

Öğeleri eşdeğerdir, ancak mutlaka eşittir, hiçbiri diğerinden olduğu.

Ortalama bir sıralama karmaşıklık ilişkilendirilebilmesi için doğrusal * soyadı - *.

### <a name="example"></a>Örnek

```cpp
// alg_nth_elem.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 ) {
   return elem1 > elem2;
}

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1.push_back( 3 * i );

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
      v1.push_back( 3 * ii + 1 );

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
      v1.push_back( 3 * iii +2 );

   cout << "Original vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   nth_element(v1.begin( ), v1.begin( ) + 3, v1.end( ) );
   cout << "Position 3 partitioned vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order, specify binary predicate
   nth_element( v1.begin( ), v1.begin( ) + 4, v1.end( ),
          greater<int>( ) );
   cout << "Position 4 partitioned (greater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   random_shuffle( v1.begin( ), v1.end( ) );
   cout << "Shuffled vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   nth_element( v1.begin( ), v1.begin( ) + 5, v1.end( ), UDgreater );
   cout << "Position 5 partitioned (UDgreater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

## <a name="none_of"></a>  none_of

Döndürür **true** koşul olduğunda hiçbir zaman verilen aralıktaki öğeler arasında yok.

```cpp
template<class InputIterator, class BinaryPredicate>
bool none_of(InputIterator first, InputIterator last, BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bir koşul için öğelerin bir aralığını denetlemek başlangıç noktası gösteren bir giriş yineleyici.

*Son*<br/>
Öğe aralığını sonuna belirten bir giriş yineleyici.

*Comp*<br/>
Sınanacak koşulu. Bu koşulu tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** koşul belirtilen aralığında en az bir kez algılanmazsa ve **false** koşul algılanırsa.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü **true** yalnızca şu durumlarda, bazı `N` aralığında `[0, last - first)`, koşul `comp(*(first + N))` her zaman **false**.

## <a name="partial_sort"></a>  partial_sort

Bir aralıktaki daha küçük öğelerin belirtilen sayısını azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class RandomAccessIterator>
void partial_sort(
    RandomAccessIterator first,
    RandomAccessIterator sortEnd,
    RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
void partial_sort(
    RandomAccessIterator first,
    RandomAccessIterator sortEnd,
    RandomAccessIterator last
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*sortEnd*<br/>
Sıralanacak alt aralığı son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*Son*<br/>
Kısmen sıralanacak bir son öğeden aralığındaki konumu ele alan bir rasgele erişim yineleyicisi.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Öğeleri eşdeğerdir, ancak mutlaka eşittir, hiçbiri diğerinden olduğu. `sort` Algoritması kararlı değilse ve öğeleri, eşdeğer öğelerin göreli sıralamasını korunur olduğunu garanti etmez. Algoritma `stable_sort` bu özgün sıralamasını koruması.

Ortalama kısmi sıralama karmaşıklığı *O*((`last`- `first`) günlük (`sortEnd`- `first`)).

### <a name="example"></a>Örnek

```cpp
// alg_partial_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
   {
      v1.push_back( 2 * ii +1 );
   }

   cout << "Original vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   partial_sort(v1.begin( ), v1.begin( ) + 6, v1.end( ) );
   cout << "Partially sorted vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To partially sort in descending order, specify binary predicate
   partial_sort(v1.begin( ), v1.begin( ) + 4, v1.end( ), greater<int>( ) );
   cout << "Partially resorted (greater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   partial_sort(v1.begin( ), v1.begin( ) + 8, v1.end( ),
UDgreater );
   cout << "Partially resorted (UDgreater) vector:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector:
v1 = ( 0 2 4 6 8 10 1 3 5 7 9 11 )
Partially sorted vector:
v1 = ( 0 1 2 3 4 5 10 8 6 7 9 11 )
Partially resorted (greater) vector:
v1 = ( 11 10 9 8 0 1 2 3 4 5 6 7 )
Partially resorted (UDgreater) vector:
v1 = ( 11 10 9 8 7 6 5 4 0 1 2 3 )
```

## <a name="partial_sort_copy"></a>  partial_sort_copy

Öğeleri bir kaynak aralığından bir hedef aralığa kopyalar, burada kaynak öğeleri daha küçük olana ya da belirtilen başka bir ikili koşula göre sıralanır.

```cpp
template<class InputIterator, class RandomAccessIterator>
RandomAccessIterator partial_sort_copy(
    InputIterator first1,
    InputIterator last1,
    RandomAccessIterator first2,
    RandomAccessIterator last2 );

template<class InputIterator, class RandomAccessIterator, class BinaryPredicate>
RandomAccessIterator partial_sort_copy(
    InputIterator first1,
    InputIterator last1,
    RandomAccessIterator first2,
    RandomAccessIterator last2,
    BinaryPredicate comp);
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Kaynak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*last1*<br/>
Bir önceki öğenin konumunu son öğesi kaynak aralıktaki ele alan giriş yineleyici.

*first2*<br/>
Sıralanmış bir hedef aralıktaki ilk öğenin konumunu bulan bir rastgele erişim yineleyicisi.

*Soyadı2*<br/>
Bir önceki öğenin konumunu son öğesi sıralanmış bir hedef aralıktaki rastgele erişim yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Bir kaynak aralığındaki son öğeden hedef aralığı bir ötesindeki öğeyi ele alan bir rastgele erişim yineleyicisini eklenir.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef aralıklar çakışmaması gerekir ve geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

İkili koşul, böylece denk olmayan öğelerin sıralama katı zayıf sağlamanız gerekir, ancak eşdeğer olan öğeler değildir. İki öğe altında daha az daha eşdeğerdir, ancak mutlaka eşittir, hiçbiri diğerinden olan.

### <a name="example"></a>Örnek

```cpp
// alg_partial_sort_copy.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <functional>
#include <iostream>

int main() {
    using namespace std;
    vector<int> v1, v2;
    list<int> list1;
    vector<int>::iterator iter1, iter2;
    list<int>::iterator list1_Iter, list1_inIter;

    int i;
    for (i = 0; i <= 9; i++)
        v1.push_back(i);

    random_shuffle(v1.begin(), v1.end());

    list1.push_back(60);
    list1.push_back(50);
    list1.push_back(20);
    list1.push_back(30);
    list1.push_back(40);
    list1.push_back(10);

    cout << "Vector v1 = ( " ;
    for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
        cout << *iter1 << " ";
    cout << ")" << endl;

    cout << "List list1 = ( " ;
    for (list1_Iter = list1.begin();
         list1_Iter!= list1.end();
         list1_Iter++)
        cout << *list1_Iter << " ";
    cout << ")" << endl;

    // Copying a partially sorted copy of list1 into v1
    vector<int>::iterator result1;
    result1 = partial_sort_copy(list1.begin(), list1.end(),
             v1.begin(), v1.begin() + 3);

    cout << "List list1 Vector v1 = ( " ;
    for (iter1 = v1.begin() ; iter1 != v1.end() ; iter1++)
        cout << *iter1 << " ";
    cout << ")" << endl;
    cout << "The first v1 element one position beyond"
         << "\n the last L 1 element inserted was " << *result1
         << "." << endl;

    // Copying a partially sorted copy of list1 into v2
    int ii;
    for (ii = 0; ii <= 9; ii++)
        v2.push_back(ii);

    random_shuffle(v2.begin(), v2.end());
    vector<int>::iterator result2;
    result2 = partial_sort_copy(list1.begin(), list1.end(),
             v2.begin(), v2.begin() + 6);

    cout << "List list1 into Vector v2 = ( " ;
    for (iter2 = v2.begin() ; iter2 != v2.end(); iter2++)
        cout << *iter2 << " ";
    cout << ")" << endl;
    cout << "The first v2 element one position beyond"
         << "\n the last L 1 element inserted was " << *result2
         << "." << endl;
}
```

## <a name="partition"></a>  Bölüm

Bir aralıktaki öğeleri, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

```cpp
template<class BidirectionalIterator, class Predicate>
BidirectionalIterator partition(
    BidirectionalIterator first,
    BidirectionalIterator last,
    Predicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bölümlenecek aralıktaki ilk öğenin konumunu bulan bir çift yönlü yineleyici.

*Son*<br/>
Bölümlenecek aralığın son öğesinde geçmiş konumu ele alan bir çift yönlü yineleyici.

*Comp*<br/>
Bir öğe sınıflandırılmaya ise karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Koşul durumu değil karşılamak için aralıktaki ilk öğenin konumunu bulan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Öğeleri *bir* ve *b* eşdeğerdir, ancak mutlaka, her iki eşit *çekme isteği* ( *bir*, *b*) false'tur ve *çekme isteği* ( *b*, *bir*) false ise, burada *çekme isteği* parametre tarafından belirtilen bir koşuldur. `partition` Algoritması kararlı değilse ve öğeleri, eşdeğer öğelerin göreli sıralamasını korunur olduğunu garanti etmez. Algoritma `stable_ partition` bu özgün sıralamasını koruması.

Karmaşıklığı doğrusal: vardır (`last` - `first`) uygulamalarının *comp* ve en fazla (`last` - `first`) / 2 değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value ) {
   return value > 5;
}

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 10 ; i++ )
   {
      v1.push_back( i );
   }
   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Partition the range with predicate greater10
   partition ( v1.begin( ), v1.end( ), greater5 );
   cout << "The partitioned set of elements in v1 is: ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="partition_copy"></a>  partition_copy

Bir koşul olduğu öğeleri kopyalar **true** bir hedef ve koşulun **false** diğerine. Öğeler belirtilen bir aralıktan gelmelidir.

```cpp
template<class InputIterator, class OutputIterator1, class OutputIterator2, class Predicate>
pair<OutputIterator1, OutputIterator2>
    partition_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator1 dest1,
    OutputIterator2 dest2,
    Predicate pred);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bir koşulu kontrol etmek için bir aralık başlangıcını gösteren bir giriş yineleyici.

*Son*<br/>
Bir aralığın sonunu gösteren bir giriş yineleyici.

*dest1*<br/>
Çıkış yineleyici için bir koşul true döndüren öğeleri kopyalamak için kullanılan test kullanarak *_Pred*.

*dest2*<br/>
Çıkış yineleyici için bir koşul false döndüren öğeleri kopyalamak için kullanılan test kullanarak *_Pred*.

*_Pred*<br/>
Sınanacak koşulu. Bu test edilecek koşulu tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi her öğe kopyalar `X` içinde `[first,last)` için `*dest1++` varsa `_Pred(X)` true ise veya `*dest2++` Aksi takdirde. Döndürür `pair<OutputIterator1, OutputIterator2>(dest1, dest2)`.

## <a name="partition_point"></a>  partition_point

Koşulu karşılamayan verili aralıktaki ilk öğeyi döndürür. Öğeler koşulu karşılayanlar karşılamayanlardan önce gelecek şekilde sıralanır.

```cpp
template<class ForwardIterator, class Predicate>
ForwardIterator partition_point(
    ForwardIterator first,
    ForwardIterator last,
    Predicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
A `ForwardIterator` denetlemek için bir koşul için bir aralık başlangıcını gösterir.

*Son*<br/>
A `ForwardIterator` bir aralığın sonunu belirtir.

*Comp*<br/>
Sınanacak koşulu. Bu öğe, aranan tarafından karşılanması koşul tanımlayan bir kullanıcı tanımlı işlevin doğrulama nesnesi tarafından sağlanır. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `ForwardIterator` tarafından test koşul yerine getirmiyor ilk öğeye başvuran *comp*, ya da döndürür *son* bir bulunamaması durumunda.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi ilk yineleyicisi bulur `it` içinde `[first, last)` hangi `comp(*it)` olduğu **false**. Sıralı olarak sıralanmalıdır *comp*.

## <a name="pop_heap"></a>  pop_heap

En büyük öğeyi bir yığının önünden aralıktaki bir sonraki son konuma kaldırır ve ardından kalan öğelerden yeni bir yığın oluşturur.

```cpp
template<class RandomAccessIterator>
void pop_heap( RandomAccessIterator first, RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
void pop_heap(RandomAccessIterator first, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Yığındaki ilk öğenin konumunu ele alan bir rastgele erişim yineleyicisi.

*Son*<br/>
Bir önceki öğenin konumunu son öğesi yığınındaki rastgele erişim yineleyici.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

`pop_heap` Algoritmasıdır, aralığın sondan sonraki konumunda bir öğe eklenen öğe eklenen söz konusu, aralıktaki önceki öğeleri içeren bir yığın push_heap algoritması tarafından gerçekleştirilen işlem tersini yığın yığınındaki öğelerden daha büyüktür.

Yığınlar iki özelliğe sahiptir:

- İlk öğe her zaman daha büyüktür.

- Öğeleri eklenebilir veya Logaritmik süre kaldırıldı.

Yığınlar öncelikli kuyruklardaki uygulamak için ideal bir yöntem olduğunu ve C++ Standart Kitaplığı kapsayıcı bağdaştırıcısı uygulamasında kullanılan [priority_queue sınıfı](../standard-library/priority-queue-class.md).

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Yeni eklenen son öğe dışlama aralığı, bir yığın olması gerekir.

Karmaşıklığı en fazla günlük gerektiren Logaritmik (* Soyadı - *) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_pop_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main()  {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 1 ; i <= 9 ; i++ )
      v1.push_back( i );

   // Make v1 a heap with default less than ordering
   random_shuffle( v1.begin( ), v1.end( ) );
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Add an element to the back of the heap
   v1.push_back( 10 );
   push_heap( v1.begin( ), v1.end( ) );
   cout << "The reheaped v1 with 10 added is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove the largest element from the heap
   pop_heap( v1.begin( ), v1.end( ) );
   cout << "The heap v1 with 10 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << endl;

   // Make v1 a heap with greater-than ordering with a 0 element
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   v1.push_back( 0 );
   push_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The 'greater than' reheaped v1 puts the smallest "
        << "element first:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Application of pop_heap to remove the smallest element
   pop_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The 'greater than' heaped v1 with the smallest element\n "
        << "removed from the heap is: ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="prev_permutation"></a>  prev_permutation

Bir aralıktaki öğeleri yeniden sıralar, böylece, önceki anlamı bir ikili koşula sahip burada belirtilebilir varsa özgün sıralama sözlüksel önceki permütasyon ile değiştirilir.

```cpp
template<class BidirectionalIterator>
bool prev_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
bool prev_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dizilmiş için aralıktaki ilk öğenin konumuna işaret eden bir çift yönlü yineleyici.

*Son*<br/>
Dizilmiş için bir son öğeden aralığındaki konumu işaret eden bir çift yönlü yineleyici.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

**true** lexicographically önceki permütasyon varsa ve aralığı; özgün sıralama değiştirilmiştir, aksi takdirde **false**, bu durumda sıralama sözlüksel en büyük dönüştürülür PERMÜTASYON.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Varsayılan ikili koşul küçüktür aralıktaki öğeleri daha küçük olması gerekir-daha önceki permütasyon iyi tanımlanmış olduğundan emin olmak için karşılaştırılabilir.

Karmaşıklığı en fazla ile doğrusal (`last` -  `first`) / 2 değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_prev_perm.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>
#include <ostream>

using namespace std;
class CInt;
ostream& operator<<( ostream& osIn, const CInt& rhs );

class CInt {
public:
   CInt( int n = 0 ) : m_nVal( n ){}
   CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ){}
   CInt&   operator=( const CInt& rhs ) {m_nVal =
   rhs.m_nVal; return *this;}
   bool operator<( const CInt& rhs ) const
      {return ( m_nVal < rhs.m_nVal );}
   friend ostream& operator<<( ostream& osIn, const CInt& rhs );

private:
   int m_nVal;
};

inline ostream& operator<<( ostream& osIn, const CInt& rhs ) {
   osIn << "CInt( " << rhs.m_nVal << " )";
   return osIn;
}

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
};

int main() {
   // Reordering the elements of type CInt in a deque
   // using the prev_permutation algorithm
   CInt c1 = 1, c2 = 5, c3 = 10;
   bool deq1Result;
   deque<CInt> deq1, deq2, deq3;
   deque<CInt>::iterator d1_Iter;

   deq1.push_back ( c1 );
   deq1.push_back ( c2 );
   deq1.push_back ( c3 );

   cout << "The original deque of CInts is deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl;

   deq1Result = prev_permutation ( deq1.begin( ), deq1.end( ) );

   if ( deq1Result )
      cout << "The lexicographically previous permutation "
           << "exists and has \nreplaced the original "
           << "ordering of the sequence in deq1." << endl;
   else
      cout << "The lexicographically previous permutation doesn't "
           << "exist\n and the lexicographically "
           << "smallest permutation\n has replaced the "
           << "original ordering of the sequence in deq1." << endl;

   cout << "After one application of prev_permutation,\n deq1 = (";
   for ( d1_Iter = deq1.begin( ); d1_Iter != --deq1.end( ); d1_Iter++ )
      cout << " " << *d1_Iter << ",";
   d1_Iter = --deq1.end( );
   cout << " " << *d1_Iter << " )." << endl << endl;

   // Permutating vector elements with binary function mod_lesser
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = -3 ; i <= 3 ; i++ )
      v1.push_back( i );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   prev_permutation ( v1.begin( ), v1.end( ), mod_lesser );

   cout << "After the first prev_permutation, vector v1 is:\n v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= 5 ) {
      prev_permutation ( v1.begin( ), v1.end( ), mod_lesser );
      cout << "After another prev_permutation of vector v1,\n v1 =   ( " ;
      for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ;Iter1 ++ )
         cout << *Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
The original deque of CInts is deq1 = ( CInt( 1 ), CInt( 5 ), CInt( 10 ) ).
The lexicographically previous permutation doesn't exist
and the lexicographically smallest permutation
has replaced the original ordering of the sequence in deq1.
After one application of prev_permutation,
deq1 = ( CInt( 10 ), CInt( 5 ), CInt( 1 ) ).

Vector v1 is ( -3 -2 -1 0 1 2 3 ).
After the first prev_permutation, vector v1 is:
v1 = ( -3 -2 0 3 2 1 -1 ).
After another prev_permutation of vector v1,
v1 =   ( -3 -2 0 3 -1 2 1 ).
After another prev_permutation of vector v1,
v1 =   ( -3 -2 0 3 -1 1 2 ).
After another prev_permutation of vector v1,
v1 =   ( -3 -2 0 2 3 1 -1 ).
After another prev_permutation of vector v1,
v1 =   ( -3 -2 0 2 -1 3 1 ).
After another prev_permutation of vector v1,
v1 =   ( -3 -2 0 2 -1 1 3 ).
```

## <a name="push_heap"></a>  push_heap

Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.

```cpp
template<class RandomAccessIterator>
void push_heap( RandomAccessIterator first, RandomAccessIterator last );

template<class RandomAccessIterator, class BinaryPredicate>
void push_heap( RandomAccessIterator first, RandomAccessIterator last, BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Yığındaki ilk öğenin konumunu ele alan bir rastgele erişim yineleyicisi.

*Son*<br/>
Yığına dönüştürülmesi aralığın son öğesinde geçmiş konumu ele alan bir rastgele erişim yineleyicisi.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Öğesi ilk geri sonuna mevcut yığına itilecek gerekir ve ardından bu öğenin varolan bir yığın eklemek için algoritma kullanılır.

Yığınlar iki özelliğe sahiptir:

- İlk öğe her zaman daha büyüktür.

- Öğeleri eklenebilir veya Logaritmik süre kaldırıldı.

Yığınlar öncelikli kuyruklardaki uygulamak için ideal bir yöntem olduğunu ve C++ Standart Kitaplığı kapsayıcı bağdaştırıcısı uygulamasında kullanılan [priority_queue sınıfı](../standard-library/priority-queue-class.md).

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Yeni eklenen son öğe dışlama aralığı, bir yığın olması gerekir.

Karmaşıklığı en fazla günlük gerektiren Logaritmik ( *- Soyadı*) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_push_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 1 ; i <= 9 ; i++ )
      v1.push_back( i );

   random_shuffle( v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Make v1 a heap with default less than ordering
   make_heap ( v1.begin( ), v1.end( ) );
   cout << "The heaped version of vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Add an element to the heap
   v1.push_back( 10 );
   cout << "The heap v1 with 10 pushed back is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   push_heap( v1.begin( ), v1.end( ) );
   cout << "The reheaped v1 with 10 added is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl << endl;

   // Make v1 a heap with greater than ordering
   make_heap ( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater-than heaped version of v1 is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   v1.push_back(0);
   cout << "The greater-than heap v1 with 11 pushed back is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   push_heap( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "The greater than reheaped v1 with 11 added is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="random_shuffle"></a>  random_shuffle

Std::random_shuffle() işlevi yerine kullanım dışı [std::shuffle](../standard-library/algorithm-functions.md#shuffle). Bir kod örneği ve daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md) ve Stackoverflow posta [neden std::random_shuffle yöntemleri kaldırılmaktadır C ++ 14'te?](http://go.microsoft.com/fwlink/p/?linkid=397954).

## <a name="remove"></a>  Kaldır

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki belirtilen bir değeri ortadan kaldırır.

```cpp
template<class ForwardIterator, class Type>
ForwardIterator remove(ForwardIterator first, ForwardIterator last, const Type& val);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri kaldırılmakta olan aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Öğeleri kaldırılmakta olan aralıktaki son öğeden sonraki birinci konum ele alan ileriye doğru yineleyici.

*VAL*<br/>
Aralıktan kaldırılacak olan değer.

### <a name="return-value"></a>Dönüş Değeri

Yeni değiştirilmiş aralığı, işlemi dizisi için belirtilen değer boş son öğeden bir önceki son konumunu bulan ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Kaldırılmaz öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal; vardır (`last` - `first`) eşitlik karşılaştırmaları.

[Listesinde sınıfı](../standard-library/list-class.md) daha verimli bir üye işlev sürümüne sahip `remove`, hangi ayrıca i işaretçileri.

### <a name="example"></a>Örnek

```cpp
// alg_remove.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value of 7
   new_end = remove ( v1.begin( ), v1.end( ), 7 );

   cout << "Vector v1 with value 7 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To change the sequence size, use erase
   v1.erase (new_end, v1.end( ) );

   cout << "Vector v1 resized with value 7 removed is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_copy"></a>  remove_copy

Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator remove_copy(InputIterator first, InputIterator last, OutputIterator result, const Type& val);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri kaldırılmakta olan aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*Son*<br/>
Öğeleri kaldırılmakta olan aralıktaki son öğeden sonraki birinci konum ele alan bir giriş yineleyici.

*Sonuç*<br/>
Öğeleri kaldırılmakta olan hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*VAL*<br/>
Aralıktan kaldırılacak olan değer.

### <a name="return-value"></a>Dönüş Değeri

Yeni Hedef aralığın, kopyalama işlemi dizisi için belirtilen değer boş son öğeden bir öncekine son konumunu bulan ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıklar geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Belirtilen değerin kaldırıldıktan sonra kopyalanacak işlemi öğeleri içerecek şekilde hedef aralığı yeterli boş alan olmalıdır.

Kaldırılmaz öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal; vardır (`last` - `first`) eşitliği ve en çok karşılaştırmaları (`last` - `first`) atamaları.

### <a name="example"></a>Örnek

```cpp
// alg_remove_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2(10);
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle (v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:     ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value of 7
   new_end = remove_copy ( v1.begin( ), v1.end( ), v2.begin( ), 7 );

   cout << "Vector v1 is left unchanged as ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is a copy of v1 with the value 7 removed:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_copy_if"></a>  remove_copy_if

Öğeleri, bir koşulu karşılayan kopyalanmayan öğeler hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator, class Predicate>
OutputIterator remove_copy_if(InputIterator first, InputIterator Last, OutputIterator result, Predicate pred);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri kaldırılmakta olan aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*Son*<br/>
Öğeleri kaldırılmakta olan aralıktaki son öğeden sonraki birinci konum ele alan bir giriş yineleyici.

*Sonuç*<br/>
Öğeleri kaldırılmakta olan hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*_Pred*<br/>
Karşılanması gereken birli koşul, bir öğenin değerini değiştirilecek olan ' dir.

### <a name="return-value"></a>Dönüş Değeri

Yeni Hedef aralığın, koşulu karşılayan öğeleri ücretsiz işlemi dizisi son öğeden bir önceki son konumunu bulan ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Belirtilen değerin kaldırıldıktan sonra kopyalanacak işlemi öğeleri içerecek şekilde hedef aralığı yeterli boş alan olmalıdır.

Kaldırılmaz öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal: vardır (`last` - `first`) eşitliği ve en çok karşılaştırmaları (`last` - `first`) atamaları.

Bu işlevlerin nasıl davrandığı hakkında daha fazla bilgi için bkz: [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

```cpp
// alg_remove_copy_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value > 6;
}

int main() {
   using namespace std;
   vector <int> v1, v2(10);
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:      ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements with a value greater than 6
   new_end = remove_copy_if ( v1.begin( ), v1.end( ),
      v2.begin( ), greater6 );

   cout << "After the appliation of remove_copy_if to v1,\n "
        << "vector v1 is left unchanged as ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is a copy of v1 with values greater "
        << "than 6 removed:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != new_end ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="remove_if"></a>  remove_if

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki bir koşulu karşılayan öğeleri ortadan kaldırır.

```cpp
template<class ForwardIterator, class Predicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri kaldırılmakta olan aralıktaki ilk öğenin konumunu gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Öğeleri kaldırılmakta olan aralıktaki son öğeden sonraki birinci konum için işaret eden bir ileriye doğru yineleyici.

*_Pred*<br/>
Karşılanması gereken birli koşul, bir öğenin değerini değiştirilecek olan ' dir.

### <a name="return-value"></a>Dönüş Değeri

Yeni değiştirilmiş aralığı, işlemi dizisi için belirtilen değer boş son öğeden bir önceki son konumunu bulan ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Kaldırılmaz öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal: vardır (`last` - `first`) eşitlik karşılaştırmaları.

Liste, işaretçiler i Kaldır daha verimli bir üye işlev sürümü vardır.

### <a name="example"></a>Örnek

```cpp
// alg_remove_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value > 6;
}

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, new_end;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Remove elements satisfying predicate greater6
   new_end = remove_if (v1.begin( ), v1.end( ), greater6 );

   cout << "Vector v1 with elements satisfying greater6 removed is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To change the sequence size, use erase
   v1.erase (new_end, v1.end( ) );

   cout << "Vector v1 resized elements satisfying greater6 removed is\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace"></a>  Değiştir

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir değerle eşleşiyorsa değiştirir.

```cpp
template<class ForwardIterator, class Type>
void replace(
    ForwardIterator first,
    ForwardIterator last,
    const Type& oldVal,
    const Type& newVal);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri değiştirilmekte aralıktaki ilk öğenin konumunu gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Öğeleri değiştirilmekte aralığın son öğesinde geçmiş konumu bir işaret eden bir ileriye doğru yineleyici.

*_OldVal*<br/>
Değiştirilmekte olan öğelerin eski değeri.

*_NewVal*<br/>
Eski değerle öğelerine atanan yeni değer.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Değiştirilmemişse öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal; vardır (`last` - `first`) eşitliği ve en çok karşılaştırmaları (`last` - `first`) atamaları yeni değerler.

### <a name="example"></a>Örnek

```cpp
// alg_replace.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle (v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements with a value of 7 with a value of 700
   replace (v1.begin( ), v1.end( ), 7 , 700);

   cout << "The vector v1 with a value 700 replacing that of 7 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_copy"></a>  replace_copy

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator replace_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    const Type& oldVal,
    const Type& newVal);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri değiştirilmekte aralıktaki ilk öğenin konumunu gösteren bir giriş yineleyici.

*Son*<br/>
Bir önceki öğenin konumunu son öğeyi aralıktaki öğeleri değiştirilmekte işaret eden bir giriş yineleyici.

*Sonuç*<br/>
Değiştirilen öğeleri dizisi kopyalandığı hedef aralıktaki ilk öğeyi gösteren bir çıkış yineleyici.

*_OldVal*<br/>
Değiştirilmekte olan öğelerin eski değeri.

*_NewVal*<br/>
Eski değerle öğelerine atanan yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Bir önceki öğenin konumunu son öğesi değiştirilmiş öğe dizisi kopyalandığı hedef aralıktaki işaret eden bir çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıklar çakışmaması gerekir ve her ikisi de geçerli olmalıdır: tüm işaretçiler tekrar başvurulabilir olmalı ve dizileri içinde son konuma ilk konumdan erişilebilmelidir.

Değiştirilmemişse öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal: vardır (`last` - `first`) karşılaştırmalar eşitlik ve en çok (`last` - `first`) atamaları yeni değerler.

### <a name="example"></a>Örnek

```cpp
// alg_replace_copy.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;
   list <int> L1 (15);
   vector <int>::iterator Iter1;
   list <int>::iterator L_Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );

   int iii;
   for ( iii = 0 ; iii <= 15 ; iii++ )
      v1.push_back( 1 );

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in one part of a vector with a value of 7
   // with a value of 70 and copy into another part of the vector
   replace_copy ( v1.begin( ), v1.begin( ) + 14,v1.end( ) -15, 7 , 70);

   cout << "The vector v1 with a value 70 replacing that of 7 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in a vector with a value of 70
   // with a value of 1 and copy into a list
   replace_copy ( v1.begin( ), v1.begin( ) + 14,L1.begin( ), 7 , 1);

   cout << "The list copy L1 of v1 with the value 0 replacing "
        << "that of 7 is:\n ( " ;
   for ( L_Iter1 = L1.begin( ) ; L_Iter1 != L1.end( ) ; L_Iter1++ )
      cout << *L_Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_copy_if"></a>  replace_copy_if

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.

```cpp
template<class InputIterator, class OutputIterator, class Predicate, class Type>
OutputIterator replace_copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    Predicate pred,
    const Type& val);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri değiştirilmekte aralıktaki ilk öğenin konumunu gösteren bir giriş yineleyici.

*Son*<br/>
Bir önceki öğenin konumunu son öğeyi aralıktaki öğeleri değiştirilmekte işaret eden bir giriş yineleyici.

*Sonuç*<br/>
Öğeleri kopyalandığı hedef aralıktaki ilk öğenin konumuna işaret eden bir çıkış yineleyici.

*_Pred*<br/>
Karşılanması gereken birli koşul, bir öğenin değerini değiştirilecek olan ' dir.

*VAL*<br/>
Eski değeri koşulu karşılayan öğelerine atanan yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Bir önceki öğenin konumunu son öğesi değiştirilmiş öğe dizisi kopyalandığı hedef aralıktaki işaret eden bir çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıklar çakışmaması gerekir ve her ikisi de geçerli olmalıdır: tüm işaretçiler tekrar başvurulabilir olmalı ve dizileri içinde son konuma ilk konumdan erişilebilmelidir.

Değiştirilmemişse öğelerin sırasını tutarlı kalır.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal; vardır (`last` - `first`) eşitliği ve en çok karşılaştırmaları (`last` - `first`) atamaları yeni değerler.

### <a name="example"></a>Örnek

```cpp
// alg_replace_copy_if.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value > 6;
}

int main() {
   using namespace std;
   vector <int> v1;
   list <int> L1 (13);
   vector <int>::iterator Iter1;
   list <int>::iterator L_Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );

   int iii;
   for ( iii = 0 ; iii <= 13 ; iii++ )
      v1.push_back( 1 );

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements with a value of 7 in the 1st half of a vector
   // with a value of 70 and copy it into the 2nd half of the vector
   replace_copy_if ( v1.begin( ), v1.begin( ) + 14,v1.end( ) -14,
      greater6 , 70);

   cout << "The vector v1 with values of 70 replacing those greater"
        << "\n than 6 in the 1st half & copied into the 2nd half is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements in a vector with a value of 70
   // with a value of 1 and copy into a list
   replace_copy_if ( v1.begin( ), v1.begin( ) + 13,L1.begin( ),
      greater6 , -1 );

   cout << "A list copy of vector v1 with the value -1\n replacing "
        << "those greater than 6 is:\n ( " ;
   for ( L_Iter1 = L1.begin( ) ; L_Iter1 != L1.end( ) ; L_Iter1++ )
      cout << *L_Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="replace_if"></a>  replace_if

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.

```cpp
template<class ForwardIterator, class Predicate, class Type>
void replace_if(
    ForwardIterator first,
    ForwardIterator last,
    Predicate pred,
    const Type& val);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Öğeleri değiştirilmekte aralıktaki ilk öğenin konumunu gösteren bir ileriye doğru yineleyici.

*Son*<br/>
Öğeleri değiştirilmekte aralığın son öğesinde geçmiş konumu bir işaret eden bir yineleyici.

*_Pred*<br/>
Karşılanması gereken birli koşul, bir öğenin değerini değiştirilecek olan ' dir.

*VAL*<br/>
Eski değeri koşulu karşılayan öğelerine atanan yeni değer.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Değiştirilmemişse öğelerin sırasını tutarlı kalır.

Algoritma `replace_if` Genelleştirme algoritması olan `replace`, belirtilen sabit değer eşitliği yerine belirtilmesi için herhangi bir koşulu izin verme.

`operator==` Eşitlik öğeler arasındaki bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Karmaşıklığı doğrusal: vardır (`last` - `first`) karşılaştırmalar eşitlik ve en çok (`last` - `first`) atamaları yeni değerler.

### <a name="example"></a>Örnek

```cpp
// alg_replace_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value ) {
   return value > 6;
}

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
      v1.push_back( 7 );

   random_shuffle ( v1.begin( ), v1.end( ) );
   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Replace elements satisfying the predicate greater6
   // with a value of 70
   replace_if ( v1.begin( ), v1.end( ), greater6 , 70);

   cout << "The vector v1 with a value 70 replacing those\n "
        << "elements satisfying the greater6 predicate is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="reverse"></a>  geriye doğru

Bir aralık içindeki öğelerin sırasını tersine çevirir.

```cpp
template<class BidirectionalIterator>
void reverse(BidirectionalIterator first, BidirectionalIterator last);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
İçinde öğeleri dizilmiş aralıktaki ilk öğenin konumuna işaret eden bir çift yönlü yineleyici.

*Son*<br/>
Bir önceki öğenin konumunu son öğesi içinde öğeleri dizilmiş aralıktaki işaret eden bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

### <a name="example"></a>Örnek

```cpp
// alg_reverse.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Reverse the elements in the vector
   reverse (v1.begin( ), v1.end( ) );

   cout << "The modified vector v1 with values reversed is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 0 1 2 3 4 5 6 7 8 9 ).
The modified vector v1 with values reversed is:
( 9 8 7 6 5 4 3 2 1 0 ).
```

## <a name="reverse_copy"></a>  reverse_copy

Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine çevirir

```cpp
template<class BidirectionalIterator, class OutputIterator>
OutputIterator reverse_copy(
    BidirectionalIterator first,
    BidirectionalIterator Last,
    OutputIterator result);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
İçinde öğeleri dizilmiş kaynak aralıktaki ilk öğenin konumuna işaret eden bir çift yönlü yineleyici.

*Son*<br/>
Bir önceki öğenin konumunu son öğesi içinde öğeleri dizilmiş kaynak aralıktaki işaret eden bir çift yönlü yineleyici.

*Sonuç*<br/>
Öğeleri kopyalandığı hedef aralıktaki ilk öğenin konumuna işaret eden bir çıkış yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Bir önceki öğenin konumunu son öğesi değiştirilmiş öğe dizisi kopyalandığı hedef aralıktaki işaret eden bir çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıklar geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

### <a name="example"></a>Örnek

```cpp
// alg_reverse_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1, v2( 10 );
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = 0 ; i <= 9 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Reverse the elements in the vector
   reverse_copy (v1.begin( ), v1.end( ), v2.begin( ) );

   cout << "The copy v2 of the reversed vector v1 is:\n ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   cout << "The original vector v1 remains unmodified as:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;
}
```

## <a name="rotate"></a>  Döndürme

İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.

```cpp
template<class ForwardIterator>
void rotate(
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Döndürülecek aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Orta*<br/>
Sınır aralıktaki öğeleri de aralık ilk kısmı ile değiştirilecek olan aralığın ikinci bölümü ilk öğenin konumunu ele alan tanımlama ileriye doğru yineleyici.

*Son*<br/>
Döndürülecek bir önceki öğenin konumunu son öğeden bir aralıktaki ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklığı en fazla ile doğrusal (`last` - `first`) değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_rotate.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1;
   deque <int> d1;
   vector <int>::iterator v1Iter1;
   deque<int>::iterator d1Iter1;

   int i;
   for ( i = -3 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =0 ; ii <= 5 ; ii++ )
   {
      d1.push_back( ii );
   }

   cout << "Vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   rotate ( v1.begin( ), v1.begin( ) + 3 , v1.end( ) );
   cout << "After rotating, vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   cout << "The original deque d1 is ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1  << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= d1.end( ) - d1.begin( ) ) {
      rotate ( d1.begin( ), d1.begin( ) + 1 , d1.end( ) );
      cout << "After the rotation of a single deque element to the back,\n d1 is   ( " ;
      for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
         cout << *d1Iter1  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

```Output
Vector v1 is ( -3 -2 -1 0 1 2 3 4 5 ).
After rotating, vector v1 is ( 0 1 2 3 4 5 -3 -2 -1 ).
The original deque d1 is ( 0 1 2 3 4 5 ).
After the rotation of a single deque element to the back,
d1 is   ( 1 2 3 4 5 0 ).
After the rotation of a single deque element to the back,
d1 is   ( 2 3 4 5 0 1 ).
After the rotation of a single deque element to the back,
d1 is   ( 3 4 5 0 1 2 ).
After the rotation of a single deque element to the back,
d1 is   ( 4 5 0 1 2 3 ).
After the rotation of a single deque element to the back,
d1 is   ( 5 0 1 2 3 4 ).
After the rotation of a single deque element to the back,
d1 is   ( 0 1 2 3 4 5 ).
```

## <a name="rotate_copy"></a>  rotate_copy

Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.

```cpp
template<class ForwardIterator, class OutputIterator>
OutputIterator rotate_copy(
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last,
    OutputIterator result );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Döndürülecek aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Orta*<br/>
Sınır aralıktaki öğeleri de aralık ilk kısmı ile değiştirilecek olan aralığın ikinci bölümü ilk öğenin konumunu ele alan tanımlama ileriye doğru yineleyici.

_ *Son* döndürülmesi biri son öğeden aralığındaki konumu ele alan ileriye doğru yineleyici.

*Sonuç*<br/>
Hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedef aralıktaki son öğeden sonraki birinci konum ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklığı en fazla ile doğrusal (`last` - `first`) değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_rotate_copy.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main() {
   using namespace std;
   vector <int> v1 , v2 ( 9 );
   deque <int> d1 , d2 ( 6 );
   vector <int>::iterator v1Iter , v2Iter;
   deque<int>::iterator d1Iter , d2Iter;

   int i;
   for ( i = -3 ; i <= 5 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii =0 ; ii <= 5 ; ii++ )
      d1.push_back( ii );

   cout << "Vector v1 is ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
      cout << *v1Iter  << " ";
   cout << ")." << endl;

   rotate_copy ( v1.begin( ), v1.begin( ) + 3 , v1.end( ), v2.begin( ) );
   cout << "After rotating, the vector v1 remains unchanged as:\n v1 = ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
      cout << *v1Iter  << " ";
   cout << ")." << endl;

   cout << "After rotating, the copy of vector v1 in v2 is:\n v2 = ( " ;
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ;v2Iter ++ )
      cout << *v2Iter  << " ";
   cout << ")." << endl;

   cout << "The original deque d1 is ( " ;
   for ( d1Iter = d1.begin( ) ; d1Iter != d1.end( ) ;d1Iter ++ )
      cout << *d1Iter  << " ";
   cout << ")." << endl;

   int iii = 1;
   while ( iii <= d1.end( ) - d1.begin( ) )
   {
      rotate_copy ( d1.begin( ), d1.begin( ) + iii , d1.end( ), d2.begin( ) );
      cout << "After the rotation of a single deque element to the back,\n d2 is   ( " ;
      for ( d2Iter = d2.begin( ) ; d2Iter != d2.end( ) ;d2Iter ++ )
         cout << *d2Iter  << " ";
      cout << ")." << endl;
      iii++;
   }
}
```

## <a name="search"></a>  Arama

Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 search(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class Predicate>
ForwardIterator1 search(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2
    Predicate comp);

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*last1*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*first2*<br/>
Eşleştirilecek aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Soyadı2*<br/>
Eşleştirilecek konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sıra veya eşleşen ilk diziyi ilk öğenin konumunu bulan ileriye doğru yineleyici bir ikili koşula göre belirtilen anlamda eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilmelidir.

Ortalama karmaşıklığı göre Aranan aralığın boyutu ile doğrusal ve en kötü durum karmaşıklığı da doğrusal Aranan dizisi bağlı ise.

### <a name="example"></a>Örnek

```cpp
// alg_search.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is twice the first
bool twice (int elem1, int elem2 )
{
   return 2 * elem1 == elem2;
}

int main() {
   using namespace std;
   vector <int> v1, v2;
   list <int> L1;
   vector <int>::iterator Iter1, Iter2;
   list <int>::iterator L1_Iter, L1_inIter;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int ii;
   for ( ii = 4 ; ii <= 5 ; ii++ )
   {
      L1.push_back( 5 * ii );
   }

   int iii;
   for ( iii = 2 ; iii <= 4 ; iii++ )
   {
      v2.push_back( 10 * iii );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "List L1 = ( " ;
   for ( L1_Iter = L1.begin( ) ; L1_Iter!= L1.end( ) ; L1_Iter++ )
      cout << *L1_Iter << " ";
   cout << ")" << endl;

   cout << "Vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
      cout << ")" << endl;

   // Searching v1 for first match to L1 under identity
   vector <int>::iterator result1;
   result1 = search (v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

   if ( result1 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is at least one match of L1 in v1"
           << "\n and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for a match to L1 under the binary predicate twice
   vector <int>::iterator result2;
   result2 = search  (v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

   if ( result2 == v1.end( ) )
      cout << "There is no match of L1 in v1."
           << endl;
   else
      cout << "There is a sequence of elements in v1 that "
           << "are equivalent\n to those in v2 under the binary "
           << "predicate twice\n and the first one begins at position "
           << result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 0 5 10 15 20 25 )
List L1 = ( 20 25 )
Vector v2 = ( 20 30 40 )
There is at least one match of L1 in v1
and the first one begins at position 4.
There is a sequence of elements in v1 that are equivalent
to those in v2 under the binary predicate twice
and the first one begins at position 2.
```

## <a name="search_n"></a>  search_n

Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.

```cpp
template<class ForwardIterator1, class Diff2, class Type>
ForwardIterator1 search_n(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    Diff2 count,
    const Type& val);

template<class ForwardIterator1, class Diff2, class Type, class BinaryPredicate>
ForwardIterator1 search_n(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    Diff2 count,
    const Type& val,
    BinaryPredicate comp);

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Aranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*last1*<br/>
Aranacak Konum son öğeden bir aralıktaki ileriye doğru yineleyici.

*Sayısı*<br/>
Aranan alt dizi boyutu.

*VAL*<br/>
Aranan dizideki öğelerin değeri.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sıra veya eşleşen ilk diziyi ilk öğenin konumunu bulan ileriye doğru yineleyici bir ikili koşula göre belirtilen anlamda eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

`operator==` Eşleşen bir öğe ile belirtilen değer arasında bir eşdeğerlik ilişkisi işlenenleri arasındaki dayatır gerekir belirlemek için kullanılır.

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklık boyutu ile doğrusal Aranan göre.

### <a name="example"></a>Örnek

```cpp
// alg_search_n.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

// Return whether second element is 1/2 of the first
bool one_half ( int elem1, int elem2 )
{
   return elem1 == 2 * elem2;
}

int main()
{
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( 5  );
   }

   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   for ( i = 0 ; i <= 2 ; i++ )
   {
      v1.push_back( 10  );
   }

   cout << "Vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Searching v1 for first match to (5 5 5) under identity
   vector <int>::iterator result1;
   result1 = search_n ( v1.begin( ), v1.end( ), 3, 5 );

   if ( result1 == v1.end( ) )
      cout << "There is no match for a sequence ( 5 5 5 ) in v1."
           << endl;
   else
      cout << "There is at least one match of a sequence ( 5 5 5 )"
           << "\n in v1 and the first one begins at "
           << "position "<< result1 - v1.begin( ) << "." << endl;

   // Searching v1 for first match to (5 5 5) under one_half
   vector <int>::iterator result2;
   result2 = search_n (v1.begin( ), v1.end( ), 3, 5, one_half );

   if ( result2 == v1.end( ) )
      cout << "There is no match for a sequence ( 5 5 5 ) in v1"
           << " under the equivalence predicate one_half." << endl;
   else
      cout << "There is a match of a sequence ( 5 5 5 ) "
           << "under the equivalence\n predicate one_half "
           << "in v1 and the first one begins at "
           << "position "<< result2 - v1.begin( ) << "." << endl;
}
```

```Output
Vector v1 = ( 0 5 10 15 20 25 5 5 5 0 5 10 15 20 25 10 10 10 )
There is at least one match of a sequence ( 5 5 5 )
in v1 and the first one begins at position 6.
There is a match of a sequence ( 5 5 5 ) under the equivalence
predicate one_half in v1 and the first one begins at position 15.
```

## <a name="set_difference"></a>  set_difference

Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_difference(
    InputIterator1  first1,
    InputIterator1  last1,
    InputIterator2  first2,
    InputIterator2  last2,
    OutputIterator  result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_difference(
    InputIterator1  first1,
    InputIterator1  last1,
    InputIterator2  first2,
    InputIterator2  last2,
    OutputIterator  result,
    BinaryPredicate  comp );
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Birleşik ve iki kaynak aralıktaki fark temsil eden tek bir aralığa sıralanmış ilk iki sıralanmış kaynak aralıktaki ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
Birleşik ve iki kaynak aralıktaki fark temsil eden tek bir aralığa sıralanmış bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa, ele alan bir giriş yineleyici.

*first2*<br/>
Art arda iki saniye içinde ilk öğenin konumunu ele alan giriş yineleyici birleşik ve iki kaynak aralıktaki fark temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

*Soyadı2*<br/>
Geçmiş konumu ele alan giriş yineleyici art arda iki saniye içindeki son öğeden birleşik ve iki kaynak aralıktaki fark temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

*Sonuç*<br/>
İki kaynak aralıktaki iki kaynak aralıktaki fark temsil eden tek bir sıralanmış aralıkta birleşik olduğu hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

İki kaynak aralıktaki farkını gösteren sıralanmış bir hedef aralıktaki son öğeden geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Hedef aralığı ya da kaynak aralıkları çakışmamalı ve ilk kaynak aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralığa her uygulama için bir önkoşul olarak düzenlenmelidir `set_difference` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak.

Her aralık içindeki öğelerin göreli sırasını hedef aralığı korunduğu kalıcı bir işlemdir. Kaynak aralıkları algoritması birleştirme tarafından değiştirilmez.

Giriş Yineleyicilerin değer türlerinin olması daha az daha-karşılaştırılabilir sipariş için iki öğe belirtildiğinde, belirlenemiyor (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Hem kaynak aralıklardaki eşdeğer öğelerin olduğunda, ilk aralıktaki öğeleri hedef aralığında ikinci aralığın öğelerden koyun. Kaynak aralıkları, yinelenen bir öğe içeriyorsa şu şekilde daha ilk kaynak Aralıktaki ikinci, hedef aralığı, oluşumunu bu öğeler kaynak aralıktaki ilk oluşumunu aşan numarasını içerecek daha ikinci kaynak aralıktaki bu öğeleri.

Algoritmanın karmaşıklığı, en fazla 2 ile doğrusal \* (( *last1 - first1*)-( *Soyadı2 - first2*)) - 1 karşılaştırmalar için boş olmayan kaynak aralık.

### <a name="example"></a>Örnek

```cpp
// alg_set_diff.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if (elem1 < 0)
      elem1 = - elem1;
   if (elem2 < 0)
      elem2 = - elem2;
   return elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -1 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 0 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3, Result3;
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a difference in asscending
   // order with the default binary predicate less <int>( )
   Result1 = set_difference ( v1a.begin( ), v1a.end( ),
      v1b.begin( ), v1b.end( ), v1.begin( ) );
   cout << "Set_difference of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a difference in descending
   // order specify binary predicate greater<int>( )
   Result2 = set_difference ( v2a.begin( ), v2a.end( ),
      v2b.begin( ), v2b.end( ),v2.begin( ), greater <int>( ) );
   cout << "Set_difference of source ranges with binary"
        << "predicate greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a difference applying a user
   // defined binary predicate mod_lesser
   Result3 = set_difference (  v3a.begin( ), v3a.end( ),
      v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
   cout << "Set_difference of source ranges with binary "
        << "predicate mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_intersection"></a>  set_intersection

Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Birleşik ve iki kaynak aralıktaki kesişimi temsil eden tek bir aralığa sıralanmış ilk iki sıralanmış kaynak aralıktaki ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
Birleşik ve iki kaynak aralıktaki kesişimi temsil eden tek bir aralığa sıralanmış bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa, ele alan bir giriş yineleyici.

*first2*<br/>
Art arda iki saniye içinde ilk öğenin konumunu ele alan giriş yineleyici birleşik ve iki kaynak aralıktaki kesişimi temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

*Soyadı2*<br/>
Geçmiş konumu ele alan giriş yineleyici art arda iki saniye içindeki son öğeden birleşik ve iki kaynak aralıktaki kesişimi temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

**_** *Sonucu* aralıkları iki kaynak yeri hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici olan iki kaynak kesişimi temsil eden tek bir sıralanmış aralıkta birleşik için aralıkları.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

İki kaynak aralıktaki kesişimi temsil eden sıralanmış bir hedef aralıktaki son öğeyi geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Hedef aralığı ya da kaynak aralıkları çakışmamalı ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralık her uygulama olarak aynı sıralamaya uygun birleştirme algoritmasının bir önkoşulu olarak düzenlenmiş olması gerekir, birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak olan.

Her aralık içindeki öğelerin göreli sırasını hedef aralığı korunduğu kalıcı bir işlemdir. Kaynak aralıkları algoritması tarafından değiştirilmez.

Giriş Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Hem kaynak aralıklardaki eşdeğer öğelerin olduğunda, ilk aralıktaki öğeleri hedef aralığında ikinci aralığın öğelerden koyun. Kaynak aralıkları yinelenen bir öğe içeriyorsa, hedef aralığı sayısı iki kaynak aralıklardaki oluşan bu öğeleri içerir.

Algoritmanın karmaşıklığı, en fazla 2 ile doğrusal \* (( *last1 - first1*) + ( *Soyadı2 - first2*)) - 1 karşılaştırmalar için boş olmayan kaynak aralık.

### <a name="example"></a>Örnek

```cpp
// alg_set_intersection.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>   // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main() {
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less than ordering
   int i;
   for ( i = -1 ; i <= 3 ; i++ )
      v1a.push_back( i );

   int ii;
   for ( ii =-3 ; ii <= 1 ; ii++ )
      v1b.push_back( ii );

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

   cout << "Original vector v2a with range sorted by the\n "
        << "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        << "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
   vector <int>::iterator Iter3a,  Iter3b, Iter3, Result3;
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
           <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into an intersection in asscending order with the
   // default binary predicate less <int>( )
   Result1 = set_intersection ( v1a.begin( ), v1a.end( ),
      v1b.begin( ), v1b.end( ), v1.begin( ) );
   cout << "Intersection of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; ++Iter1 )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into an intersection in descending order, specify
   // binary predicate greater<int>( )
   Result2 = set_intersection ( v2a.begin( ), v2a.end( ),
      v2b.begin( ), v2b.end( ),v2.begin( ), greater <int>( ) );
   cout << "Intersection of source ranges with binary predicate"
        << " greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; ++Iter2 )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into an intersection applying a user-defined
   // binary predicate mod_lesser
   Result3 = set_intersection ( v3a.begin( ), v3a.end( ),
      v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
   cout << "Intersection of source ranges with binary predicate "
        << "mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; ++Iter3 )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_symmetric_difference"></a>  set_symmetric_difference

İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Birleşik ve iki kaynak aralıktaki simetrik fark temsil eden tek bir aralığa sıralanmış ilk iki sıralanmış kaynak aralıktaki ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
Birleşik ve iki kaynak aralıktaki simetrik fark temsil eden tek bir aralığa sıralanmış bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa, ele alan bir giriş yineleyici.

*first2*<br/>
Art arda iki saniye içinde ilk öğenin konumunu ele alan giriş yineleyici birleşik ve iki kaynak aralıktaki simetrik fark temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

*Soyadı2*<br/>
Geçmiş konumu ele alan giriş yineleyici art arda iki saniye içindeki son öğeden birleşik ve iki kaynak aralıktaki simetrik fark temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

**_** *Sonucu* aralıkları iki kaynak yeri hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici iki simetrik fark temsil eden tek bir sıralanmış aralıkta birleşik üzeresiniz Kaynak aralıkları.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Bir önceki öğenin konumunu son öğeyi temsil eden iki kaynak aralıktaki simetrik fark sıralanmış bir hedef aralıktaki ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Hedef aralığı ya da kaynak aralıkları çakışmamalı ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralığa her uygulama için bir önkoşul olarak düzenlenmelidir `merge*` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak.

Her aralık içindeki öğelerin göreli sırasını hedef aralığı korunduğu kalıcı bir işlemdir. Kaynak aralıkları algoritması birleştirme tarafından değiştirilmez.

Giriş Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Hem kaynak aralıklardaki eşdeğer öğelerin olduğunda, ilk aralıktaki öğeleri hedef aralığında ikinci aralığın öğelerden koyun. Kaynak aralıkları yinelenen bir öğe içeriyorsa, hedef aralığı kaynak aralıktaki birinde söz konusu öğelerin oluşumları aşıyor oluşumları ikinci kaynağında söz konusu öğelerin sayının mutlak değerini ardından içerecek Aralık.

Algoritmanın karmaşıklığı, en fazla 2 ile doğrusal \* ((*last1 - first1*)-(*Soyadı2 - first2*)) - 1 karşılaştırmalar için boş olmayan kaynak aralık.

### <a name="example"></a>Örnek

```cpp
// alg_set_sym_diff.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser (int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a,  Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less-than ordering
   int i;
   for ( i = -1 ; i <= 4 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 0 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) ,  v2 ( v1 );
   vector <int>::iterator Iter2a, Iter2b, Iter2, Result2;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a, Iter3b, Iter3, Result3;
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference in ascending
   // order with the default binary predicate less <int>( )
   Result1 = set_symmetric_difference ( v1a.begin( ), v1a.end( ),
      v1b.begin( ), v1b.end( ), v1.begin( ) );
   cout << "Set_symmetric_difference of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference in descending
   // order, specify binary predicate greater<int>( )
   Result2 = set_symmetric_difference ( v2a.begin( ), v2a.end( ),
      v2b.begin( ), v2b.end( ),v2.begin( ), greater <int>( ) );
   cout << "Set_symmetric_difference of source ranges with binary"
        << "predicate greater specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a symmetric difference applying a user
   // defined binary predicate mod_lesser
   Result3 = set_symmetric_difference ( v3a.begin( ), v3a.end( ),
      v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
   cout << "Set_symmetric_difference of source ranges with binary "
        << "predicate mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="set_union"></a>  set_union

İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryPredicate>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Birleşik ve iki kaynak aralıktaki birleşimi temsil eden tek bir aralığa sıralanmış ilk iki sıralanmış kaynak aralıktaki ilk öğenin konumu ele alan giriş yineleyici.

*last1*<br/>
Birleşik ve iki kaynak aralıktaki birleşimi temsil eden tek bir aralığa sıralanmış bir önceki öğenin konumunu son öğeden ilk iki sıralanmış kaynak aralığa, ele alan bir giriş yineleyici.

*first2*<br/>
Art arda iki saniye içinde ilk öğenin konumunu ele alan giriş yineleyici birleşik ve iki kaynak aralıktaki birleşimi temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

*Soyadı2*<br/>
Geçmiş konumu ele alan giriş yineleyici art arda iki saniye içindeki son öğeden birleşik ve iki kaynak aralıktaki birleşimi temsil eden tek bir aralığa sıralanmış kaynak aralığa sıralanır.

**_** *Sonucu* aralıkları iki kaynak yeri hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici iki kaynak aralıktaki birleşimi temsil eden tek bir sıralanmış aralıkta birleşik üzeresiniz.

*Comp*<br/>
Bir öğenin diğerinden daha büyük olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürmelidir **true** ilk öğe olduğunda ikinci öğe küçüktür ve **false** Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

İki kaynak aralıktaki birleşimi temsil eden sıralanmış bir hedef aralıktaki son öğeyi geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalıdır; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Hedef aralığı ya da kaynak aralıkları çakışmamalı ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralığa her uygulama için bir önkoşul olarak düzenlenmelidir `merge` olarak aynı sıralamaya uygun şekilde algoritmasıdır birleştirilmiş aralıkları Sıralama algoritması tarafından kullanılacak.

Her aralık içindeki öğelerin göreli sırasını hedef aralığı korunduğu kalıcı bir işlemdir. Kaynak aralıkları algoritması tarafından değiştirilmez `merge`.

Giriş Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Hem kaynak aralıklardaki eşdeğer öğelerin olduğunda, ilk aralıktaki öğeleri hedef aralığında ikinci aralığın öğelerden koyun. Kaynak aralıkları yinelenen bir öğe içeriyorsa, hedef aralığı sayısı iki kaynak aralıklardaki oluşan bu öğeleri içerir.

Algoritmanın karmaşıklığı, en fazla 2 ile doğrusal \* (( *last1 - first1*)-( *Soyadı2 - first2*)) - 1 karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_set_union.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 < elem2;
}

int main()
{
   using namespace std;
   vector <int> v1a, v1b, v1 ( 12 );
   vector <int>::iterator Iter1a, Iter1b, Iter1, Result1;

   // Constructing vectors v1a & v1b with default less than ordering
   int i;
   for ( i = -1 ; i <= 3 ; i++ )
   {
      v1a.push_back(  i );
   }

   int ii;
   for ( ii =-3 ; ii <= 1 ; ii++ )
   {
      v1b.push_back(  ii  );
   }

   cout << "Original vector v1a with range sorted by the\n "
        <<  "binary predicate less than is  v1a = ( " ;
   for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
      cout << *Iter1a << " ";
   cout << ")." << endl;

   cout << "Original vector v1b with range sorted by the\n "
        <<  "binary predicate less than is  v1b = ( " ;
   for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
      cout << *Iter1b << " ";
   cout << ")." << endl;

   // Constructing vectors v2a & v2b with ranges sorted by greater
   vector <int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
   vector <int>::iterator Iter2a,  Iter2b, Iter2, Result2;
   sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
   sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

   cout << "Original vector v2a with range sorted by the\n "
        <<  "binary predicate greater is   v2a =  ( " ;
   for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
      cout << *Iter2a << " ";
   cout << ")." << endl;

   cout << "Original vector v2b with range sorted by the\n "
        <<  "binary predicate greater is   v2b =  ( " ;
   for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
      cout << *Iter2b << " ";
   cout << ")." << endl;

   // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
   vector <int> v3a ( v1a ), v3b ( v1b ) ,  v3 ( v1 );
   vector <int>::iterator Iter3a, Iter3b, Iter3, Result3;
   sort ( v3a.begin( ), v3a.end( ), mod_lesser );
   sort ( v3b.begin( ), v3b.end( ), mod_lesser  );

   cout << "Original vector v3a with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3a =  ( " ;
   for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
      cout << *Iter3a << " ";
   cout << ")." << endl;

   cout << "Original vector v3b with range sorted by the\n "
        <<  "binary predicate mod_lesser is   v3b =  ( " ;
   for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
      cout << *Iter3b << " ";
   cout << ")." << endl;

   // To combine into a union in ascending order with the default
    // binary predicate less <int>( )
   Result1 = set_union ( v1a.begin( ), v1a.end( ),
      v1b.begin( ), v1b.end( ), v1.begin( ) );
   cout << "Union of source ranges with default order,"
        << "\n vector v1mod =  ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // To combine into a union in descending order, specify binary
   // predicate greater<int>( )
   Result2 = set_union (  v2a.begin( ), v2a.end( ),
      v2b.begin( ), v2b.end( ),v2.begin( ), greater <int>( ) );
   cout << "Union of source ranges with binary predicate greater "
        << "specified,\n vector v2mod  = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // To combine into a union applying a user-defined
   // binary predicate mod_lesser
   Result3 = set_union ( v3a.begin( ), v3a.end( ),
      v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
   cout << "Union of source ranges with binary predicate "
        << "mod_lesser specified,\n vector v3mod  = ( " ; ;
   for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

## <a name="shuffle"></a>  Std::Shuffle

Bir rastgele sayı üreticisinin kullanarak verilen bir aralıktaki öğeleri seçeneği (düzenlemelerinin).

```cpp
template<class RandomAccessIterator, class UniformRandomNumberGenerator>
void shuffle(RandomAccessIterator first,
    RandomAccessIterator last,
    UniformRandomNumberGenerator&& gen);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Karıştırılmış (dahil) için bir yineleyici aralıktaki ilk öğeyi. Gereksinimlerini karşılamalıdır `RandomAccessIterator` ve `ValueSwappable`.

*Son*<br/>
Karıştırılmış, özel bir yineleyici aralıktaki son öğeyi için. Gereksinimlerini karşılamalıdır `RandomAccessIterator` ve `ValueSwappable`.

*Genel*<br/>
Rastgele sayı üreticisinin, `shuffle()` işlem için işlevi kullanır. Gereksinimlerini karşılamalıdır bir `UniformRandomNumberGenerator`.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve kullandığı bir kod örneği için `shuffle()`, bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="sort"></a>  Sıralama

Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class RandomAccessIterator>
   void sort(
      RandomAccessIterator first,
      RandomAccessIterator last);

template<class RandomAccessIterator, class Predicate>
   void sort(
      RandomAccessIterator first,
      RandomAccessIterator last,
      Predicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir rasgele erişim yineleyicisi.

*Son*<br/>
Sıralanacak aralığın son öğesinde geçmiş konumu ele alan bir rasgele erişim yineleyicisi.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. Bu ikili koşulu, iki bağımsız değişkeni alır ve döndürür **true** iki bağımsız değişken sıradaysa ve **false** Aksi takdirde. Bu bir karşılaştırıcı işlevi, katı bir zayıf çiftlerini dizisindeki öğelerin sıralama dayatır gerekir. Daha fazla bilgi için [algoritmaları](../standard-library/algorithms.md).

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Öğeleri eşdeğerdir, ancak mutlaka eşittir, hiçbiri diğerinden olduğu. `sort` Algoritması kararlı değilse ve bu nedenle öğeleri, eşdeğer öğelerin göreli sıralamasını korunur olduğunu garanti etmez. Algoritma `stable_sort` bu özgün sıralamasını koruması.

Sıralama karmaşıklığı ortalamasıdır *O*( *N* günlük *N*), burada *N* =  *son - ilk*.

### <a name="example"></a>Örnek

```cpp
// alg_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater ( int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   int ii;
   for ( ii = 0 ; ii <= 5 ; ii++ )
   {
      v1.push_back( 2 * ii + 1 );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order. specify binary predicate
   sort( v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "Resorted (greater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   sort( v1.begin( ), v1.end( ), UDgreater );
   cout << "Resorted (UDgreater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 0 2 4 6 8 10 1 3 5 7 9 11 )
Sorted vector v1 = ( 0 1 2 3 4 5 6 7 8 9 10 11 )
Resorted (greater) vector v1 = ( 11 10 9 8 7 6 5 4 3 2 1 0 )
Resorted (UDgreater) vector v1 = ( 11 10 9 8 7 6 5 4 3 2 1 0 )
```

## <a name="sort_heap"></a>  sort_heap

Bir yığını sıralanmış bir aralığa dönüştürür.

```cpp
template<class RandomAccessIterator>
   void sort_heap(
      RandomAccessIterator first,
      RandomAccessIterator last);

template<class RandomAccessIterator, class Predicate>
   void sort_heap(
      RandomAccessIterator first,
      RandomAccessIterator last,
      Predicate comp);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Hedef yığınındaki ilk öğenin konumunu bulan bir rastgele erişim yineleyicisi.

*Son*<br/>
Hedef yığın içindeki son öğeden sonraki birinci konum ele alan bir rastgele erişim yineleyicisi.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Yığınlar iki özelliğe sahiptir:

- İlk öğe her zaman daha büyüktür.

- Öğeleri eklenebilir veya Logaritmik süre kaldırıldı.

Bu algoritma, aralığın uygulandığı, sonra uygulamanın bir yığın artık değil.

Eşdeğer öğelerin göreli sırasını değil gerekmeyen korunduğu için bu tutarlı bir sıralama değildir.

Yığınlar öncelikli kuyruklardaki uygulamak için ideal bir yöntem olduğunu ve C++ Standart Kitaplığı kapsayıcı bağdaştırıcısı uygulamasında kullanılan [priority_queue sınıfı](../standard-library/priority-queue-class.md).

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Karmaşıklığı en fazla olan *N* günlük *N*burada *N* = ( *- Soyadı*).

### <a name="example"></a>Örnek

```cpp
// alg_sort_heap.cpp
// compile with: /EHsc
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>
#include <string>
#include <vector>
using namespace std;

void print(const string& s, const vector<int>& v) {
    cout << s << ": ( ";

    for (auto i = v.begin(); i != v.end(); ++i) {
        cout << *i << " ";
    }

    cout << ")" << endl;
}

int main() {
    vector<int> v;
    for (int i = 1; i <= 9; ++i) {
        v.push_back(i);
    }
    print("Initially", v);

    random_shuffle(v.begin(), v.end());
    print("After random_shuffle", v);

    make_heap(v.begin(), v.end());
    print("     After make_heap", v);

    sort_heap(v.begin(), v.end());
    print("     After sort_heap", v);

    random_shuffle(v.begin(), v.end());
    print("             After random_shuffle", v);

    make_heap(v.begin(), v.end(), greater<int>());
    print("After make_heap with greater<int>", v);

    sort_heap(v.begin(), v.end(), greater<int>());
    print("After sort_heap with greater<int>", v);
}
```

## <a name="stable_partition"></a>  stable_partition

Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

```cpp
template<class BidirectionalIterator, class Predicate>
BidirectionalIterator stable_partition(
    BidirectionalIterator first,
    BidirectionalIterator last,
    Predicate pred );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Bölümlenecek aralıktaki ilk öğenin konumunu bulan bir çift yönlü yineleyici.

*Son*<br/>
Bölümlenecek aralığın son öğesinde geçmiş konumu ele alan bir çift yönlü yineleyici.

*_Pred*<br/>
Bir öğe sınıflandırılmaya ise karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. Bir koşulu, tek bir bağımsız değişken alır ve döndürür **true** veya **false**.

### <a name="return-value"></a>Dönüş Değeri

Koşul durumu değil karşılamak için aralıktaki ilk öğenin konumunu bulan bir çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Öğeleri *bir* ve *b* eşdeğerdir, ancak mutlaka, her iki eşit *çekme isteği* ( *bir*, *b*) false'tur ve *çekme isteği* ( *b*, *bir*) false ise, burada *çekme isteği* parametre tarafından belirtilen bir koşuldur. `stable_ partition` Algoritması kararlı ve öğeleri, eşdeğer öğelerin göreli sıralamasını korunur, garanti eder. Algoritma `partition` mu mutlaka Koru bu özgün sıralama.

### <a name="example"></a>Örnek

```cpp
// alg_stable_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value ) {
   return value > 5;
}

int main() {
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, result;

   int i;
   for ( i = 0 ; i <= 10 ; i++ )
      v1.push_back( i );

   int ii;
   for ( ii = 0 ; ii <= 4 ; ii++ )
      v1.push_back( 5 );

   random_shuffle(v1.begin( ), v1.end( ) );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Partition the range with predicate greater10
   result = stable_partition (v1.begin( ), v1.end( ), greater5 );
   cout << "The partitioned set of elements in v1 is:\n ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "The first element in v1 to fail to satisfy the"
        << "\n predicate greater5 is: " << *result << "." << endl;
}
```

## <a name="stable_sort"></a>  stable_sort

Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class BidirectionalIterator>
void stable_sort( BidirectionalIterator first, BidirectionalIterator last );

template<class BidirectionalIterator, class BinaryPredicate>
void stable_sort(
    BidirectionalIterator first,
    BidirectionalIterator last,
    BinaryPredicate comp );

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Sıralanacak aralıktaki ilk öğenin konumunu bulan bir çift yönlü yineleyici.

*Son*<br/>
Sıralanacak aralığın son öğesinde geçmiş konumu ele alan bir çift yönlü yineleyici.

*Comp*<br/>
Sıralama, ardışık öğeleri tarafından karşılanması için karşılaştırma ölçütü tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir.

Öğeleri eşdeğerdir, ancak mutlaka eşittir, hiçbiri diğerinden olduğu. `sort` Algoritması kararlı ve öğeleri, eşdeğer öğelerin göreli sıralamasını korunur, garanti eder.

Çalışma zamanı karmaşıklığı `stable_sort` kullanılabilir bellek miktarına bağlıdır ancak (yeterli bellek verilir) en iyi durumda *O*( *N* günlük *N*) ve en kötü durumu olan *O*( *N* (günlük *N* ) 2), burada *N* =  *- soyadı.* Genellikle, `sort` algoritmasıdır kıyasla önemli ölçüde daha hızlı `stable_sort`.

### <a name="example"></a>Örnek

```cpp
// alg_stable_sort.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // For greater<int>( )
#include <iostream>

// Return whether first element is greater than the second
bool UDgreater (int elem1, int elem2 )
{
   return elem1 > elem2;
}

int main()
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 2 * i  );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   stable_sort(v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order, specify binary predicate
   stable_sort(v1.begin( ), v1.end( ), greater<int>( ) );
   cout << "Resorted (greater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // A user-defined (UD) binary predicate can also be used
   stable_sort(v1.begin( ), v1.end( ), UDgreater );
   cout << "Resorted (UDgreater) vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 0 2 4 6 8 10 0 2 4 6 8 10 )
Sorted vector v1 = ( 0 0 2 2 4 4 6 6 8 8 10 10 )
Resorted (greater) vector v1 = ( 10 10 8 8 6 6 4 4 2 2 0 0 )
Resorted (UDgreater) vector v1 = ( 10 10 8 8 6 6 4 4 2 2 0 0 )
```

## <a name="swap"></a>  değiştirme

Geçersiz kılma ilk iki nesnenin değerlerini birbiriyle değiştirir. İkinci geçersiz kılma değerleri iki nesne dizileri arasında değiş tokuş eder.

```cpp
template<class Type>
   void swap(
      Type& left,
      Type& right);
template<class Type, size_t N>
   void swap(
      Type (& left)[N],
      Type (& right)[N]);\r

```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlk geçersiz kılma için değiştirilen içeriği sağlamak için ilk nesne. İkinci geçersiz kılma için ilk içeriğinin değiş tokuş için nesneler dizisi.

*sağ*<br/>
İlk geçersiz kılma için değiştirilen içeriği sağlamak için ikinci nesne. İkinci için geçersiz kılma, ikinci içeriğini değiş tokuş için nesneleri dizisi.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme tek nesneler üzerinde çalışmak üzere tasarlanmıştır. İkinci aşırı yükleme iki diziler arasında nesneleri içeriğini değiştirir.

### <a name="example"></a>Örnek

```cpp
// alg_swap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
   using namespace std;
   vector <int> v1, v2;
   vector <int>::iterator Iter1, Iter2, result;

   for ( int i = 0 ; i <= 10 ; i++ )
   {
      v1.push_back( i );
   }

   for ( int ii = 0 ; ii <= 4 ; ii++ )
   {
      v2.push_back( 5 );
   }

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   swap( v1, v2 );

   cout << "Vector v1 is ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   cout << "Vector v2 is ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 0 1 2 3 4 5 6 7 8 9 10 ).
Vector v2 is ( 5 5 5 5 5 ).
Vector v1 is ( 5 5 5 5 5 ).
Vector v2 is ( 0 1 2 3 4 5 6 7 8 9 10 ).
```

## <a name="swap_ranges"></a>  swap_ranges

Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 swap_ranges(
   ForwardIterator1 first1,
   ForwardIterator1 last1,
   ForwardIterator2 first2 );

```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Değiştirilecek öğeleri olan ilk aralığının ilk konuma işaret eden bir ileriye doğru yineleyici.

*last1*<br/>
Bir öncekine değiştirilecek öğeleri olan ilk aralığın son konumunu işaret eden bir ileriye doğru yineleyici.

*first2*<br/>
Değiştirilecek öğeleri olan ikinci aralığının ilk konuma işaret eden bir ileriye doğru yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Bir öncekine değiştirilecek öğeleri olan ikinci aralığın son konumunu işaret eden bir ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilmelidir. Aralığın ilk büyük olacak şekilde ikinci aralığı vardır.

Karmaşıklığı ile doğrusal *last1* - *first1* takasları gerçekleştirilir. Öğeleri aynı türde kapsayıcılar takas varsa, bunları `swap` bu kapsayıcı üye işlevi kullanılmalıdır, üye işlevi genellikle sabit karmaşası olduğundan.

### <a name="example"></a>Örnek

```cpp
// alg_swap_ranges.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main()
{
   using namespace std;
   vector <int> v1;
   deque <int> d1;
   vector <int>::iterator v1Iter1;
   deque<int>::iterator d1Iter1;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( i );
   }

   int ii;
   for ( ii =4 ; ii <= 9 ; ii++ )
   {
      d1.push_back( 6 );
   }

   cout << "Vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1  << " ";
   cout << ")." << endl;

   cout << "Deque d1 is  ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1  << " ";
   cout << ")." << endl;

   swap_ranges ( v1.begin( ), v1.end( ), d1.begin( ) );

   cout << "After the swap_range, vector v1 is ( " ;
   for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
      cout << *v1Iter1 << " ";
   cout << ")." << endl;

   cout << "After the swap_range deque d1 is   ( " ;
   for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
      cout << *d1Iter1 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 0 1 2 3 4 5 ).
Deque d1 is  ( 6 6 6 6 6 6 ).
After the swap_range, vector v1 is ( 6 6 6 6 6 6 ).
After the swap_range deque d1 is   ( 0 1 2 3 4 5 ).
```

## <a name="transform"></a>  Dönüştürme

Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator, class UnaryFunction>
OutputIterator transform(
    InputIterator first1,
    InputIterator last1,
    OutputIterator result,
    UnaryFunction func );

template<class InputIterator1, class InputIterator2, class OutputIterator, class BinaryFunction>
OutputIterator transform(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    OutputIterator result,
    BinaryFunction func );
```

### <a name="parameters"></a>Parametreler

*first1*<br/>
Üzerinde yapılacak ilk kaynak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*last1*<br/>
İşlenemeyen ilk kaynak aralıktaki son öğeden sonraki birinci konum ele alan giriş yineleyici.

*first2*<br/>
Üzerinde yapılacak ikinci kaynak aralıktaki ilk öğenin konumunu ele alan giriş yineleyici.

*Sonuç*<br/>
Hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici.

*_Func*<br/>
Kullanıcı tanımlı tekli ilk kaynak aralıktaki her öğeye uygulanan algoritması ilk sürümünde kullanılan nesnesi veya ikili, ileriye doğru sırada uygulanan algoritma ikinci sürümünde kullanılan bir kullanıcı tanımlı (UD) ikili fonksiyon nesnesi işlevi , iki kaynak aralıkları.

### <a name="return-value"></a>Dönüş Değeri

İşlev nesnesi tarafından dönüştürülmüş çıktı öğeleri alan hedef aralığın son öğesinde geçmiş konumu ele alan çıkış yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve her dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir. Hedef aralığı dönüştürülmüş kaynak aralığı içerecek kadar büyük olmalıdır.

Varsa *sonucu* eşit olarak ayarlanır *first1* algoritma ilk sürümünde, ardından kaynak ve hedef aralıklar aynı olacaktır ve sıra yerinde değiştirilecek. Ancak *sonucu* aralık içinde bir konuma adres değil [`first1` + 1, `last1`).

Karmaşıklığı en fazla ile doğrusal (`last1` - `first1`) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_transform.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

// The function object multiplies an element by a Factor
template <class Type>
class MultValue
{
   private:
      Type Factor;   // The value to multiply by
   public:
      // Constructor initializes the value to multiply by
      MultValue ( const Type& val ) : Factor ( val ) {
      }

      // The function call for the element to be multiplied
      Type operator( ) ( Type& elem ) const
      {
         return elem * Factor;
      }
};

int main()
{
   using namespace std;
   vector <int> v1, v2 ( 7 ), v3 ( 7 );
   vector <int>::iterator Iter1, Iter2 , Iter3;

   // Constructing vector v1
   int i;
   for ( i = -4 ; i <= 2 ; i++ )
   {
      v1.push_back(  i );
   }

   cout << "Original vector  v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Modifying the vector v1 in place
   transform (v1.begin( ), v1.end( ), v1.begin( ), MultValue<int> ( 2 ) );
   cout << "The elements of the vector v1 multiplied by 2 in place gives:"
        << "\n v1mod = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")." << endl;

   // Using transform to multiply each element by a factor of 5
   transform ( v1.begin( ), v1.end( ), v2.begin( ), MultValue<int> ( 5 ) );

   cout << "Multiplying the elements of the vector v1mod\n "
        <<  "by the factor 5 & copying to v2 gives:\n v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")." << endl;

   // The second version of transform used to multiply the
   // elements of the vectors v1mod & v2 pairwise
   transform ( v1.begin( ), v1.end( ),  v2.begin( ), v3.begin( ),
      multiplies <int>( ) );

   cout << "Multiplying elements of the vectors v1mod and v2 pairwise "
        <<  "gives:\n v3 = ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")." << endl;
}
```

```Output
Original vector  v1 = ( -4 -3 -2 -1 0 1 2 ).
The elements of the vector v1 multiplied by 2 in place gives:
v1mod = ( -8 -6 -4 -2 0 2 4 ).
Multiplying the elements of the vector v1mod
by the factor 5 & copying to v2 gives:
v2 = ( -40 -30 -20 -10 0 10 20 ).
Multiplying elements of the vectors v1mod and v2 pairwise gives:
v3 = ( 320 180 80 20 0 20 80 ).
```

## <a name="unique"></a>  benzersiz

Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.

```cpp
template<class ForwardIterator>
   ForwardIterator unique(
      ForwardIterator first,
      ForwardIterator last);

template<class ForwardIterator, class Predicate>
   ForwardIterator unique(
      ForwardIterator first,
      ForwardIterator last,
      Predicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Yinelenen kaldırma taranacak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Bir son öğeden aralığındaki konumu için yinelenen kaldırma taranacak bulan ileriye doğru yineleyici.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Bir önceki öğenin konumunu kaldırılmaz son öğeyi ele alan ileriye doğru yineleyici ardışık yinelemelere içeren değiştirilmiş bir dizi yeni sonuna.

### <a name="remarks"></a>Açıklamalar

Her iki biçimi algoritmasının ikinci yinelenen eşit öğelerin art arda çifti kaldırın.

Böylece silinmeyen öğelerin göreli sırasını değiştirilmez algoritmasının kalıcı bir işlemdir.

Başvurulan aralık geçerli olmalı; Tüm İşaretçiler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilmelidir. Dizideki öğelerin sayısı o algoritması tarafından değiştirilmez `unique` ve öğeler değiştirilmiş dizinin sonundan tekrar başvurulabilir ancak belirtilmedi.

Doğrusal gerektiren karmaşıklığı (`last` - `first`) - 1 karşılaştırmalar.

Liste daha verimli bir üye işlevi "benzersiz" daha iyi gerçekleştirebilir sağlar.

Bu algoritmalar ilişkilendirilebilir bir kapsayıcı üzerinde kullanılamaz.

### <a name="example"></a>Örnek

```cpp
// alg_unique.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>

using namespace std;

// Return whether modulus of elem1 is equal to modulus of elem2
bool mod_equal ( int elem1, int elem2 )
{
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 == elem2;
};

int main()
{
   vector <int> v1;
   vector <int>::iterator v1_Iter1, v1_Iter2, v1_Iter3,
         v1_NewEnd1, v1_NewEnd2, v1_NewEnd3;

   int i;
   for ( i = 0 ; i <= 3 ; i++ )
   {
      v1.push_back( 5 );
      v1.push_back( -5 );
   }

   int ii;
   for ( ii = 0 ; ii <= 3 ; ii++ )
   {
      v1.push_back( 4 );
   }
   v1.push_back( 7 );

   cout << "Vector v1 is ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1.end( ) ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Remove consecutive duplicates
   v1_NewEnd1 = unique ( v1.begin( ), v1.end( ) );

   cout << "Removing adjacent duplicates from vector v1 gives\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1_NewEnd1 ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Remove consecutive duplicates under the binary prediate mod_equals
   v1_NewEnd2 = unique ( v1.begin( ), v1_NewEnd1 , mod_equal );

   cout << "Removing adjacent duplicates from vector v1 under the\n "
        << " binary predicate mod_equal gives\n ( " ;
   for ( v1_Iter2 = v1.begin( ) ; v1_Iter2 != v1_NewEnd2 ; v1_Iter2++ )
      cout << *v1_Iter2 << " ";
   cout << ")." << endl;

   // Remove elements if preceded by an element that was greater
   v1_NewEnd3 = unique ( v1.begin( ), v1_NewEnd2, greater<int>( ) );

   cout << "Removing adjacent elements satisfying the binary\n "
        << " predicate mod_equal from vector v1 gives ( " ;
   for ( v1_Iter3 = v1.begin( ) ; v1_Iter3 != v1_NewEnd3 ; v1_Iter3++ )
      cout << *v1_Iter3 << " ";
   cout << ")." << endl;
}
```

```Output
Vector v1 is ( 5 -5 5 -5 5 -5 5 -5 4 4 4 4 7 ).
Removing adjacent duplicates from vector v1 gives
( 5 -5 5 -5 5 -5 5 -5 4 7 ).
Removing adjacent duplicates from vector v1 under the
  binary predicate mod_equal gives
( 5 4 7 ).
Removing adjacent elements satisfying the binary
  predicate mod_equal from vector v1 gives ( 5 7 ).
```

## <a name="unique_copy"></a>  unique_copy

Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator unique_copy( InputIterator first,
    InputIterator last,
    OutputIterator result );

template<class InputIterator, class OutputIterator, class BinaryPredicate>
OutputIterator unique_copy( InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryPredicate comp );
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Kopyalanacak kaynak aralıktaki ilk öğenin konumunu bulan ileriye doğru yineleyici.

*Son*<br/>
Kopyalanacak kaynak aralıktaki son öğeden sonraki birinci konum ele alan ileriye doğru yineleyici.

*Sonuç*<br/>
Birbirini izleyen yinelemeler ile kopyayı alan hedef aralıktaki ilk öğenin konumunu bulan çıktı yineleyici kaldırıldı.

*Comp*<br/>
Gerçekleştirilecek iki öğe varsa karşılanması koşul tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi olarak eşdeğer. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Birbirini izleyen yinelemeler ile kopyayı alan hedef aralığın son öğesinde geçmiş konumu ele alan çıkış yineleyici kaldırıldı.

### <a name="remarks"></a>Açıklamalar

Her iki biçimi algoritmasının ikinci yinelenen eşit öğelerin art arda çifti kaldırın.

Böylece silinmeyen öğelerin göreli sırasını değiştirilmez algoritmasının kalıcı bir işlemdir.

Başvurulan aralıkların geçerli olması gerekir; Tüm İşaretçiler tekrar başvurulabilir olmalı ve bir dizi içinde son konuma ilk konumdan erişilebilmelidir.

Doğrusal gerektiren karmaşıklığı (`last` - `first`) karşılaştırmalar.

### <a name="example"></a>Örnek

```cpp
// alg_unique_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>
#include <ostream>

using namespace std;

// Return whether modulus of elem1 is equal to modulus of elem2
bool mod_equal ( int elem1, int elem2 ) {
   if ( elem1 < 0 )
      elem1 = - elem1;
   if ( elem2 < 0 )
      elem2 = - elem2;
   return elem1 == elem2;
};

int main() {
   vector <int> v1;
   vector <int>::iterator v1_Iter1, v1_Iter2,
         v1_NewEnd1, v1_NewEnd2;

   int i;
   for ( i = 0 ; i <= 1 ; i++ ) {
      v1.push_back( 5 );
      v1.push_back( -5 );
   }

   int ii;
   for ( ii = 0 ; ii <= 2 ; ii++ )
      v1.push_back( 4 );
   v1.push_back( 7 );

   int iii;
   for ( iii = 0 ; iii <= 5 ; iii++ )
      v1.push_back( 10 );

   cout << "Vector v1 is\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1.end( ) ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   // Copy first half to second, removing consecutive duplicates
   v1_NewEnd1 = unique_copy ( v1.begin( ), v1.begin( ) + 8, v1.begin( ) + 8 );

   cout << "Copying the first half of the vector to the second half\n "
        << "while removing adjacent duplicates gives\n ( " ;
   for ( v1_Iter1 = v1.begin( ) ; v1_Iter1 != v1_NewEnd1 ; v1_Iter1++ )
      cout << *v1_Iter1 << " ";
   cout << ")." << endl;

   int iv;
   for ( iv = 0 ; iv <= 7 ; iv++ )
      v1.push_back( 10 );

   // Remove consecutive duplicates under the binary prediate mod_equals
   v1_NewEnd2 = unique_copy ( v1.begin( ), v1.begin( ) + 14,
      v1.begin( ) + 14 , mod_equal );

   cout << "Copying the first half of the vector to the second half\n "
        << " removing adjacent duplicates under mod_equals gives\n ( " ;
   for ( v1_Iter2 = v1.begin( ) ; v1_Iter2 != v1_NewEnd2 ; v1_Iter2++ )
      cout << *v1_Iter2 << " ";
   cout << ")." << endl;
}
```

## <a name="upper_bound"></a>  upper_bound

Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator, class Type>
   ForwardIterator upper_bound(
      ForwardIterator first,
      ForwardIterator last,
      const Type& value);

template<class ForwardIterator, class Type, class Predicate>
   ForwardIterator upper_bound(
      ForwardIterator first,
      ForwardIterator last,
      const Type& value,
      Predicate comp);

```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Aranacak aralıktaki ilk öğenin konumu.

*Son*<br/>
Bir önceki öğenin konumunu son öğesi aranacak aralıktaki.

*value*<br/>
Sıralanmış aralıktaki tarafından döndürülen yineleyici tarafından ele alınan öğenin değeri olması gereken değer.

*Comp*<br/>
Bir öğenin daha az olan algılama tanımlayan kullanıcı tanımlı işlevin doğrulama nesnesi. İkili koşulu, iki bağımsız değişkeni alır ve döndürür **true** karşılanmazsa ve **false** koşullar karşılanırsa.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen değerden daha büyük bir değere sahip ilk öğenin konumuna ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralık geçerli olmalı; Tüm yineleyiciler tekrar başvurulabilir olmalı ve dizi içinde son konuma ilk konumdan erişilebilir olmalıdır erişilebilmelidir.

Bir sıralanmış aralıkta kullanımının ön koşuludur `upper_bound` ve sıralama ölçütü ikili koşul tarafından belirtildiği gibi aynı.

Aralığın değiştirilmez `upper_bound`.

İleriye doğru Yineleyicilerin değer türlerinin daha küçük olması-sıralanmalıdır daha karşılaştırılabilir, iki öğe belirtildiğinde, (yani birinin diğerinden diğerinden daha küçük olmadığı anlamında) eşit veya birinin diğerinden küçük olduğu belirlenebilir. Bu bir sıralamaya neden olur öğeler arasında neden olur

Algoritmanın karmaşıklığı, rasgele erişim yineleyicileri için logaritmik ve doğrusal Aksi takdirde doğrusaldır adım sayısı ile (`last - first`).

### <a name="example"></a>Örnek

```cpp
// alg_upper_bound.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>      // greater<int>( )
#include <iostream>

// Return whether modulus of elem1 is less than modulus of elem2
bool mod_lesser( int elem1, int elem2 )
{
    if ( elem1 < 0 )
        elem1 = - elem1;
    if ( elem2 < 0 )
        elem2 = - elem2;
    return elem1 < elem2;
}

int main()
{
    using namespace std;

    vector<int> v1;
    // Constructing vector v1 with default less-than ordering
    for ( auto i = -1 ; i <= 4 ; ++i )
    {
        v1.push_back(  i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back(  ii  );
    }

    cout << "Starting vector v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    sort(v1.begin(), v1.end());
    cout << "Original vector v1 with range sorted by the\n "
        << "binary predicate less than is v1 = ( " ;
    for (const auto &Iter : v1)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vector v2 with range sorted by greater
    vector<int> v2(v1);

    sort(v2.begin(), v2.end(), greater<int>());

    cout << "Original vector v2 with range sorted by the\n "
        << "binary predicate greater is v2 = ( " ;
    for (const auto &Iter : v2)
        cout << Iter << " ";
    cout << ")." << endl;

    // Constructing vectors v3 with range sorted by mod_lesser
    vector<int> v3(v1);
    sort(v3.begin(), v3.end(), mod_lesser);

    cout << "Original vector v3 with range sorted by the\n "
        <<  "binary predicate mod_lesser is v3 = ( " ;
    for (const auto &Iter : v3)
        cout << Iter << " ";
    cout << ")." << endl;

    // Demonstrate upper_bound

    vector<int>::iterator Result;

    // upper_bound of 3 in v1 with default binary predicate less<int>()
    Result = upper_bound(v1.begin(), v1.end(), 3);
    cout << "The upper_bound in v1 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // upper_bound of 3 in v2 with the binary predicate greater<int>( )
    Result = upper_bound(v2.begin(), v2.end(), 3, greater<int>());
    cout << "The upper_bound in v2 for the element with a value of 3 is: "
        << *Result << "." << endl;

    // upper_bound of 3 in v3 with the binary predicate  mod_lesser
    Result = upper_bound(v3.begin(), v3.end(), 3,  mod_lesser);
    cout << "The upper_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}

```
## <a name="see-also"></a>Ayrıca bkz.

[\<algoritma >](../standard-library/algorithm.md)<br/>