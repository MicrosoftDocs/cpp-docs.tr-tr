---
title: '&lt;algoritma&gt; işlevleri'
ms.date: 11/04/2016
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
ms.assetid: c10b0c65-410c-4c83-abf8-8b7f61bba8d0
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
ms.openlocfilehash: f389d38cf84f8f72d12242e798010d53a26f81a8
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661535"
---
# <a name="ltalgorithmgt-functions"></a>&lt;algoritma&gt; işlevleri

## <a name="adjacent_find"></a>adjacent_find

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
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator adjacent_find(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class BinaryPredicate>
ForwardIterator adjacent_find(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*soyadına*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*pred*\
Aranan aralıktaki bitişik öğelerin değerlerinin karşılanmasını sağlayan ikili koşul.

### <a name="return-value"></a>Dönüş değeri

Her birine eşit (ilk sürümde) veya ikili koşulun (İkinci sürümde) tarafından verilen koşulu karşılayan, bu tür bir öğe çifti bulunduğu bir ileri Yineleyici. Aksi takdirde, *son* ' a işaret eden bir yineleyici döndürülür.

### <a name="remarks"></a>Açıklamalar

`adjacent_find` Algoritma, değiştirici olmayan bir dizi algoritmadır. Aranacak Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve son konuma artırılamadı tarafından ilk kez ulaşılabilir. Algoritmanın zaman karmaşıklığı, aralıkta bulunan öğelerin sayısında doğrusal bir sayıdır.

Öğeler `operator==` arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

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
    list<int> L;
    list<int>::iterator Iter;
    list<int>::iterator result1, result2;

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
        cout << "There are two adjacent elements that are equal.\n"
            << "They have a value of "
            << *( result1 ) << "." << endl;

    result2 = adjacent_find( L.begin( ), L.end( ), twice );
    if ( result2 == L.end( ) )
        cout << "There are not two adjacent elements where the "
            << "second is twice the first." << endl;
    else
    {
        cout << "There are two adjacent elements where "
            << "the second is twice the first.\n"
            << "They have values of " << *(result2++)
            << " & " << *result2 << "." << endl;
    }
}
```

```Output
L = ( 50 40 10 20 20 )
There are two adjacent elements that are equal.
They have a value of 20.
There are two adjacent elements where the second is twice the first.
They have values of 10 & 20.
```

## <a name="all_of"></a>all_of

Verilen aralıktaki her bir öğede bir koşul olduğunda **true** döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
bool all_of(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template <class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
bool all_of(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir koşulun denetlenmesi için nereden başlayacağını gösteren bir giriş Yineleyici. Yineleyici, bir dizi öğenin başladığı yeri işaretler.

*soyadına*\
Bir koşulu denetlenecek öğe aralığının sonunu gösteren bir giriş Yineleyici.

*pred*\
İçin sınanacak koşul. Bu, denetlenen bir öğe tarafından karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı bir koşul işlevi nesnesidir. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Belirtilen aralıktaki her öğede koşul algılanırsa veya Aralık boşsa **true** , değilse **false** değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon **işlevi yalnızca,** `N` `[0, last - first)`Aralık içinde her biri için true değerini döndürür `pred(*(first + N))` .

### <a name="example"></a>Örnek

```cpp
// alg_all_of.cpp
// compile with: /EHsc
#include <list>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;

    list<int> li { 50, 40, 10, 20, 20 };
    list<int>::iterator iter;

    cout << "li = ( ";
    for (iter = li.begin(); iter != li.end(); iter++)
        cout << *iter << " ";
    cout << ")" << endl;

    // Check if all elements in li are even.
    auto is_even = [](int elem){ return !(elem % 2); };
    if (all_of(li.begin(), li.end(), is_even))
        cout << "All the elements are even numbers.\n";
    else
        cout << "Not all the elements are even numbers.\n";
}
```

```Output
li = ( 50 40 10 20 20 )
All the elements are even numbers.
```

## <a name="any_of"></a>any_of

Bir koşul, belirtilen öğe aralığında en az bir kez olduğunda **true** döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
bool any_of(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template <class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
bool any_of(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir koşul için bir öğe aralığının nerede başlatılacağını gösteren bir giriş Yineleyici.

*soyadına*\
Bir koşulu denetlenecek öğe aralığının sonunu gösteren bir giriş Yineleyici.

*pred*\
İçin sınanacak koşul. Bu, Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Koşul, sınanmakta olan öğe tarafından yerine getirilmesi gereken koşulu tanımlar. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşul, belirtilen aralıkta en az bir kez algılanırsa **true** , koşul hiç algılanmadıysa **false** döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yalnızca, Aralık içinde bazıları `N` için true değerini döndürür

`[0, last - first)`, koşul `pred(*(first + N))` true 'dur.

### <a name="example"></a>Örnek

```cpp
// alg_any_of.cpp
// compile with: /EHsc
#include <list>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;

    list<int> li { 51, 41, 11, 21, 20 };

    cout << "li = ( ";
    for (auto const& el : li)
        cout << el << " ";
    cout << ")" << endl;

    // Check if there is an even elememt in li.
    auto is_even = [](int const elem){ return !(elem % 2); };
    if (any_of(li.begin(), li.end(), is_even))
        cout << "There's an even element in li.\n";
    else
        cout << "There are no even elements in li.\n";
}
```

```Output
li = ( 51 41 11 21 20 )
There's an even element in li.
```

## <a name="binary_search"></a>binary_search

Belirtilen değere eşit sıralanmış bir aralıkta bir öğe olup olmadığını ya da bir ikili koşula göre belirtilen anlamda ona eşdeğer bir öğe olup olmadığını sınar.

```cpp
template<class ForwardIterator, class Type>
bool binary_search(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ForwardIterator, class Type, class BinaryPredicate>
bool binary_search(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*soyadına*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*deeri*\
Öğe değeri ile eşleşmesi gereken veya ikili koşul tarafından belirtilen öğe değeri ile koşulu karşılaması gereken değer.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

aralıkta belirtilen değere eşit veya eşdeğer bir öğe bulunursa **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralığı geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve sıra içinde, son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Sıralanmış aralığın her biri, algoritma tarafından Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya uygun `binary_search` olarak, algoritmanın uygulamasına bir ön koşul olarak düzenlenmelidir.

Kaynak aralıkları tarafından `binary_search`değiştirilmez.

İleriye doğru yineleyicilerin değer türlerinin sıralanabilmesi için kıyasla daha az karşılaştırılabilir olması gerekir. bu sayede, iki öğe verildiğinde, eşdeğer oldukları (Yani bunlardan daha küçük olmadığı anlamda) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, eşdeğer olmayan öğeler arasında bir sıralamaya neden olur

Algoritmanın karmaşıklığı Rastgele erişimli yineleyiciler ve doğrusal olarak, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle, (`last` - `first`) ile orantılıdır.

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

    list<int> List1;

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

```Output
List1 = ( 5 10 20 25 30 50 )
There is an element in list List1 with a value equal to 10.
There is an element in list List1 with a value greater than 10 under greater than.
Ordered using mod_lesser, vector v1 = ( 0 -1 1 -2 2 3 4 )
There is an element with a value equivalent to -3 under mod_lesser.
```

## <a name="clamp"></a>Clamp

Bir değeri üst ve alt sınır ile karşılaştırır ve sınırlar arasındaysa değere bir başvuru ya da değerin üstünde ya da altında ise, üst veya alt sınır başvurusu döndürür.

```cpp
template<class Type>
constexpr const Type& clamp(
    const Type& value,
    const Type& lower,
    const Type& upper);

template<class Type, class Compare>
constexpr const Type& clamp(
    const Type& value,
    const Type& lower,
    const Type& upper,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*deeri*\
*Üst* ve *alt*ile karşılaştırılacak değer.

*düşürül*\
Değerlerin Clamp *değerine* alt sınırı.

*üst*\
Değerlerin Clamp *değerine* göre üst sınırı.

*pred*\
*Değeri* *alt* veya *üst*ile karşılaştırmak için kullanılan bir koşul. Karşılaştırma koşulu iki bağımsız değişken alır ve ilki ikinciden küçükse **true** , aksi durumda **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

`upper < value` *Alt* `value < lower`If için bir başvuru veya bir *üst* if başvurusu döndürür. Aksi takdirde, *değere*bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

*Sınır* *daha*küçüktür ise, bu davranış tanımsızdır.

## <a name="copy"></a>kopya

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına ileri yönde atar.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator copy(
    InputIterator first,
    InputIterator last,
    OutputIterator destBeg);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 copy(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Kaynak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*soyadına*\
Kaynak aralıktaki son öğeden sonraki konumu ele alan bir giriş Yineleyici.

*destBeg*\
Hedef aralıktaki ilk öğenin konumunu ele alarak çıkış Yineleyici.

### <a name="return-value"></a>Dönüş değeri

Hedef aralıktaki son öğeden bir geçen konumu ele alan çıkış Yineleyici, yani `result` Yineleyici adresler + (*son* - *ilk*).

### <a name="remarks"></a>Açıklamalar

Kaynak aralığının geçerli olması gerekir ve hedefte, kopyalanmakta olan tüm öğeleri tutmak için yeterli alan olmalıdır.

Algoritma, kaynak öğeleri ilk öğesiyle başlayarak sırayla kopyalamadığından, hedef Aralık kaynak aralığı ile örtüşebilir ve kaynak aralığın *son* konumu hedef aralıkta yer alır. `copy`Kaynak ve hedef aralıklar arasında çakışma yoksa sağ değil, öğeleri sola kaydırmak için kullanılabilir. Herhangi bir sayıda konum sağa kaydırmak için [copy_backward](../standard-library/algorithm-functions.md#copy_backward) algoritmasını kullanın.

`copy` Algoritma yalnızca yineleyiciler tarafından işaret edilen değerleri değiştirir ve hedef aralıktaki öğelere yeni değerler atanıyor. Yeni öğe oluşturmak için kullanılamaz ve öğeleri boş bir kapsayıcıya doğrudan ekleyemez.

### <a name="example"></a>Örnek

```cpp
// alg_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
    using namespace std;
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2;

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

## <a name="copy_backward"></a>copy_backward

Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
BidirectionalIterator2 copy_backward(
    BidirectionalIterator1 first,
    BidirectionalIterator1 last,
    BidirectionalIterator2 destEnd);
```

### <a name="parameters"></a>Parametreler

*adı*\
Kaynak aralıktaki ilk öğenin konumunu belirleyen çift yönlü yineleyici.

*soyadına*\
Kaynak aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

*destEnd*\
Hedef aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

### <a name="return-value"></a>Dönüş değeri

Hedef aralıktaki son öğeden bir geçen konumu ele alan çıkış Yineleyici, yani Yineleyici *DestEnd* -(*son* - *ilk*) adresini adresleyen.

### <a name="remarks"></a>Açıklamalar

Kaynak aralığının geçerli olması gerekir ve hedefte, kopyalanmakta olan tüm öğeleri tutmak için yeterli alan olmalıdır.

`copy_backward` Algoritma ,`copy` algoritmadan daha sıkı gereksinimler getirir. Hem giriş hem de çıkış yineleyicileri çift yönlü olmalıdır.

Ve `copy_backward` [move_backward](../standard-library/algorithm-functions.md#move_backward) algoritmaları, çıkış aralığını hedef C++ aralığın sonuna işaret eden bir yineleyici ile tanımlayarak tek standart kitaplık algoritmalardır.

Algoritma, kaynak öğeleri son öğe ile başlayan sırayla kopyalamadığından, hedef Aralık kaynak aralığı ile örtüşebilir ve kaynak aralığın *ilk* konumu hedef aralıkta yer içermez. `copy_backward`Kaynak ve hedef aralıklar arasında çakışma olmaması dışında, öğeleri sağa doğru kaydırmak için kullanılabilir. Herhangi bir sayıda konum sola kaydırmak için [kopyalama](../standard-library/algorithm-functions.md#copy) algoritmasını kullanın.

`copy_backward` Algoritma yalnızca yineleyiciler tarafından işaret edilen değerleri değiştirir ve hedef aralıktaki öğelere yeni değerler atanıyor. Yeni öğe oluşturmak için kullanılamaz ve öğeleri boş bir kapsayıcıya doğrudan ekleyemez.

### <a name="example"></a>Örnek

```cpp
// alg_copy_bkwd.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main() {
    using namespace std;
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2;

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

```Output
v1 = ( 0 10 20 30 40 50 )
v2 = ( 0 3 6 9 12 15 18 21 24 27 30 )
v2 with v1 insert = ( 0 3 6 9 0 10 20 21 24 27 30 )
v2 with shifted insert = ( 0 3 6 9 0 10 0 10 20 27 30 )
```

## <a name="copy_if"></a>copy_if

Bir dizi öğe içinde, belirtilen koşul için **doğru** olan öğeleri kopyalar.

```cpp
template<class InputIterator, class OutputIterator, class UnaryPredicate>
OutputIterator copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator dest,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class UnaryPredicate>
ForwardIterator2 copy_if(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Koşulu denetlemek için bir aralığın başlangıcını gösteren bir giriş Yineleyici.

*soyadına*\
Aralığın sonunu gösteren bir giriş yineleyicisi.

*HD*\
Kopyalanmış öğelerin hedefini gösteren çıkış yineleyicisi.

*pred*\
Aralıktaki her öğenin test edileceği koşul. Bu koşul, Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Birli koşul bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşulu yerine getiren her öğe için bir kez *hedefe* eşit olan bir çıkış yineleyicisi. Diğer bir deyişle, dönüş değeri eksi *hedef* , kopyalanmış öğelerin sayısına eşittir.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi değerlendirilir

`if (pred(*first + N)) * dest++ = *(first + N))`

`N` aralıkta `N` herbiriiçinbirkez,endüşükdeğerlebaşlayandeğerlerikesinlikleartırmakiçin.`[0, last - first)` *Hedef* ve *ilk* olarak depolama bölgelerini belirlerseniz, *hedef* Aralık `[ first, last )`içinde olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// alg_copy_if.cpp
// compile with: /EHsc
#include <list>
#include <algorithm>
#include <iostream>

void listlist(std::list<int> l)
{
    std::cout << "( ";
    for (auto const& el : l)
        std::cout << el << " ";
    std::cout << ")" << std::endl;
}

int main()
{
    using namespace std;
    list<int> li{ 46, 59, 88, 72, 79, 71, 60, 5, 40, 84 };
    list<int> le(li.size()); // le = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };
    list<int> lo(li.size()); // lo = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

    cout << "li = ";
    listlist(li);

    // is_even checks if the element is even.
    auto is_even = [](int const elem) { return !(elem % 2); };
    // use copy_if to select only even elements from li 
    // and copy them to le, starting from le's begin position
    auto ec = copy_if(li.begin(),li.end(), le.begin(), is_even);
    le.resize(std::distance(le.begin(), ec));  // shrink le to new size

    cout << "Even numbers are le = ";
    listlist(le);

    // is_odd checks if the element is odd.
    auto is_odd = [](int const elem) { return (elem % 2); };
    // use copy_if to select only odd elements from li
    // and copy them to lo, starting from lo's begin position
    auto oc = copy_if(li.begin(), li.end(), lo.begin(), is_odd);
    lo.resize(std::distance(lo.begin(), oc));  // shrink lo to new size

    cout << "Odd numbers are lo = ";
    listlist(lo);
}
```

```Output
li = ( 46 59 88 72 79 71 60 5 40 84 )
Even numbers are le = ( 46 88 72 60 40 84 )
Odd numbers are lo = ( 59 79 71 5 )
```

## <a name="copy_n"></a>copy_n

Belirtilen sayıda öğeyi kopyalar.

```cpp
template<class InputIterator, class Size, class OutputIterator>
OutputIterator copy_n(
    InputIterator first,
    Size count,
    OutputIterator dest);

template<class ExecutionPolicy, class ForwardIterator1, class Size, class ForwardIterator2>
ForwardIterator2 copy_n(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    Size count,
    ForwardIterator2 dest);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin nereden kopyalanacağını gösteren bir giriş Yineleyici.

*biriktirme*\
Kopyalanacak öğe sayısını belirten imzalı veya işaretsiz bir tamsayı türü.

*HD*\
Öğelerin nereye kopyalanacağını gösteren bir çıkış yineleyicisi.

### <a name="return-value"></a>Dönüş değeri

Öğelerin kopyalandığı çıkış yineleyiciyi döndürür. Bu, *hedef* parametrenin döndürülen değeriyle aynıdır.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, Aralık `*(dest + N) = *(first + N))` `N` `[0, count)`içinde her biri için bir kez değerlendirilir ve en düşük değer ile `N` başlangıç değerlerini kesin olarak artırır. Ardından döndürür `dest + N`. *Hedef* ve *ilk* olarak depolama bölgelerini belirlerseniz, *hedef* Aralık `[first, last)`içinde olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// alg_copy_n.cpp
// compile with: cl /EHsc /W4 alg_copy_n.cpp
#include <algorithm>
#include <iostream>
#include <string>

int main()
{
    using namespace std;
    string s1{"dandelion"};
    string s2{"badger"};

    cout << s1 << " + " << s2 << " = ";

    // Copy the first 3 letters from s1
    // to the first 3 positions in s2
    copy_n(s1.begin(), 3, s2.begin());

    cout << s2 << endl;
}
```

```Output
dandelion + badger = danger
```

## <a name="count"></a>biriktirme

Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.

```cpp
template<class InputIterator, class Type>
typename iterator_traits<InputIterator>::difference_type count(
    InputIterator first,
    InputIterator last,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Type>
typename iterator_traits<ForwardIterator>::difference_type
count(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir giriş yineleyicisi, geçilen aralıktaki ilk öğenin konumunu ele alıyor.

*soyadına*\
Bir giriş yineleyicisi, ele eklenecek aralıktaki son öğeden sonraki konumu ele alıyor.

*deeri*\
Sayılacak öğelerin değeri.

### <a name="return-value"></a>Dönüş değeri

`InputIterator` Değer *değeri*olan [*First*, *Last*) aralığındaki öğe sayısını sayan fark türü.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Bu algoritma, [count_if](../standard-library/algorithm-functions.md#count_if)şablon işlevi ile herhangi bir koşulu karşılayan öğeleri saymak için genelleştirilmiştir.

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

## <a name="count_if"></a>count_if

Değerleri belirtilen koşula uyan bir aralıktaki öğelerin sayısını döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
typename iterator_traits<InputIterator>::difference_type count_if(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
typename iterator_traits<ForwardIterator>::difference_type
count_if(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Aranacak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*soyadına*\
Aranacak aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*pred*\
Bir öğenin sayılmaması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşul tarafından belirtilen koşulu karşılayan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi, algoritma [sayısının](../standard-library/algorithm-functions.md#count)genelleştirilmesidir ve bu koşulun "şuna eşit belirli bir değere" koşulunu herhangi bir koşula göre değiştirir.

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

## <a name="equal"></a>sıfıra

Bir ikili koşula göre belirtilen anlamda, eşitlik veya denklik için öğe ile iki Aralık öğesini karşılaştırır.

Farklı `std::equal` kapsayıcı türlerindeki (örneğin `vector` ve `list`) veya farklı öğe türlerini karşılaştırırken veya kapsayıcıların alt aralıklarını karşılaştırmanız gerektiğinde kullanın. Aksi halde, aynı kapsayıcı türünde aynı türdeki öğeleri karşılaştırırken, her kapsayıcı için belirtilen üye `operator==` olmayan öğeyi kullanın.

İkinci Aralık için yalnızca tek bir yineleyici alan aşırı yüklemeler ikinci aralığın ilk aralıktan daha uzun olması fark etmez ve ikinci Aralık daha kısaysa tanımsız davranışlara neden olacak şekilde, C++ 14 kodunda çift aralıklı aşırı yüklemeleri kullanın. ilk aralıktan fazla.

```cpp
template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    BinaryPredicate pred); // C++14

template<class InputIterator1, class InputIterator2>
bool equal(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2);

template<class InputIterator1, class InputIterator2, class BinaryPredicate>
bool equal(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
bool equal(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
bool equal(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
bool equal(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
bool equal(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Sınanacak ilk aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*last1*\
Test edilecek ilk aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*first2*\
Test edilecek ikinci aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*last2*\
Test edilecek ikinci aralıktaki son öğeden bir önceki öğenin konumunu ele aldığı bir giriş Yineleyici.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

yalnızca, veya öğesi öğesine göre karşılaştırıldığı zaman ikili koşulun altında aralıklar özdeş veya eşdeğer ise **true** . Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Aranacak Aralık geçerli olmalıdır; tüm yineleyiciler başvurulmalıdır ve en son konuma artırılamadı tarafından ilk kez ulaşılabilir.

İki Aralık eşitse, algoritmanın zaman karmaşıklığı, aralıkta bulunan öğelerin sayısında doğrusal olur. Aksi takdirde, işlev hemen **false**döndürür.

`operator==` Ne ne de Kullanıcı tanımlı koşul, işlenenleri arasında simetrik, yansımalı ve geçişli bir denklik ilişkisi uygulamak için gerekli değildir.

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

## <a name="equal_range"></a>equal_range

Sıralı bir Aralık verildiğinde, tüm öğelerin verilen değere eşit olduğu alt aralığı bulur.

```cpp
template<class ForwardIterator, class Type>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ForwardIterator, class Type, class Compare>
pair<ForwardIterator, ForwardIterator> equal_range(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*soyadına*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*deeri*\
Sıralı aralıktaki aranmakta olan değer.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Tüm öğelerin, kullanılan ikili koşul ( *Pred* veya varsayılan, küçüktür) tarafından tanımlanan anlamda *değere* eşit olduğu, bir alt Aralık belirten bir alt aralığı belirten bir çift yineleyiciler çifti.

Aralıktaki hiçbir öğe *değere*eşdeğer değilse, döndürülen çiftin içindeki ileri yineleyiciler eşittir ve aralığın sırasını bozmadan *değerin* eklenebileceği noktayı belirler.

### <a name="remarks"></a>Açıklamalar

Algoritmanın döndürdüğü çiftin ilk yineleyicisi [lower_bound](../standard-library/algorithm-functions.md#lower_bound)ve ikinci Yineleyici [upper_bound](../standard-library/algorithm-functions.md#upper_bound).

Aralık, öğesine `equal_range`verilen koşula göre sıralanmalıdır. Örneğin, büyüktür koşulunu kullanacaksanız, Aralık azalan düzende sıralanmalıdır.

Tarafından `equal_range` döndürülen yineleyicilerin çifti tarafından tanımlanan muhtemelen boş alt aralıktaki öğeler, kullanılan koşul tarafından tanımlanan anlamda *değere* eşdeğerdir.

Algoritmanın karmaşıklığı Rastgele erişimli yineleyiciler ve doğrusal olarak, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle - , diğer bir deyişle, diğer bir deyişle,

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

template<class T> void equal_range_demo( const vector<T>& original_vector, T value )
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
        = equal_range( v.begin(), v.end(), value );

    cout << "Result of equal_range with value = " << value << ":" << endl << '\t';
    dump_vector( v, result );
    cout << endl;
}

template<class T, class F> void equal_range_demo( const vector<T>& original_vector, T value, F pred, string predname )
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
        = equal_range( v.begin(), v.end(), value, pred );

    cout << "Result of equal_range with value = " << value << ":" << endl << '\t';
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

## <a name="fill"></a>doldurması

Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.

```cpp
template<class ForwardIterator, class Type>
void fill(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Type>
void fill(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
İleri bir yineleyici, içine eklenecek aralıktaki ilk öğenin konumunu ele alıyor.

*soyadına*\
Bir ileriye doğru yineleyici, içine geçmek üzere aralıktaki son öğeden sonraki konumu ele alıyor.

*deeri*\
[*First*, *Last*) aralığındaki öğelere atanacak değer.

### <a name="remarks"></a>Açıklamalar

Hedef Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve son konuma artırılamadı tarafından ilk kez ulaşılabilir. Karmaşıklık, aralığın boyutuyla doğrusal olarak belirlenir.

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
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="fill_n"></a>fill_n

Belirli bir öğeyle başlayan bir aralıktaki belirli öğe sayısına yeni bir değer atar.

```cpp
template<class OutputIterator, class Size, class Type>
OutputIterator fill_n(
    OutputIterator first,
    Size count,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Size, class Type>
ForwardIterator fill_n(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    Size count,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Değer *değerine*atanacak aralıktaki ilk öğenin konumunu ele alarak çıkış Yineleyici.

*biriktirme*\
Değere atanacak öğe sayısını belirten imzalı veya işaretsiz bir tamsayı türü.

*deeri*\
[*First*, *First + Count*) aralığındaki öğelere atanacak değer.

### <a name="return-value"></a>Dönüş değeri

Eğer *Count* değeri sıfır >, aksi takdirde ilk öğe olan öğe için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Hedef Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve son konuma artırılamadı tarafından ilk kez ulaşılabilir. Karmaşıklık, aralığın boyutuyla doğrusal olarak belirlenir.

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
    vector<int> v;

    for ( auto i = 0 ; i < 9 ; ++i )
        v.push_back( 0 );

    cout << " vector v = ( " ;
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

## <a name="find"></a>bilgi

Bir öğenin belirli bir değere sahip olan aralıktaki ilk geçtiği konumu bulur.

```cpp
template<class InputIterator, class Type>
InputIterator find(
    InputIterator first,
    InputIterator last,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Type>
ForwardIterator find(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Belirtilen değer için aranacak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*soyadına*\
Belirtilen değer için Aranmak üzere aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*deeri*\
Aranacak değer.

### <a name="return-value"></a>Dönüş değeri

Aranmakta olan aralıktaki belirtilen değerin ilk oluşumunu ele aldığı bir giriş Yineleyici. Denk bir değere sahip hiçbir öğe bulunmazsa, *en son*döndürür.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Kullanarak `find()`bir kod örneği için bkz. [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="find_end"></a>find_end

Belirli bir diziye özdeş veya bir ikili koşula göre belirtildiği şekilde denk olan son dizi için bir aralık arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_end(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class Pred>
ForwardIterator1 find_end(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    Pred pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator1
find_end(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1,
class ForwardIterator2, class BinaryPredicate>
ForwardIterator1
find_end(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*first1*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*last1*\
Arama yapılacak aralıktaki son öğeden sonraki konumu ele alarak ileri Yineleyici.

*first2*\
Arama için aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*last2*\
Arama için aralıktaki son öğeden geçen bir konumu ele alarak ileri Yineleyici.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Belirtilen [first2, Last2) dizisiyle eşleşen [First1, last1) içindeki son alt dizinin ilk öğesinin konumunu ele alan bir ileriye doğru yineleyici.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide, son konuma artırılamadı tarafından ilk kez ulaşılabilir.

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
    vector<int> v1, v2;
    list<int> L1;
    vector<int>::iterator Iter1, Iter2;
    list<int>::iterator L1_Iter, L1_inIter;

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
    vector<int>::iterator result1;
    result1 = find_end ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

    if ( result1 == v1.end( ) )
        cout << "There is no match of L1 in v1."
            << endl;
    else
        cout << "There is a match of L1 in v1 that begins at "
            << "position "<< result1 - v1.begin( ) << "." << endl;

    // Searching v1 for a match to L1 under the binary predicate twice
    vector<int>::iterator result2;
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

## <a name="find_first_of"></a>find_first_of

Bir hedef aralığındaki çeşitli değerlerden herhangi birinin ilk geçtiği yeri veya bir ikili koşula göre belirtilen bir öğeler kümesine belirtildiği şekilde denk olan çeşitli öğelerin geçtiği ilk yeri arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 find_first_of(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 find_first_of(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator1
find_first_of(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1,
class ForwardIterator2, class BinaryPredicate>
ForwardIterator1
find_first_of(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*first1*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*last1*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*first2*\
Eşleştirilecek aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*last2*\
Bir ileri Yineleyici, eşleştirilecek aralıktaki son öğeden sonraki konumu ele alıyor.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Bir ileri Yineleyici, belirtilen sırayla eşleşen veya bir ikili koşula göre belirtilen bir Sense ile eşdeğer olan ilk alt dizinin ilk öğesinin konumunu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide, son konuma artırılamadı tarafından ilk kez ulaşılabilir.

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
    vector<int> v1, v2;
    list<int> L1;
    vector<int>::iterator Iter1, Iter2;
    list<int>::iterator L1_Iter, L1_inIter;

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
    vector<int>::iterator result1;
    result1 = find_first_of ( v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

    if ( result1 == v1.end( ) )
        cout << "There is no match of L1 in v1."
            << endl;
    else
        cout << "There is at least one match of L1 in v1"
            << "\n and the first one begins at "
            << "position "<< result1 - v1.begin( ) << "." << endl;

    // Searching v1 for a match to L1 under the binary predicate twice
    vector<int>::iterator result2;
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

## <a name="find_if"></a>find_if

Bir öğenin belirli bir koşulu karşıladığı aralıktaki ilk geçtiği konumu bulur.

```cpp
template<class InputIterator, class UnaryPredicate>
InputIterator find_if(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
ForwardIterator find_if(
    ExecutionPolicy&& exec,
    ForwardIterator first, ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*soyadına*\
Aranacak aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*pred*\
Aranmakta olan öğenin yerine getirilmesi için koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi veya [lambda ifadesi](../cpp/lambda-expressions-in-cpp.md) . Birli koşul tek bir bağımsız değişken alır ve memnun olursa **true** , aksi takdirde **false** döndürür. *Pred* imzası etkin `bool pred(const T& arg);`bir şekilde olmalıdır; burada `T` , başvuru yapıldığında örtük olarak dönüştürülebilen `InputIterator` bir tür olur. **Const** anahtar sözcüğü yalnızca işlev nesnesinin veya lambda bağımsız değişkeni değiştirmemelidir.

### <a name="return-value"></a>Dönüş değeri

Koşul tarafından belirtilen koşulu karşılayan aralıktaki ilk öğeyi ifade eden bir giriş Yineleyici (koşul, **true**sonucunu vermez). Koşulu karşılayan bir öğe bulunmazsa, *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi, "Şuna eşittir belirli bir değere" koşulunu değiştirme algoritması [bul](../standard-library/algorithm-functions.md#find)'un bir genelleştirmesidir. Mantıksal ters (koşulu karşılamayan ilk öğeyi bulun) için bkz. [find_if_not](../standard-library/algorithm-functions.md#find_if_not).

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

## <a name="find_if_not"></a>find_if_not

Bir koşulu karşılamayan belirtilen aralıktaki ilk öğeyi döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
InputIterator find_if_not(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
ForwardIterator find_if_not(
    ExecutionPolicy&& exec,
    ForwardIterator first, ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*soyadına*\
Aranacak aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*pred*\
Aranan öğenin karşılanmadığı koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi veya [lambda ifadesi](../cpp/lambda-expressions-in-cpp.md) . Birli koşul tek bir bağımsız değişken alır ve memnun olursa **true** , aksi takdirde **false** döndürür. *Pred* imzası etkin `bool pred(const T& arg);`bir şekilde olmalıdır; burada `T` , başvuru yapıldığında örtük olarak dönüştürülebilen `InputIterator` bir tür olur. **Const** anahtar sözcüğü yalnızca işlev nesnesinin veya lambda bağımsız değişkeni değiştirmemelidir.

### <a name="return-value"></a>Dönüş değeri

Koşul tarafından belirtilen koşulu karşılamayan aralıktaki ilk öğeyi başvuran bir giriş Yineleyici (koşul **false**olarak sonuçlanır). Tüm öğeler koşulu karşılıyorsa (koşul her öğe için **true** sonucunu verir), *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi, "Şuna eşittir belirli bir değere" koşulunu değiştirme algoritması [bul](../standard-library/algorithm-functions.md#find)'un bir genelleştirmesidir. Mantıksal ters (koşulu karşılayan ilk öğeyi bulun) için bkz. [find_if](../standard-library/algorithm-functions.md#find_if).

Bir kod örneği `find_if_not()`için, bkz. [find_if](../standard-library/algorithm-functions.md#find_if).

## <a name="for_each"></a>for_each

Bir aralıktaki ileriye doğru sıradaki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.

```cpp
template<class InputIterator, class Function>
Function for_each(
    InputIterator first,
    InputIterator last,
    Function func);

template<class ExecutionPolicy, class ForwardIterator, class Function>
void for_each(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Function func);
```

### <a name="parameters"></a>Parametreler

*adı*\
Üzerinde çalışılan aralıktaki ilk öğenin konumunu ele alan bir giriş Yineleyici.

*soyadına*\
Üzerinde çalışılan aralıktaki son öğeden sonraki konumu ele alan bir giriş Yineleyici.

*melerinin*\
Aralıktaki her öğeye uygulanan Kullanıcı tanımlı işlev nesnesi.

### <a name="return-value"></a>Dönüş değeri

İşlev nesnesinin, aralıktaki tüm öğelere uygulandıktan sonra bir kopyası.

### <a name="remarks"></a>Açıklamalar

Algoritma `for_each` çok esnektir ve farklı, Kullanıcı tarafından belirtilen yollarla bir aralıktaki her öğe değişikliğine izin verir. Şablonlı işlevler, farklı parametreler geçirerek değiştirilmiş bir formda yeniden kullanılabilir. Kullanıcı tanımlı işlevler, algoritmanın aralıktaki tüm öğeleri işledikten sonra dönebilecek iç bir durum içinde bilgi birikmesini sağlayabilir.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve sıra içinde, son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Karmaşıklık en çok (*son* - *ilk*) karşılaştırmalarda doğrusal olarak belirlenir.

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
    MultValue ( const Type& value ) : Factor ( value ) {
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
    void operator( ) ( int elem )
    {
        num++;      // Increment the element count
        sum += elem;   // Add the value to the partial sum
    }

    // return Average
    operator double( )
    {
        return static_cast<double> (sum) /
            static_cast<double> (num);
    }
};

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1;

    // Constructing vector v1
    int i;
    for ( i = -4 ; i <= 2 ; i++ )
    {
        v1.push_back( i );
    }

    cout << "Original vector v1 = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // Using for_each to multiply each element by a Factor
    for_each ( v1.begin( ), v1.end( ), MultValue<int> ( -2 ) );

    cout << "Multiplying the elements of the vector v1\n "
            << "by the factor -2 gives:\n v1mod1 = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // The function object is templatized and so can be
    // used again on the elements with a different Factor
    for_each (v1.begin( ), v1.end( ), MultValue<int> (5 ) );

    cout << "Multiplying the elements of the vector v1mod\n "
            << "by the factor 5 gives:\n v1mod2 = ( " ;
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
Original vector v1 = ( -4 -3 -2 -1 0 1 2 ).
Multiplying the elements of the vector v1
by the factor -2 gives:
v1mod1 = ( 8 6 4 2 0 -2 -4 ).
Multiplying the elements of the vector v1mod
by the factor 5 gives:
v1mod2 = ( 40 30 20 10 0 -10 -20 ).
The average of the elements of v1 is:
Average ( v1mod2 ) = 10.
```

## <a name="for_each_n"></a>for_each_n

```cpp
template<class InputIterator, class Size, class Function>
InputIterator for_each_n(
    InputIterator first,
    Size n,
    Function f);

template<class ExecutionPolicy, class ForwardIterator, class Size, class Function>
ForwardIterator for_each_n(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    Size n,
    Function f);
```

## <a name="generate"></a>üretecek

Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki her öğeye atar.

```cpp
template<class ForwardIterator, class Generator>
void generate(
    ForwardIterator first,
    ForwardIterator last,
    Generator gen);

template<class ExecutionPolicy, class ForwardIterator, class Generator>
void generate(
    ExecutionPolicy&& exec,
    ForwardIterator first, ForwardIterator last,
    Generator gen);
```

### <a name="parameters"></a>Parametreler

*adı*\
Değerleri atanacak olan aralıktaki ilk öğenin konumunu ele veren ileriye doğru bir yineleyici.

*soyadına*\
Bir ileriye doğru yineleyici, değerleri atanacak olan aralıktaki son öğeden geçen öğeyi ele alıyor.

*alanına*\
Aralıktaki öğelerin her birine atanacak değerleri oluşturmak için kullanılan bağımsız değişken olmadan çağrılan bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi aralıktaki her öğe için çağrılır ve her çağrıldığında aynı değeri döndürmesi gerekmez. Örneğin, bir dosyadan okuma veya yerel bir durumu değiştirme ve değiştirme gibi olabilir. Oluşturucunun sonuç türü, Aralık için ileri yineleyicilerinin değer türüne dönüştürülebilir olmalıdır.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve sıra içinde, son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Karmaşıklık, gerekli olan oluşturucuya tam olarak ( `last`  -  `first`) çağrıları ile doğrusal bir şekilde yapılır.

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
    vector<int> v1 ( 5 );
    vector<int>::iterator Iter1;
    deque<int> deq1 ( 5 );
    deque<int>::iterator d1_Iter;

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

## <a name="generate_n"></a>generate_n

Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki belirli sayıda öğeye atar ve en son atanan değeri aşan konuma döndürür.

```cpp
template<class OutputIterator, class Diff, class Generator>
void generate_n(
    OutputIterator first,
    Diff count,
    Generator gen);

template<class ExecutionPolicy, class ForwardIterator, class Size, class Generator>
ForwardIterator generate_n(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    Size count,
    Generator gen);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Değerleri atanacak aralıktaki ilk öğenin konumunu ele veren çıkış Yineleyici.

*biriktirme*\
Oluşturucu işlevi tarafından bir değere atanacak öğe sayısını belirten imzalı veya işaretsiz bir tamsayı türü.

*alanına*\
Aralıktaki öğelerin her birine atanacak değerleri oluşturmak için kullanılan bağımsız değişken olmadan çağrılan bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi aralıktaki her öğe için çağrılır ve her çağrıldığında aynı değeri döndürmesi gerekmez. Örneğin, bir dosyadan okuma veya yerel bir durumu değiştirme ve değiştirme gibi olabilir. Oluşturucunun sonuç türü, Aralık için ileri yineleyicilerinin değer türüne dönüştürülebilir olmalıdır.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve sıra içinde, son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Karmaşıklık, gereken oluşturucunun tam olarak `count` çağrılarında doğrusal bir şekilde yapılır.

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

template <typename C>
void print(const string& s, const C& c)
{
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

## <a name="includes"></a>içermektedir

Sıralanmış bir aralığın ikinci bir sıralanmış aralıkta kapsanan tüm öğeleri içerip içermediğini sınar, burada öğeler arasındaki sıralama veya denklik ölçütü bir ikili koşula göre belirlenebilir.

```cpp
template<class InputIterator1, class InputIterator2>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2);

template<class InputIterator1, class InputIterator2, class Compare>
bool includes(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
bool includes(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Compare>
bool includes(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İkinci sıralı kaynak aralıktaki ilk öğenin konumunu ele alan, ikincinin tüm öğelerinin birincinin içine dahil edilip edilmeyeceğini test eden bir giriş Yineleyici.

*last1*\
İkinci sıralı kaynak aralıktaki en son öğeden geçen bir bir girdi yineleyicisi, ikincinin tüm öğelerinin birincinin içinde yer almayacağı için test edilir.

*first2*\
İkinci art arda sıralanmış kaynak aralıklarının ikinci kısmında ilk öğenin konumunu ele alan, ikincinin tüm öğelerinin birincinin içinde olup olmadığı test edilecek bir giriş Yineleyici.

*last2*\
İkinci art arda sıralanmış kaynak aralıklarının ikinci içindeki son öğeden geçen bir bir girdi yineleyicisi, ikincinin tüm öğelerinin birincinin içinde yer almayacağı için test edilir.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

ilk sıralanmış Aralık ikinci sıralı aralıktaki tüm öğeleri içeriyorsa **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu testi düşünmek için bir diğer yol ise ikinci kaynak aralığının ilk kaynak aralığın bir alt kümesi olup olmadığını belirlemiştir.

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide, son konuma artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Sıralanmış kaynak aralıklarının her biri, algoritma uygulaması için bir önkoşul olarak düzenlenmelidir, bu arada, Birleşik aralıkları sıralamak için algoritma tarafından kullanılacak şekilde aynı sıralamaya uygun olarak dahildir.

Kaynak aralıkları algoritma `merge`tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için kıyasla daha az olması gerekir, böylece iki öğe söz konusu olduğunda, eşdeğer oldukları (Yani bunlardan daha küçük olmayan) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha kesin olarak, algoritma, belirtilen bir ikili koşulun altındaki ilk sıralanmış aralıktaki tüm öğelerin, ikinci sıralı aralıktaki olanlarla eşdeğer sıralamaya sahip olup olmadığını sınar.

Algoritmanın karmaşıklığı, boş olmayan kaynak aralıkları için en çok `2 * ((last1 - first1) - (last2 - first2)) - 1` karşılaştırmalar ile doğrusal bir şekilde yapılır.

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
    vector<int> v1a, v1b;
    vector<int>::iterator Iter1a, Iter1b;

    // Constructing vectors v1a & v1b with default less-than ordering
    int i;
    for ( i = -2 ; i <= 4 ; i++ )
    {
        v1a.push_back( i );
    }

    int ii;
    for ( ii =-2 ; ii <= 3 ; ii++ )
    {
        v1b.push_back( ii );
    }

    cout << "Original vector v1a with range sorted by the\n "
            << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
            << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vectors v2a & v2b with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b );
    vector<int>::iterator Iter2a, Iter2b;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );
    v2a.pop_back( );

    cout << "Original vector v2a with range sorted by the\n "
            << "binary predicate greater is v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
            << "binary predicate greater is v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
    vector<int> v3a ( v1a ), v3b ( v1b ) ;
    vector<int>::iterator Iter3a, Iter3b;
    reverse (v3a.begin( ), v3a.end( ) );
    v3a.pop_back( );
    v3a.pop_back( );
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
            << "binary predicate mod_lesser is v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
            << "binary predicate mod_lesser is v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To test for inclusion under an asscending order
    // with the default binary predicate less<int>( )
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
        v2b.begin( ), v2b.end( ), greater<int>( ) );
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
At least one of the elements in vector v3b is not contained under mod_lesser in vector v3a.
```

## <a name="inplace_merge"></a>inplace_merge

Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class BidirectionalIterator>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last);

template<class BidirectionalIterator, class Compare>
void inplace_merge(
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last,
    Compare pred);

template<class ExecutionPolicy, class BidirectionalIterator>
void inplace_merge(
    ExecutionPolicy&& exec,
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last);

template<class ExecutionPolicy, class BidirectionalIterator, class Compare>
void inplace_merge(
    ExecutionPolicy&& exec,
    BidirectionalIterator first,
    BidirectionalIterator middle,
    BidirectionalIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Art arda iki sıralı aralıktaki ilk öğenin konumunu birleştirerek ve tek bir aralığa göre sıralanacak çift yönlü bir yineleyici.

*Beceri*\
Art arda iki sıralı aralığın ikinci, tek bir aralığa göre birleştirileceği ve sıralanan ilk öğenin konumunu ele aldığı çift yönlü bir yineleyici.

*soyadına*\
Art arda iki sıralı aralığın ikinci, tek bir aralığa göre birleştirilmesi ve sıralanabilmesi için geçen öğeden geçen öğeden geçen bir çift yönlü Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış ardışık aralıklar geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide, son konuma artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Sıralanmış ardışık aralıklar, her biri algoritma tarafından, Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya `inplace_merge` uygun olarak, algoritmanın uygulamasına bir önkoşul olarak düzenlenmelidir. Her aralıktaki öğelerin göreli sırası korunduğu için işlem kararlı değildir. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, öğe ilk Aralık Birleşik aralıktaki ikinciden önce gelir.

Algoritma, belleğin geçici bir arabelleğe ayırdığı şekilde kullanılabilir belleğe göre değişir. Yeterli bellek varsa, `(last - first) - 1` en iyi durum karşılaştırmalar ile doğrusal olur; yardımcı bellek kullanılabilir değilse, en kötü `N log(N)`durum, burada *N* = *son* - *birincsahiptir*.

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
    vector<int> v1;
    vector<int>::iterator Iter1, Iter2, Iter3;

    // Constructing vector v1 with default less-than ordering
    int i;
    for ( i = 0 ; i <= 5 ; i++ )
    {
        v1.push_back( i );
    }

    int ii;
    for ( ii =-5 ; ii <= 0 ; ii++ )
    {
        v1.push_back( ii );
    }

    cout << "Original vector v1 with subranges sorted by the\n "
            << "binary predicate less than is v1 = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")" << endl;

    // Constructing vector v2 with ranges sorted by greater
    vector<int> v2 ( v1 );
    vector<int>::iterator break2;
    break2 = find ( v2.begin( ), v2.end( ), -5 );
    sort ( v2.begin( ), break2 , greater<int>( ) );
    sort ( break2 , v2.end( ), greater<int>( ) );
    cout << "Original vector v2 with subranges sorted by the\n "
            << "binary predicate greater is v2 = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")" << endl;

    // Constructing vector v3 with ranges sorted by mod_lesser
    vector<int> v3 ( v1 );
    vector<int>::iterator break3;
    break3 = find ( v3.begin( ), v3.end( ), -5 );
    sort ( v3.begin( ), break3 , mod_lesser );
    sort ( break3 , v3.end( ), mod_lesser );
    cout << "Original vector v3 with subranges sorted by the\n "
            << "binary predicate mod_lesser is v3 = ( " ;
    for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")" << endl;

    vector<int>::iterator break1;
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
binary predicate less than is v1 = ( 0 1 2 3 4 5 -5 -4 -3 -2 -1 0 )
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

## <a name="is_heap"></a>is_heap

Belirtilen aralıktaki öğeler bir yığın oluşturbiliyorsa, **true** döndürür.

```cpp
template<class RandomAccessIterator>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
bool is_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);

template<class ExecutionPolicy, class RandomAccessIterator>
bool is_heap(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
bool is_heap(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir yığını denetlemek için aralığın başlangıcını belirten rastgele bir erişim Yineleyici.

*soyadına*\
Bir aralığın sonunu gösteren bir rastgele erişim Yineleyici.

*pred*\
Order öğelerini test etmek için bir koşul. Karşılaştırma koşulu iki bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Belirtilen aralıktaki öğeler bir yığın oluşturacaksa **true** , değilse **false** döndürür.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevi [is_heap_until](../standard-library/algorithm-functions.md#is_heap_until)`(first , last) == last`döndürür.

İkinci şablon işlevi şunu döndürür

`is_heap_until(first, last, pred) == last`.

## <a name="is_heap_until"></a>is_heap_until

Yığın sıralama koşulunu karşılamayan [ `first`, `last`) aralığındaki ilk öğede konumlandırılmış bir yineleyici döndürür veya Aralık bir yığın oluşturur.

```cpp
template<class RandomAccessIterator>
RandomAccessIterator is_heap_until(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
RandomAccessIterator is_heap_until(
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);

template<class ExecutionPolicy, class RandomAccessIterator>
RandomAccessIterator is_heap_until(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
RandomAccessIterator is_heap_until(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir yığını denetlemek için bir aralığın ilk öğesini belirten bir rastgele erişim Yineleyici.

*soyadına*\
Bir yığını denetlemek için aralığın sonunu belirten bir rastgele erişim Yineleyici.

*pred*\
Yığın tanımlayan katı zayıf sıralama koşulunu belirten bir ikili koşul. Varsayılan koşul, `std::less<>` *Pred* belirtilmediğinde belirlenir.

### <a name="return-value"></a>Dönüş değeri

Belirtilen Aralık bir yığın veya bir ya da daha az öğe içeriyorsa *son* döndürür. Aksi takdirde, yığın koşulunu karşılamayan bulunan ilk öğe için bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

`next` İlk şablon işlevi, `[first, last)` `std::less<>`içinde işlev nesnesi tarafından sıralanan yığın olaniçindekisonyineleyiciyidöndürür.`[first, next)` Uzaklık `last - first` 2 ' den küçükse, işlev *son*döndürür.

İkinci şablon işlevi, yığın sıralama koşulu yerine `std::less<>` *Pred* 'yi kullanması dışında, ilki ile aynı şekilde davranır.

## <a name="is_partitioned"></a>is_partitioned

Bir koşul için **doğru** test eden belirtilen aralıktaki tüm öğeler **false**test eden herhangi bir öğeden önce geliyorsa **true** döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
bool is_partitioned(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template <class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
bool is_partitioned(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir aralığın bir koşulu denetlemeye başladığı yeri gösteren bir giriş yineleyicisi.

*soyadına*\
Bir aralığın sonunu gösteren bir giriş yineleyicisi.

*pred*\
Sınanacak koşul. Bu, aranmakta olan öğe tarafından yerine getirilmesi gereken koşulu tanımlayan Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Bir koşul için **doğru** test eden belirtilen aralıktaki tüm öğelerin, **yanlış**test eden herhangi bir öğeden önce geldiği ve aksi durumda **false**döndürdüğünden, **true** döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yalnızca içindeki `[first, last)` tüm öğeler *Pred*tarafından bölümlenmiş ise true değerini döndürür `X` ; diğer bir `pred (X)` deyişle, `Y` içindeki `[first, last)` tüm öğeler `pred (Y)` **yanlış**.

## <a name="is_permutation"></a>is_permutation

Her iki Aralık de aynı öğeleri içeriyorsa, öğelerin aynı sırada olup olmadığına bakılmaksızın true döndürür. İkinci Aralık için yalnızca tek bir yineleyici alan aşırı yüklemeler ikinci aralığın ilk aralıktan daha uzun olması fark etmez ve ikinci Aralık daha kısaysa tanımsız davranışlara neden olacak şekilde, C++ 14 kodunda çift aralıklı aşırı yüklemeleri kullanın. ilk aralıktan fazla.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
bool is_permutation(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    BinaryPredicate Pred);

// C++14
template<class ForwardIterator1, class ForwardIterator2>
bool is_permutation(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
bool is_permutation(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*first1*\
Aralığın ilk öğesine başvuran bir ileri Yineleyici.

*last1*\
Aralığın son öğesinden bir geçen bir ileri Yineleyici.

*first2*\
Karşılaştırma için kullanılan ikinci bir aralığın ilk öğesine başvuran bir ileri Yineleyici.

*last2*\
Karşılaştırma için kullanılan ikinci bir aralığın son öğesinden bir geçen bir ileri Yineleyici.

*pred*\
Denklik için test eden ve **bool**döndüren bir koşul.

### <a name="return-value"></a>Dönüş değeri

aralıklar karşılaştırma koşuluna göre özdeş olacak şekilde yeniden düzenlenbiliyorsa, **true** . Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

`is_permutation`en kötü durumda büyük olasılıkla karmaşıklığa sahiptir.

İlk şablon işlevi, tarafından `[first1, last1)`belirlenen aralıkta olduğu gibi, *first2* adresinden başlayan aralıkta çok sayıda öğe olduğunu varsayar. İkinci aralıkta daha fazla öğe varsa, bunlar yok sayılır; daha az varsa, tanımsız bir davranış meydana gelir. Üçüncü şablon işlevi (C++ 14 ve üzeri) Bu varsayımını yapmaz. Her ikisi de **true değeri** yalnızca, x = = Y, *first2* veya `[first2, last2)`' `[first1, last1)` den başlayarak Aralık içinde olduğu gibi, x = = Y için aynı aralıkta bulunan her bir x öğesi için de geçerlidir. Burada, `operator==` işlenenleri arasında ikili bir karşılaştırma gerçekleştirmeniz gerekir.

İkinci ve dördüncü şablon işlevleri aynı şekilde davranır, ancak ile `operator==(X, Y)` `Pred(X, Y)`değiştirilir. Doğru şekilde davranması için koşul simetrik, yansımalı ve geçişli olmalıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını `is_permutation`gösterir:

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

## <a name="is_sorted"></a>is_sorted

Belirtilen aralıktaki öğeler sıralanmış sıradüzende ise, **true** döndürür.

```cpp
template<class ForwardIterator>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class Compare>
bool is_sorted(
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator>
bool is_sorted(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Compare>
bool is_sorted(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Denetlenecek aralığın başlayacağı konumu gösteren bir ileri Yineleyici.

*soyadına*\
Bir aralığın sonunu gösteren bir ileri Yineleyici.

*pred*\
İki öğe arasında bir sıra belirlenmesi için sınanacak koşul. Karşılaştırma koşulu iki bağımsız değişken alır ve **true** veya **false**değerini döndürür. Bu, ile `operator<`aynı görevi gerçekleştirir.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevi [is_sorted_until](#is_sorted_until)`( first, last ) == last`döndürür. `operator<` İşlev, sıra karşılaştırması gerçekleştirir.

İkinci şablon işlevi döndürür `is_sorted_until( first, last , pred ) == last`. *Pred* koşul işlevi, sıra karşılaştırması gerçekleştirir.

## <a name="is_sorted_until"></a>is_sorted_until

Belirtilen aralıktan `ForwardIterator` sıralanmış sırada olan son öğeye ayarlanmış bir döndürür.

İkinci sürüm, belirtilen iki öğe sıralanmış sırada olduğunda **true değeri** döndüren bir karşılaştırma işlevi nesnesi sağlamanıza olanak sağlar ve aksi takdirde **yanlış** olur.

```cpp
template<class ForwardIterator>
ForwardIterator is_sorted_until(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class Compare>
ForwardIterator is_sorted_until(
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator is_sorted_until(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Compare>
ForwardIterator is_sorted_until(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Denetlenecek aralığın nerede başlayacağını gösteren bir ileriye doğru yineleyici.

*soyadına*\
Bir aralığın sonunu gösteren bir ileri Yineleyici.

*pred*\
İki öğe arasında bir sıra belirlenmesi için sınanacak koşul. Karşılaştırma koşulu iki bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Sıralı düzende `ForwardIterator` son öğeye bir küme döndürür. Sıralanmış sıra *ilk*öğesinden başlar.

### <a name="remarks"></a>Açıklamalar

İlk `next` şablon işlevi ' de `[first, last]` son yineleyiciyi döndürür, bu `[first, next)` nedenle tarafından `operator<`sıralanan sıralanmış bir sıra. 2 ' den küçükse, işlev son ' u döndürür. `distance()`

İkinci şablon işlevi aynı şekilde davranır, ancak ile `operator<(X, Y)` `pred(X, Y)`değiştirilir.

## <a name="iter_swap"></a>iter_swap

Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
void iter_swap( ForwardIterator1 left, ForwardIterator2 right );
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Değeri değiş tokuş edilecek olan ileri yineleyicilerinin biri.

*Right*\
Değeri değiş tokuş edilecek olan ileri yineleyiciler ikincisinin ikincisi.

### <a name="remarks"></a>Açıklamalar

`swap`, geriye doğru uyumluluk için C++ standart olan **İter_swap**için tercih edilen tercihe göre kullanılmalıdır. Ve `Fit1` daha`Fit2` `swap( *Fit1, *Fit2 )`sonra yineleyicilervarsa,öğesineeşdeğerdir`iter_swap( Fit1, Fit2 )`.

Giriş iletme yineleyicilerinin değer türleri aynı değere sahip olmalıdır.

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
    vector<int> v1;
    vector<int>::iterator Iter1;
    deque<int> deq2;
    deque<int>::iterator d2_Iter;

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

## <a name="lexicographical_compare"></a>lexicographical_compare

Daha küçük olanı belirlemek için iki diziyi öğe öğe karşılaştırır.

```cpp
template<class InputIterator1, class InputIterator2>
bool lexicographical_compare(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2 );

template<class InputIterator1, class InputIterator2, class Compare>
bool lexicographical_compare(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
bool lexicographical_compare(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Compare>
bool lexicographical_compare(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Karşılaştırılacak ilk aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last1*\
Karşılaştırılacak ilk aralıktaki son öğeden önceki konumu ele aldığı bir giriş Yineleyici.

*first2*\
Karşılaştırılacak ikinci aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last2*\
Karşılaştırılan ikinci aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

ilk Aralık, ikinci aralıktan sözcüıgrafik küçükse **true** ; Aksi halde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Sıralar arasında bir lexicografik karşılaştırması, onları öğesine göre öğe ile karşılaştırır:

- Karşılık gelen iki öğeyi eşit olarak bulur ve karşılaştırma sonuçları diziler arasındaki karşılaştırma sonucu olarak alınır.

- Hiçbir inede bulunmadı, ancak bir dizide diğerinin daha fazla öğesi vardır ve daha kısa bir sıra daha uzun bir sıra daha küçüktür olarak kabul edilir.

- Herhangi bir inede bulunmadı ve diziler aynı sayıda öğeye sahip ve bu nedenle sıralar eşitse ve Karşılaştırmanın sonucu **false**.

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
    vector<int> v1, v2;
    list<int> L1;
    vector<int>::iterator Iter1, Iter2;
    list<int>::iterator L1_Iter, L1_inIter;

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

## <a name="lower_bound"></a>lower_bound

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
    BinaryPredicate pred );
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*soyadına*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*deeri*\
Düzenli aralıktaki ilk konumu veya olası ilk konumu aranmakta olan değer.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Belirtilen değere eşit veya ondan daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bir ileriye doğru yineleyici, burada denklik bir ikili koşula göre belirtilir.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralığı geçerli olmalıdır; tüm yineleyiciler, en başta artırılamadı 'e başvurulamamalıdır.

Sıralanmış bir Aralık, kullanmanın `lower_bound` önkoşuludur ve sıralama ikili koşula göre belirtilen şekilde aynıdır.

Aralık, algoritma `lower_bound`tarafından değiştirilmez.

İleriye doğru yineleyicilerin değer türlerinin sıralanabilmesi için kıyasla daha az karşılaştırılabilir olması gerekir. bu sayede, iki öğe verildiğinde, eşdeğer oldukları (Yani bunlardan daha küçük olmadığı anlamda) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, eşdeğer olmayan öğeler arasında bir sıralamaya neden olur

Algoritmanın karmaşıklığı Rastgele erişimli yineleyiciler ve doğrusal olarak, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle, (`last - first`) ile orantılıdır.

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
        v1.push_back( i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back( ii );
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
        << "binary predicate mod_lesser is v3 = ( " ;
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

    // lower_bound of 3 in v3 with the binary predicate mod_lesser
    Result = lower_bound(v3.begin(), v3.end(), 3, mod_lesser);
    cout << "The lower_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}
```

## <a name="make_heap"></a>make_heap

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
    BinaryPredicate pred );
```

### <a name="parameters"></a>Parametreler

*adı*\
Bir yığına dönüştürülecek aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Bir yığına dönüştürülecek aralıktaki son öğeden geçmiş bir konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Heap 'ler iki özelliğe sahiptir:

- İlk öğe her zaman en büyüktür.

- Öğeler, logaritmik bir zamanda eklenebilir veya kaldırılabilir.

Heap 'ler, öncelik kuyruklarını uygulamanın ideal bir yoludur ve C++ standart kitaplık kapsayıcı bağdaştırıcısı [priority_queue sınıfının](../standard-library/priority-queue-class.md)uygulamasında kullanılır.

Karmaşıklık, karşılaştırmalar gerektiren `3 * (last - first)` doğrusal bir değer.

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
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2;

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

## <a name="max"></a>Biçimlendir

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
    BinaryPredicate pred);
template<class Type>
constexpr Type& max (
    initializer_list<Type> ilist);
template<class Type, class Pr>
constexpr Type& max(
    initializer_list<Type> ilist,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Karşılaştırılan iki nesnenin ilki.

*Right*\
Karşılaştırılan iki nesnenin ikincisi.

*pred*\
İki nesneyi karşılaştırmak için kullanılan bir ikili koşul.

*liste tümce*\
Karşılaştırılacak nesneleri içeren Başlatıcı listesi.

### <a name="return-value"></a>Dönüş değeri

İki nesnenin daha büyük olması, hiçbiri daha büyük değilse; Bu durumda, iki nesnenin ilki döndürülür. Bir initializer_list söz konusu olduğunda, listedeki nesnelerin en büyük kısmını döndürür.

### <a name="remarks"></a>Açıklamalar

`max` Algoritma parametre olarak geçirilme sırasında olağandışı bir şekilde yapılır. Çoğu C++ standart kitaplık algoritmaları, konumu parametre olarak geçirilen yineleyiciler tarafından belirtilen bir dizi öğe üzerinde çalışır. Bir dizi öğe üzerinde çalışan bir işleve ihtiyacınız varsa, bunun yerine [max_element](../standard-library/algorithm-functions.md#max_element) kullanın. Visual Studio 2017, initializer_list alan aşırı yüklemelerin üzerinde **constexpr** 'yi sunar.

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
    vector<int> v1, v2, v3, v4, v5;
    vector<int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

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

## <a name="max_element"></a>max_element

Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator>
constexpr ForwardIterator max_element(
    ForwardIterator first,
    ForwardIterator last );

template<class ForwardIterator, class Compare>
constexpr ForwardIterator max_element(
    ForwardIterator first,
    ForwardIterator last,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator max_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Compare>
ForwardIterator max_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
En büyük öğe için aranacak aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*soyadına*\
En büyük öğe için Aranmak üzere aralıktaki son öğeden bir önceki konumu ele alarak ileriye doğru bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

Aranan aralıktaki en büyük öğenin ilk oluşum konumunu ele alarak ileriye doğru bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, her bir sırada bir kez başvurulmalıdır ve en son konum, artırılamadı tarafından ilk kez erişilebilir.

Karmaşıklık doğrusal: `(last - first) - 1` boş olmayan bir Aralık için karşılaştırmalar gereklidir.

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
    vector<int> v1;
    vector<int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

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

## <a name="merge"></a>birleþtirmek

İki sıralanmış kaynak aralığından tüm öğeleri, sıralama ölçütünün bir ikili koşula göre belirtilebileceği tek, sıralanmış bir hedef aralıkla birleştirir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator merge(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class Compare>
OutputIterator merge(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator>
ForwardIterator merge(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class Compare>
ForwardIterator merge(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Bir giriş yineleyicisi, birleştirilmiş iki kaynak aralıktaki ilk öğenin, birleştirilmek ve tek bir aralığa göre sıralanarak konumunu ele alıyor.

*last1*\
Bir giriş yineleyicisi, birleştirilmiş iki kaynak aralığın ilki olan son öğeden sonra tek bir aralığa göre sıralanarak konumunu ele alıyor.

*first2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında yer aldığı ve tek bir aralığa sıralanmış bir giriş Yineleyici.

*last2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında son öğeden geçen ve tek bir aralığa sıralanmış bir giriş Yineleyici.

*kaynaklanan*\
İkinci kaynak aralıklarının tek bir sıralanmış aralıkta birleştirileceği hedef aralıktaki ilk öğenin konumunu ele aldığı çıkış Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , değilse **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

Sıralanmış hedef aralıktaki son öğeden sonraki konumu ele alarak çıkış Yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Hedef Aralık, kaynak aralıklarından biriyle çakışmamalıdır ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralıklarının her biri, algoritma tarafından Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya uygun `merge` olarak, algoritmanın uygulamasına bir ön koşul olarak düzenlenmelidir.

Her aralıktaki öğelerin göreli sırası hedef aralıkta korunduğu için işlem kararlı değildir. Kaynak aralıkları algoritma `merge`tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için kıyasla daha az olması gerekir, böylece iki öğe söz konusu olduğunda, eşdeğer oldukları (Yani bunlardan daha küçük olmayan) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, ilk aralıktaki öğeler, hedef aralıktaki ikinci kaynak aralığından öğeden önce gelmelidir.

Algoritmanın karmaşıklığı, en çok `(last1 - first1) - (last2 - first2) - 1` karşılaştırmalar ile doğrusal olarak belirlenir.

[Liste sınıfı](../standard-library/list-class.md) , iki listenin öğelerini birleştirmek için "Merge" üye işlevini sağlar.

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
    vector<int> v1a, v1b, v1 ( 12 );
    vector<int>::iterator Iter1a, Iter1b, Iter1;

    // Constructing vector v1a and v1b with default less than ordering
    int i;
    for ( i = 0 ; i <= 5 ; i++ )
        v1a.push_back( i );

    int ii;
    for ( ii =-5 ; ii <= 0 ; ii++ )
        v1b.push_back( ii );

    cout << "Original vector v1a with range sorted by the\n "
            << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
            << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vector v2 with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
    vector<int>::iterator Iter2a, Iter2b, Iter2;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

    cout << "Original vector v2a with range sorted by the\n "
            << "binary predicate greater is   v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
            << "binary predicate greater is   v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vector v3 with ranges sorted by mod_lesser
    vector<int> v3a( v1a ), v3b( v1b ) , v3( v1 );
    vector<int>::iterator Iter3a, Iter3b, Iter3;
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
            << "binary predicate mod_lesser is   v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
            << "binary predicate mod_lesser is   v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To merge inplace in ascending order with default binary
    // predicate less<int>( )
    merge ( v1a.begin( ), v1a.end( ), v1b.begin( ), v1b.end( ), v1.begin( ) );
    cout << "Merged inplace with default order,\n vector v1mod = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // To merge inplace in descending order, specify binary
    // predicate greater<int>( )
    merge ( v2a.begin( ), v2a.end( ), v2b.begin( ), v2b.end( ),
        v2.begin( ), greater<int>( ) );
    cout << "Merged inplace with binary predicate greater specified,\n "
            << "vector v2mod = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // Applying A user-defined (UD) binary predicate mod_lesser
    merge ( v3a.begin( ), v3a.end( ), v3b.begin( ), v3b.end( ),
        v3.begin( ), mod_lesser );
    cout << "Merged inplace with binary predicate mod_lesser specified,\n "
            << "vector v3mod = ( " ; ;
    for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

## <a name="min"></a>Min

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
    BinaryPredicate pred);

template<class Type>
constexpr Type min(
    initializer_list<Type> ilist);

template<class Type, class Pr>
constexpr Type min(
    initializer_list<Type> ilist,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Karşılaştırılan iki nesnenin ilki.

*Right*\
Karşılaştırılan iki nesnenin ikincisi.

*pred*\
İki nesneyi karşılaştırmak için kullanılan bir ikili koşul.

*liste tümce*\
`initializer_list` Karşılaştırılacak üyeleri içeren.

### <a name="return-value"></a>Dönüş değeri

İki nesnenin daha küçük olması, ikisi de değilse; Bu durumda, iki nesnenin ilki döndürülür. Bir `initializer_list`durumunda, listedeki nesnelerin en az birini döndürür.

### <a name="remarks"></a>Açıklamalar

`min` Algoritma parametre olarak geçirilme sırasında olağandışı bir şekilde yapılır. Çoğu C++ standart kitaplık algoritmaları, konumu parametre olarak geçirilen yineleyiciler tarafından belirtilen bir dizi öğe üzerinde çalışır. Bir dizi öğe kullanan bir işleve ihtiyacınız varsa, [min_element](../standard-library/algorithm-functions.md#min_element)kullanın. [](../cpp/constexpr-cpp.md) Visual Studio 2017 ' deki `initializer_list` aşırı yüklemeler üzerinde constexpr etkinleştirildi.

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
    vector<int> v1, v2, v3, v4, v5;
    vector<int>::iterator Iter1, Iter2, Iter3, Iter4, Iter5;

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

## <a name="min_element"></a>min_element

Belirtilen bir aralıktaki en küçük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator>
constexpr ForwardIterator min_element(
    ForwardIterator first,
    ForwardIterator last );

template<class ForwardIterator, class Compare>
constexpr ForwardIterator min_element(
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator min_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Compare>
ForwardIterator min_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
En küçük öğe için aranacak aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*soyadına*\
En küçük öğe için Aranmak üzere aralıktaki son öğeden bir önceki konumu ele alarak ileriye doğru bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , değilse **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

Aranan aralıktaki en küçük öğenin ilk oluşum konumunu ele alarak ileriye doğru bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, her bir sırada bir kez başvurulmalıdır ve en son konum, artırılamadı tarafından ilk kez erişilebilir.

Karmaşıklık doğrusal: `(last - first) - 1` boş olmayan bir Aralık için karşılaştırmalar gereklidir.

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
    vector<int> v1;
    vector<int>::iterator v1_Iter, v1_R1_Iter, v1_R2_Iter;

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

## <a name="minmax_element"></a>minmax_element

`min_element` Ve`max_element` tek bir çağrıda gerçekleştirilen işleri gerçekleştirir.

```cpp
template<class ForwardIterator>
constexpr pair<ForwardIterator, ForwardIterator> minmax_element(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class Compare>
constexpr pair<ForwardIterator, ForwardIterator> minmax_element(
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator>
pair<ForwardIterator, ForwardIterator> minmax_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class Compare>
pair<ForwardIterator, ForwardIterator> minmax_element(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir aralığın başlangıcını gösteren bir ileri Yineleyici.

*soyadına*\
Bir aralığın sonunu gösteren bir ileri Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve ilki ikinciden küçükse **true** , aksi takdirde **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

Döndürür

`pair<ForwardIterator, ForwardIterator>( min_element(first, last), max_element(first, last))`.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevi şunu döndürür

`pair<ForwardIterator,ForwardIterator>(min_element(first,last), max_element(first,last))`.

İkinci şablon işlevi aynı şekilde davranır, ancak ile `operator<(X, Y)` `pred(X, Y)`değiştirilir.

Dizi boş değilse, işlev en çok `3 * (last - first - 1) / 2` karşılaştırmalarda gerçekleştirilir.

## <a name="minmax"></a>MinMax

İki giriş parametresini karşılaştırır ve bunları daha küçük bir şekilde bir çift olarak döndürür.

```cpp
template<class Type>
constexpr pair<const Type&, const Type&> minmax(
    const Type& left,
    const Type& right);

template<class Type, class BinaryPredicate>
constexpr pair<const Type&, const Type&> minmax(
    const Type& left,
    const Type& right,
    BinaryPredicate pred);

template<class Type>
constexpr pair<Type&, Type&> minmax(
    initializer_list<Type> ilist);

template<class Type, class BinaryPredicate>
constexpr pair<Type&, Type&> minmax(
    initializer_list<Type> ilist,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Karşılaştırılan iki nesnenin ilki.

*Right*\
Karşılaştırılan iki nesnenin ikincisi.

*pred*\
İki nesneyi karşılaştırmak için kullanılan bir ikili koşul.

*liste tümce*\
`initializer_list` Karşılaştırılacak üyeleri içeren.

### <a name="remarks"></a>Açıklamalar

Eğer *Right* , *Left*değerinden `pair<const Type&, const Type&>( right, left )` küçükse ilk şablon işlevi döndürür. Aksi takdirde, döndürür `pair<const Type&, const Type&>( left, right )`.

İkinci üye işlevi, ilk öğenin daha küçük olduğu bir çift döndürür ve ikinci değer *Pred*ile karşılaştırıldığında daha büyüktür.

Kalan şablon işlevleri, *sol* ve *sağ* parametrelerin *ınlist*ile yerini alacak şekilde aynı şekilde davranır.

İşlev tam olarak bir karşılaştırma gerçekleştirir.

## <a name="mismatch"></a>mez

İki Aralık öğesini öğesiyle karşılaştırır ve bir farkın gerçekleştiği ilk konumu bulur.

İkinci Aralık için yalnızca tek bir yineleyici alan aşırı yüklemeler ikinci aralığın ilk aralıktan daha uzun olması fark etmez ve ikinci Aralık daha kısaysa tanımsız davranışlara neden olacak şekilde, C++ 14 kodunda çift aralıklı aşırı yüklemeleri kullanın. ilk aralıktan fazla.

```cpp
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    BinaryPredicate pred );

//C++14
template<class InputIterator1, class InputIterator2>
pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2 );

template<class InputIterator1, class InputIterator2, class BinaryPredicate> pair<InputIterator1, InputIterator2>>
mismatch(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    BinaryPredicate pred);

//C++17
template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
pair<ForwardIterator1, ForwardIterator2>
mismatch(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
pair<ForwardIterator1, ForwardIterator2>
mismatch(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
pair<ForwardIterator1, ForwardIterator2>
mismatch(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
pair<ForwardIterator1, ForwardIterator2>
mismatch(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Sınanacak ilk aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*last1*\
Test edilecek ilk aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*first2*\
Test edilecek ikinci aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*last2*\
Test edilecek ikinci aralıktaki son öğeden bir önceki öğenin konumunu ele aldığı bir giriş Yineleyici.

*pred*\
Her aralıktaki geçerli öğeleri karşılaştıran ve eşdeğer olup olmadığını belirleyen Kullanıcı tanımlı koşul işlevi nesnesi. Memnun olmadığında **true** , **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

İki aralıktaki uyuşmazlığın konumlarını, ilk bileşen yineleyicisini ilk aralıktaki konuma ve ikinci bileşen yineleyicisini ikinci aralıktaki konuma adresleyen yineleyiciler çifti. Aralıklardaki öğeler arasında bir fark yoksa veya ikinci sürümdeki ikili koşulun iki aralıktaki tüm öğe çiftleri tarafından karşılanmasını içeriyorsa, ilk bileşen yineleyicisi ilk öğe için son öğeden önceki konuma işaret eder İkinci aralıkta test edilen son öğeden sonraki bir konumdan konumlandırmak için Aralık ve ikinci bileşen yineleyicisi.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlevi, [First1, last1) tarafından belirlenen aralıkta olduğu gibi, first2 adresinden başlayan aralıkta çok sayıda öğe olduğunu varsayar. İkinci aralıkta daha fazla varsa, bunlar yok sayılır; daha az varsa, tanımsız davranış sonucu olur.

Aranacak Aralık geçerli olmalıdır; tüm yineleyiciler başvurulmalıdır ve en son konuma artırılamadı tarafından ilk kez ulaşılabilir.

Algoritmanın zaman karmaşıklığı, daha kısa bir aralıktaki öğe sayısında doğrusal bir değer içerir.

Kullanıcı tanımlı koşul, işlenenleri arasında simetrik, yansımalı ve geçişli bir denklik ilişkisi uygulamak için gerekli değildir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, uyuşmazlığın nasıl kullanılacağını göstermektedir. C++ 03 aşırı yüklemesi yalnızca, nasıl beklenmeyen bir sonuç üretebileceğini göstermek için gösterilir.

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
```

```Output
C++03: vec_1 and vec_2 are a mismatch: false
C++14: vec_1 and vec_2: mismatch. Left iterator at end right iterator at 30
C++14 vec_1 v. vec_2 modified: mismatch. Left iterator at 15 right iterator at 42
C++14 vec_3 v. vec_4 with pred: match.
C++14 vec_3 v. modified vec_4 with pred: mismatch. Left iterator at 60 right iterator at 31
C++14: vec_1 and list_1 are a mismatch: false
Press a key
```

## <a name="alg_move"></a>&lt;algTaşı&gt;

Belirtilen aralıkla ilişkili öğeleri taşı.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator move(
    InputIterator first,
    InputIterator last,
    OutputIterator dest);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 move(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Taşınacak öğe aralığının nerede başlatılacağını gösteren bir giriş Yineleyici.

*soyadına*\
Taşınacak öğe aralığının sonunu gösteren bir giriş Yineleyici.

*HD*\
Taşınan öğeleri içeren çıkış yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, Aralık `*(dest + N) = move(*(first + N))` `N` `[0, last - first)`içinde her biri için bir kez değerlendirilir ve en düşük değer ile `N` başlangıç değerlerini kesin olarak artırır. Ardından döndürür `dest + N`. Ve `dest` *ilk* olarak depolama bölgelerini belirlerseniz, *hedef* Aralık `[first, last)`içinde olmamalıdır.

## <a name="move_backward"></a>move_backward

Bir yineleyicinin öğelerini diğerine taşır. Hareket belirli bir aralıktaki son öğeyle başlar ve söz konusu aralıktaki ilk öğeyle biter.

```cpp
template<class BidirectionalIterator1, class BidirectionalIterator2>
BidirectionalIterator2 move_backward(
    BidirectionalIterator1 first,
    BidirectionalIterator1 last,
    BidirectionalIterator2 destEnd);
```

### <a name="parameters"></a>Parametreler

*adı*\
Öğelerin taşınacağı aralığın başlangıcını gösteren bir yineleyici.

*soyadına*\
Öğelerin taşınacağı aralığın sonunu gösteren bir yineleyici. Bu öğe taşınmadı.

*destEnd*\
Hedef aralıkta son öğeden bir önceki öğenin konumunu belirleyen çift yönlü yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, Aralık `*(destEnd - N - 1) = move(*(last - N - 1))` `N` `[0, last - first)`içinde her biri için bir kez değerlendirilir ve en düşük değer ile `N` başlangıç değerlerini kesin olarak artırır. Ardından döndürür `destEnd - (last - first)`. *DestEnd* ve *ilk* olarak Storage bölgelerini belirlerseniz, *DestEnd* 'in aralıkta `[first, last)`olmaması gerekir.

`move`ve `move_backward` , bir taşıma yineleyicisi `copy` ile `copy_backward` , ve işlev ile eşdeğerdir.

## <a name="next_permutation"></a>next_permutation

Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.

```cpp
template<class BidirectionalIterator>
bool next_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
bool next_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aralıktaki ilk öğenin konumunu gösteren çift yönlü bir yineleyici.

*soyadına*\
Çift yönlü bir yineleyici, aralıktaki son öğeden geçmiş bir konuma işaret ediyor.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

lexıgrafiksel bir sonraki permütasyon varsa ve aralığın orijinal sıralamasını değiştirse **doğru** ; Aksi takdirde **yanlış**, bu durumda sıralama lexıgrafiksel en küçük permütasyon 'e dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Varsayılan ikili koşul değerinden küçüktür ve sonraki permütasyonun iyi tanımlanmış olduğundan emin olmak için aralıktaki öğelerin karşılaştırıdan küçük olması gerekir.

Karmaşıklık, en fazla `(last - first) / 2` takas ile doğrusal bir şekilde belirlenir.

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
    CInt( int n = 0 ) : m_nVal( n ) {}
    CInt( const CInt& rhs ) : m_nVal( rhs.m_nVal ) {}
    CInt& operator=( const CInt& rhs ) {m_nVal =
        rhs.m_nVal; return *this;}
    bool operator<( const CInt& rhs ) const
        { return ( m_nVal < rhs.m_nVal ); }
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
    vector<int> v1;
    vector<int>::iterator Iter1;

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
            cout << *Iter1 << " ";
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

## <a name="nth_element"></a>nth_element

Aralıktaki sıranın *n*. öğesini doğru bir şekilde bulur ve bu sayede dizideki tüm öğelerin bu değerden küçük veya ona eşit olması ve dizide izleyen tüm öğelerin bu değerden büyük veya ona eşit olması için bir dizi öğeyi bölümler.

```cpp
template<class RandomAccessIterator>
void nth_element(
    RandomAccessIterator first,
    RandomAccessIterator nth,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
void nth_element(
    RandomAccessIterator first,
    RandomAccessIterator nth,
    RandomAccessIterator last,
    Compare pred);

template<class ExecutionPolicy, class RandomAccessIterator>
void nth_element(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator nth,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
void nth_element(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator nth,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bölümlendirilmek üzere aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*dereceden*\
Bölümün sınırında doğru sıralanabilmesi için öğenin konumunu ele alan Rastgele erişimli bir yineleyici.

*soyadına*\
Bölümlendirilmek üzere aralıktaki son öğeden geçmiş bir konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Algoritma, n. öğesinin iki tarafındaki alt aralıklardaki öğelerin sıralanacağını garanti etmez. `nth_element` Bu sayede `partial_sort`, seçilen bazı öğelerin altındaki aralıktaki öğeleri sipariş eden ve alt aralığın sıralaması gerekmediği `partial_sort` zaman daha hızlı bir alternatif olarak kullanılabilen daha az garanti verir.

Öğeler eşdeğer, ancak eşit değildir, ancak ikisi de küçüktür.

Sıralama karmaşıklığına ilişkin ortalama, *en son birinciyle*karşılaştırıldığında doğrusal bir şekilde belirlenir.

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
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="none_of"></a>none_of

Verilen aralıktaki öğeler arasında hiçbir zaman bir koşul mevcut olmadığında **true** döndürür.

```cpp
template<class InputIterator, class UnaryPredicate>
bool none_of(
    InputIterator first,
    InputIterator last,
    UnaryPredicate pred);

template <class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
bool none_of(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir koşul için bir dizi öğeyi denetlemeye nereden başlayacağını belirten bir giriş Yineleyici.

*soyadına*\
Bir öğe aralığının sonunu gösteren bir giriş Yineleyici.

*pred*\
Sınanacak koşul. Bu, koşulu tanımlayan Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşul, belirtilen aralıkta en az bir kez saptanmamışsa **true** , koşul algılanırsa **false** değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi yalnızca `N` , Aralık `[0, last - first)`içinde, `pred(*(first + N))` koşul her zaman **false**olduğunda **true** döndürür.

## <a name="partial_sort"></a>partial_sort

Bir aralıktaki daha küçük öğelerin belirtilen sayısını azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class RandomAccessIterator>
void partial_sort(
    RandomAccessIterator first,
    RandomAccessIterator sortEnd,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
void partial_sort(
    RandomAccessIterator first,
    RandomAccessIterator sortEnd,
    RandomAccessIterator last
    Compare pred);

template<class ExecutionPolicy, class RandomAccessIterator>
void partial_sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator middle,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
void partial_sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator middle,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*sortEnd*\
Sıralama yapılacak alt aralıktaki son öğeden bir önceki konumu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Kısmen sıralanacak aralıktaki son öğeden geçmiş bir konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Öğeler eşdeğer, ancak eşit değildir, ancak ikisi de küçüktür. `sort` Algoritma kararlı değildir ve denk öğelerin göreli sıralamasına karşı korunmayacağını garanti etmez. Algoritma `stable_sort` bu orijinal sıralamayı korur.

Ortalama Kısmi sıralama karmaşıklığı *O*`last`((`first`- ) log (`sortEnd`- ))`first`.

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
    vector<int> v1;
    vector<int>::iterator Iter1;

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
    partial_sort(v1.begin( ), v1.begin( ) + 8, v1.end( ), UDgreater );
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

## <a name="partial_sort_copy"></a>partial_sort_copy

Öğeleri bir kaynak aralığından bir hedef aralığa kopyalar, burada kaynak öğeleri daha küçük olana ya da belirtilen başka bir ikili koşula göre sıralanır.

```cpp
template<class InputIterator, class RandomAccessIterator>
RandomAccessIterator partial_sort_copy(
    InputIterator first1,
    InputIterator last1,
    RandomAccessIterator first2,
    RandomAccessIterator last2 );

template<class InputIterator, class RandomAccessIterator, class Compare>
RandomAccessIterator partial_sort_copy(
    InputIterator first1,
    InputIterator last1,
    RandomAccessIterator first2,
    RandomAccessIterator last2,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator, class RandomAccessIterator>
RandomAccessIterator partial_sort_copy(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    RandomAccessIterator result_first,
    RandomAccessIterator result_last);

template<class ExecutionPolicy, class ForwardIterator, class RandomAccessIterator, class Compare>
RandomAccessIterator partial_sort_copy(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    RandomAccessIterator result_first,
    RandomAccessIterator result_last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Kaynak aralıktaki ilk öğenin konumunu ele aldığı bir giriş Yineleyici.

*last1*\
Kaynak aralıktaki son öğeden sonraki konumu ele aldığı bir giriş Yineleyici.

*first2*\
Sıralanmış hedef aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*last2*\
Sıralanmış hedef aralıktaki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Hedef aralıktaki öğeyi, kaynak aralıktan açılan son öğeden sonraki bir konuma adresleyen Rastgele erişimli bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef aralıklar çakışmamalı ve geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Eşdeğer olmayan öğelerin sıralanabilmesi, ancak eşdeğer olan öğelerin olmaması için ikili koşulun katı zayıf bir sıralama sağlaması gerekir. İki öğe küçüktür, ancak eşit değildir, ancak ikisi de küçüktür.

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

## <a name="partition"></a>bölümünüzün

Bir aralıktaki öğeleri, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

```cpp
template<class BidirectionalIterator, class UnaryPredicate>
BidirectionalIterator partition(
    BidirectionalIterator first,
    BidirectionalIterator last,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
ForwardIterator partition(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bölümlendirilmek üzere aralıktaki ilk öğenin konumunu ele alarak çift yönlü bir yineleyici.

*soyadına*\
Bölümlendirilmek üzere aralıktaki son öğeden geçmiş bir konumu ele alarak çift yönlü bir yineleyici.

*pred*\
Bir öğe sınıflandırılabildiğinde karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşul koşulunu yerine getirmek için aralıktaki ilk öğenin konumunu ele alarak çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

*A* ve *b* öğeleri eşdeğerdir, ancak her ikisi de false ise eşit değildir `pred( a, b )` ve `pred( b, a )` false ise, her ikisi de parametre belirtilen *koşul olur.* `partition` Algoritma kararlı değildir ve denk öğelerin göreli sıralamasına karşı korunmayacağını garanti etmez. Algoritma `stable_partition` bu orijinal sıralamayı korur.

Karmaşıklık doğrusal değildir: *Pred* ve `(last - first)` en çok `(last - first)/2` takas eden uygulamalar vardır.

### <a name="example"></a>Örnek

```cpp
// alg_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value )
{
    return value > 5;
}

int main()
{
    using namespace std;
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2;

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

## <a name="partition_copy"></a>partition_copy

, Koşulun bir hedefe **doğru** olması için ve koşulun **yanlış** olduğu bir diğerinin olduğu öğeleri kopyalar. Öğeler belirtilen bir aralıktan gelmelidir.

```cpp
template<class InputIterator, class OutputIterator1, class OutputIterator2, class UnaryPredicate>
pair<OutputIterator1, OutputIterator2> partition_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator1 dest1,
    OutputIterator2 dest2,
    UnaryPredicate pred);

template <class ExecutionPolicy, class ForwardIterator, class ForwardIterator1, class ForwardIterator2, class UnaryPredicate>
pair<ForwardIterator1, ForwardIterator2> partition_copy(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    ForwardIterator1 out_true,
    ForwardIterator2 out_false,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir koşulu denetlemek için aralığın başlangıcını gösteren bir giriş Yineleyici.

*soyadına*\
Bir aralığın sonunu gösteren bir giriş yineleyicisi.

*dest1*\
*Pred*kullanılarak test edilen bir koşul için doğru döndüren öğeleri kopyalamak için kullanılan bir çıkış yineleyicisi.

*dest2*\
*Pred*kullanılarak test edilen bir koşul için yanlış döndüren öğeleri kopyalamak için kullanılan bir çıkış yineleyicisi.

*pred*\
Sınanacak koşul. Bu, test edilecek koşulu tanımlayan Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, true ise, `X` veya `[first,last)` `*dest1++` `pred(X)` değilse`*dest2++` öğesine öğesine her öğeyi kopyalar. Döndürür `pair<OutputIterator1, OutputIterator2>(dest1, dest2)`.

## <a name="partition_point"></a>partition_point

Koşulu karşılamayan verili aralıktaki ilk öğeyi döndürür. Öğeler koşulu karşılayanlar karşılamayanlardan önce gelecek şekilde sıralanır.

```cpp
template<class ForwardIterator, class UnaryPredicate>
ForwardIterator partition_point(
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Bir `ForwardIterator` koşulu denetlemek için aralığın başlangıcını belirten bir.

*soyadına*\
Bir `ForwardIterator` aralığın sonunu gösteren bir.

*pred*\
Sınanacak koşul. Bu, aranmakta olan öğe tarafından yerine getirilmesi gereken koşulu tanımlayan Kullanıcı tanımlı bir koşul işlevi nesnesi tarafından sağlanır. Birli koşul tek bir bağımsız değişken alır ve **true** veya **false**değerini döndürür.

### <a name="return-value"></a>Dönüş değeri

`ForwardIterator` *Pred*tarafından test edilmiş koşulu yerine getirmeyen ilk öğeye başvuran bir döndürür veya bir tane bulunamazsa *son* ' u döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `it` ' de **false**' `[first, last)` `pred(*it)` olan ilk yineleyiciyi bulur. Sıra, *Pred*tarafından sıralanmalıdır.

## <a name="pop_heap"></a>pop_heap

En büyük öğeyi bir yığının önünden aralıktaki bir sonraki son konuma kaldırır ve ardından kalan öğelerden yeni bir yığın oluşturur.

```cpp
template<class RandomAccessIterator>
void pop_heap(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class BinaryPredicate>
void pop_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Yığın içindeki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Yığın içindeki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

`pop_heap` Algoritma, Push_heap algoritması tarafından gerçekleştirilen işlemin tersidir, bu, bir aralığın bir sonraki-son konumundaki bir öğenin aralıktaki önceki öğelerden oluşan bir yığına eklendiği, bu durumda öğe, yığın, yığında zaten bulunan öğelerden daha büyük.

Heap 'ler iki özelliğe sahiptir:

- İlk öğe her zaman en büyüktür.

- Öğeler, logaritmik bir zamanda eklenebilir veya kaldırılabilir.

Heap 'ler, öncelik kuyruklarını uygulamanın ideal bir yoludur ve C++ standart kitaplık kapsayıcı bağdaştırıcısı [priority_queue sınıfının](../standard-library/priority-queue-class.md)uygulamasında kullanılır.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Sonundaki yeni eklenen öğeyi hariç tutma bir yığın olmalıdır.

Karmaşıklık, en çok `log (last - first)` karşılaştırmaların gerektirmesi için karmaşıktır.

### <a name="example"></a>Örnek

```cpp
// alg_pop_heap.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1, Iter2;

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

## <a name="prev_permutation"></a>prev_permutation

Bir aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama, varsa sözcüıgrafik önceki daha büyük permütasyon ile değiştirilmelidir, bu durumda Previous 'in anlamı bir ikili koşula göre belirtilebilir.

```cpp
template<class BidirectionalIterator>
bool prev_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last);

template<class BidirectionalIterator, class BinaryPredicate>
bool prev_permutation(
    BidirectionalIterator first,
    BidirectionalIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aralıktaki ilk öğenin konumunu gösteren çift yönlü bir yineleyici.

*soyadına*\
Çift yönlü bir yineleyici, aralıktaki son öğeden geçmiş bir konuma işaret ediyor.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

lexıgrafik önceki permütasyon varsa ve aralığın orijinal sıralamasını değiştirse **doğru** ; Aksi takdirde **yanlış**, bu durumda sıralama lexıgrafiksel en büyük PERMÜTASYONA dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Varsayılan ikili koşul değerinden küçüktür ve önceki permütasyon 'nin iyi tanımlanmış olduğundan emin olmak için aralıktaki öğelerin karşılaştırılabilir olması gerekir.

Karmaşıklık, en çok (`last` - `first`)/2 takas ile doğrusal bir değer.

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

int main()
{
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
    vector<int> v1;
    vector<int>::iterator Iter1;

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
            cout << *Iter1 << " ";
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

## <a name="push_heap"></a>push_heap

Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.

```cpp
template<class RandomAccessIterator>
void push_heap(
    RandomAccessIterator first,
    RandomAccessIterator last );

template<class RandomAccessIterator, class BinaryPredicate>
void push_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Yığın içindeki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Bir yığına dönüştürülecek aralıktaki son öğeden geçmiş bir konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Öğe önce var olan bir yığının sonuna geri itilmeli ve ardından bu öğeyi mevcut yığına eklemek için algoritma kullanılır.

Heap 'ler iki özelliğe sahiptir:

- İlk öğe her zaman en büyüktür.

- Öğeler, logaritmik bir zamanda eklenebilir veya kaldırılabilir.

Heap 'ler, öncelik kuyruklarını uygulamanın ideal bir yoludur ve C++ standart kitaplık kapsayıcı bağdaştırıcısı [priority_queue sınıfının](../standard-library/priority-queue-class.md)uygulamasında kullanılır.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Sonundaki yeni eklenen öğeyi hariç tutma bir yığın olmalıdır.

Karmaşıklık, en çok `log(last - first)` karşılaştırmaların gerektirmesi için karmaşıktır.

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
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2;

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

## <a name="random_shuffle"></a>random_shuffle

Std:: random_shuffle () işlevi kullanım dışıdır ve [std:: karıştır](../standard-library/algorithm-functions.md#shuffle)ile değiştirilmiştir. Bir kod örneği ve daha fazla bilgi için, bkz [ \<. Random >](../standard-library/random.md) ve Stack Overflow Post, [c++ 14 ' te neden kullanım dışı bırakılıyor?](https://go.microsoft.com/fwlink/p/?linkid=397954).

## <a name="remove"></a>temizlenmesine

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki belirtilen bir değeri ortadan kaldırır.

```cpp
template<class ForwardIterator, class Type>
ForwardIterator remove(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Type>
ForwardIterator remove(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin kaldırıldığı aralıktaki ilk öğenin konumunu ele veren ileriye doğru bir yineleyici.

*soyadına*\
Öğelerin kaldırıldığı aralıktaki son öğeden bir önceki konumu ele veren ileriye doğru bir yineleyici.

*deeri*\
Aralıktan kaldırılacak değer.

### <a name="return-value"></a>Dönüş değeri

Değiştirilen aralığın yeni bitiş konumunu ele aldığı bir ileriye doğru yineleyici, bir tane, belirtilen değerin en son öğesi boş olan bir sonraki dizi öğesidir.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Kaldırılmayan öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal; eşitlik için karşılaştırmalar`last`( - `first`) vardır.

[Liste sınıfının](../standard-library/list-class.md) daha verimli bir üye işlev sürümü `remove`vardır ve bu da işaretçileri yeniden bağlar.

### <a name="example"></a>Örnek

```cpp
// alg_remove.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1, Iter2, new_end;

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

## <a name="remove_copy"></a>remove_copy

Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator remove_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
ForwardIterator2 remove_copy(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin kaldırıldığı aralıktaki ilk öğenin konumunu ele veren bir giriş Yineleyici.

*soyadına*\
Öğelerin kaldırıldığı aralıktaki son öğeden önceki konumu ele veren bir giriş Yineleyici.

*kaynaklanan*\
Bir çıkış yineleyicisi, öğelerin kaldırıldığı hedef aralıktaki ilk öğenin konumunu ele alıyor.

*deeri*\
Aralıktan kaldırılacak değer.

### <a name="return-value"></a>Dönüş değeri

Hedef aralığın yeni bitiş konumunu ele alarak bir ileri Yineleyici, belirtilen değerin Remnant sırasının bir kopyasının son öğesinden geçmiş.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıkları geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Hedef aralıkta, belirtilen değerin öğeleri kaldırıldıktan sonra kopyalanacak Remnant öğelerini içerecek kadar yeterli alan olması gerekir.

Kaldırılmayan öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal; eşitlik ve en`last`çok ( - `first``last`)atamalariçin()karşılaştırmalarvardır. - `first`

### <a name="example"></a>Örnek

```cpp
// alg_remove_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1, v2(10);
    vector<int>::iterator Iter1, Iter2, new_end;

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

## <a name="remove_copy_if"></a>remove_copy_if

Bir koşulu karşılayan öğeler hariç, bir kaynak aralıktaki öğeleri bir hedef aralığa kopyalar. Öğeler kalan öğelerin sırasını bozmadan kopyalanır. Yeni bir hedef aralığın sonunu döndürür.

```cpp
template<class InputIterator, class OutputIterator, class UnaryPredicate>
OutputIterator remove_copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class UnaryPredicate>
ForwardIterator2 remove_copy_if(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin kaldırıldığı aralıktaki ilk öğenin konumunu ele veren bir giriş Yineleyici.

*soyadına*\
Öğelerin kaldırıldığı aralıktaki son öğeden önceki konumu ele veren bir giriş Yineleyici.

*kaynaklanan*\
Bir çıkış yineleyicisi, öğelerin kaldırıldığı hedef aralıktaki ilk öğenin konumunu ele alıyor.

*pred*\
Karşılanması gereken birli koşul, bir öğenin değerinin değiştirilmesini sağlar.

### <a name="return-value"></a>Dönüş değeri

Hedef aralığın yeni bitiş konumunu ele eden bir ileriye doğru yineleyici, bir tane, koşulun yerine geçen öğelerin boş olan Remnant dizisinin son öğesi.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak aralığı geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Hedef aralıkta, belirtilen değerin öğeleri kaldırıldıktan sonra kopyalanacak Remnant öğelerini içerecek kadar yeterli alan olması gerekir.

Kaldırılmayan öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal: eşitlik ve en çok (`last``last``first` -  - )atamalarayönelikkarşılaştırmalarvardır`first`.

Bu işlevlerin nasıl davrandığına ilişkin bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

int main()
{
    using namespace std;
    vector<int> v1, v2(10);
    vector<int>::iterator Iter1, Iter2, new_end;

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

## <a name="remove_if"></a>remove_if

Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki bir koşulu karşılayan öğeleri ortadan kaldırır.

```cpp
template<class ForwardIterator, class UnaryPredicate>
ForwardIterator remove_if(
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate>
ForwardIterator remove_if(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin kaldırıldığı aralıktaki ilk öğenin konumunu işaret eden ileriye doğru bir yineleyici.

*soyadına*\
Bir ileri Yineleyici, öğelerin kaldırıldığı aralıktaki son öğeden bir önceki konumu işaret ediyor.

*pred*\
Karşılanması gereken birli koşul, bir öğenin değerinin değiştirilmesini sağlar.

### <a name="return-value"></a>Dönüş değeri

Değiştirilen aralığın yeni bitiş konumunu ele aldığı bir ileriye doğru yineleyici, bir tane, belirtilen değerin en son öğesi boş olan bir sonraki dizi öğesidir.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Kaldırılmayan öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal: eşitlik için (`last` - `first`) karşılaştırmalar vardır.

Listenin, yeniden bağlantı işaretçilerini Kaldır ' ın daha verimli bir üye işlev sürümü vardır.

### <a name="example"></a>Örnek

```cpp
// alg_remove_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value )
{
    return value > 6;
}

int main()
{
    using namespace std;
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2, new_end;

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

## <a name="replace"></a>değiştirin

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir değerle eşleşiyorsa değiştirir.

```cpp
template<class ForwardIterator, class Type>
void replace(
    ForwardIterator first,
    ForwardIterator last,
    const Type& oldVal,
    const Type& newVal);

template<class ExecutionPolicy, class ForwardIterator, class Type>
void replace(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    const Type& oldVal,
    const Type& newVal);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin değiştirildiği aralıktaki ilk öğenin konumunu işaret eden ileri Yineleyici.

*soyadına*\
İleri Yineleyici, öğelerin değiştirilmekte olduğu aralıktaki son öğeden geçmiş bir konuma işaret ediyor.

*oldVal*\
Değiştirilmekte olan öğelerin eski değeri.

*newVal*\
Eski değer ile öğelere atanmakta olan yeni değer.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Değiştirilmeyen öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal;  - `last``first`eşitlik için karşılaştırmalar ve yeni değerlerin en çok () atamaları vardır.`last` - `first`

### <a name="example"></a>Örnek

```cpp
// alg_replace.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="replace_copy"></a>replace_copy

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.

```cpp
template<class InputIterator, class OutputIterator, class Type>
OutputIterator replace_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    const Type& oldVal,
    const Type& newVal);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class Type>
ForwardIterator2 replace_copy(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    const Type& oldVal,
    const Type& newVal);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin değiştirildiği aralıktaki ilk öğenin konumunu gösteren bir giriş Yineleyici.

*soyadına*\
Bir giriş yineleyicisi, öğelerin değiştirildiği aralıktaki son öğeden önceki konuma işaret ediyor.

*kaynaklanan*\
Değiştirilen öğe sırasının kopyalandığı hedef aralıktaki ilk öğeyi gösteren bir çıkış yineleyicisi.

*oldVal*\
Değiştirilmekte olan öğelerin eski değeri.

*newVal*\
Eski değer ile öğelere atanmakta olan yeni değer.

### <a name="return-value"></a>Dönüş değeri

Bir çıkış yineleyicisi, hedef aralıktaki son öğeden geçen bir konuma işaret eden, değiştirilen öğe dizisi öğesine kopyalanır.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıkları çakışmamalı ve her ikisi de geçerli olmalıdır: tüm işaretçiler, artırılamadı tarafından ilk konumun erişilebilir olması gerekir.

Değiştirilmeyen öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal: eşitlik`last`için ( - `first`) ve yeni değerlerin en çok (`last` - `first`) atamalarına yönelik karşılaştırmalar vardır.

### <a name="example"></a>Örnek

```cpp
// alg_replace_copy.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    list<int> L1 (15);
    vector<int>::iterator Iter1;
    list<int>::iterator L_Iter1;

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

## <a name="replace_copy_if"></a>replace_copy_if

Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.

```cpp
template<class InputIterator, class OutputIterator, class UnaryPredicate, class Type>
OutputIterator replace_copy_if(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    UnaryPredicate pred,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class UnaryPredicate, class Type>
ForwardIterator2 replace_copy_if(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    UnaryPredicate pred,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin değiştirildiği aralıktaki ilk öğenin konumunu gösteren bir giriş Yineleyici.

*soyadına*\
Bir giriş yineleyicisi, öğelerin değiştirildiği aralıktaki son öğeden önceki konuma işaret ediyor.

*kaynaklanan*\
Bir çıkış yineleyicisi, öğelerin kopyalandığı hedef aralıktaki ilk öğenin konumunu işaret eder.

*pred*\
Karşılanması gereken birli koşul, bir öğenin değerinin değiştirilmesini sağlar.

*deeri*\
Eski değeri koşulu karşılayan öğelere atanmakta olan yeni değer.

### <a name="return-value"></a>Dönüş değeri

Bir çıkış yineleyicisi, hedef aralıktaki son öğeden geçen bir konuma işaret eden, değiştirilen öğe dizisi öğesine kopyalanır.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıkları çakışmamalı ve her ikisi de geçerli olmalıdır: tüm işaretçiler, artırılamadı tarafından ilk konumun erişilebilir olması gerekir.

Değiştirilmeyen öğelerin sırası kararlı kalır.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal;  - `last``first`eşitlik için karşılaştırmalar ve yeni değerlerin en çok () atamaları vardır.`last` - `first`

### <a name="example"></a>Örnek

```cpp
// alg_replace_copy_if.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>

bool greater6 ( int value )
{
    return value > 6;
}

int main()
{
    using namespace std;
    vector<int> v1;
    list<int> L1 (13);
    vector<int>::iterator Iter1;
    list<int>::iterator L_Iter1;

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

## <a name="replace_if"></a>replace_if

Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.

```cpp
template<class ForwardIterator, class UnaryPredicate, class Type>
void replace_if(
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class UnaryPredicate, class Type>
void replace_if(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    UnaryPredicate pred,
    const Type& value);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin değiştirildiği aralıktaki ilk öğenin konumunu işaret eden ileri Yineleyici.

*soyadına*\
Öğelerin değiştirilmekte olduğu aralıktaki son öğeden önceki konuma işaret eden bir yineleyici.

*pred*\
Karşılanması gereken birli koşul, bir öğenin değerinin değiştirilmesini sağlar.

*deeri*\
Eski değeri koşulu karşılayan öğelere atanmakta olan yeni değer.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Değiştirilmeyen öğelerin sırası kararlı kalır.

Algoritma `replace_if` , belirli bir sabit değere eşitlik yerine `replace`her koşulun belirtilmesini sağlayan algoritmanın genelleştirmesidir.

Öğeler `operator==` arasındaki eşitliğin belirlenmesi için kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Karmaşıklık doğrusal: eşitlik`last`için ( - `first`) ve yeni değerlerin en çok (`last` - `first`) atamalarına yönelik karşılaştırmalar vardır.

### <a name="example"></a>Örnek

```cpp
// alg_replace_if.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater6 ( int value )
{
    return value > 6;
}

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="reverse"></a>tersini

Bir aralık içindeki öğelerin sırasını tersine çevirir.

```cpp
template<class BidirectionalIterator>
void reverse(
    BidirectionalIterator first,
    BidirectionalIterator last);

template<class ExecutionPolicy, class BidirectionalIterator>
void reverse(
    ExecutionPolicy&& exec,
    BidirectionalIterator first,
    BidirectionalIterator last);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Öğelerin daha fazla kapalı olduğu aralıktaki ilk öğenin konumunu gösteren çift yönlü bir yineleyici.

*soyadına*\
Öğelerin, öğelerin en son kullanıldığı aralıktaki son öğeden geçmiş bir konuma işaret eden çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak aralığı geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

### <a name="example"></a>Örnek

```cpp
// alg_reverse.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="reverse_copy"></a>reverse_copy

Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine çevirir

```cpp
template<class BidirectionalIterator, class OutputIterator>
OutputIterator reverse_copy(
    BidirectionalIterator first,
    BidirectionalIterator last,
    OutputIterator result);

template<class ExecutionPolicy, class BidirectionalIterator, class ForwardIterator>
ForwardIterator reverse_copy(
    ExecutionPolicy&& exec,
    BidirectionalIterator first,
    BidirectionalIterator last,
    ForwardIterator result);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir çift yönlü yineleyiciden, öğelerin bir aralıktaki ilk öğenin konumunu gösteren bir çift yönlü Yineleyici.

*soyadına*\
Çift yönlü bir yineleyici, öğelerin, öğelerin, içindeki son öğeden en sonda yer aldığı bir konuma işaret ediyor.

*kaynaklanan*\
Bir çıkış yineleyicisi, öğelerin kopyalandığı hedef aralıktaki ilk öğenin konumunu işaret eder.

### <a name="return-value"></a>Dönüş değeri

Bir çıkış yineleyicisi, hedef aralıktaki son öğeden geçen bir konuma işaret eden, değiştirilen öğe dizisi öğesine kopyalanır.

### <a name="remarks"></a>Açıklamalar

Başvurulan kaynak ve hedef aralıkları geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

### <a name="example"></a>Örnek

```cpp
// alg_reverse_copy.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1, v2( 10 );
    vector<int>::iterator Iter1, Iter2;

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

## <a name="rotate"></a>Boyut

İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.

```cpp
template<class ForwardIterator>
void rotate(
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator rotate(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir ileri Yineleyici, döndürülmek üzere aralıktaki ilk öğenin konumunu ele alıyor.

*Beceri*\
Aralığı içindeki ilk öğenin, öğeleri aralığın ilk bölümünde olacak şekilde değiştirilecek olan aralığın ikinci parçasındaki konumunu tanımlayan bir ileriye doğru yineleyici.

*soyadına*\
Bir ileri Yineleyici, döndürülmek üzere aralıktaki son öğeden sonraki konumu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Karmaşıklık, en çok (`last` - `first`) değiştirmeleri ile doğrusal bir değer.

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
    vector<int> v1;
    deque<int> d1;
    vector<int>::iterator v1Iter1;
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
        cout << *v1Iter1 << " ";
    cout << ")." << endl;

    rotate ( v1.begin( ), v1.begin( ) + 3 , v1.end( ) );
    cout << "After rotating, vector v1 is ( " ;
    for ( v1Iter1 = v1.begin( ) ; v1Iter1 != v1.end( ) ;v1Iter1 ++ )
        cout << *v1Iter1 << " ";
    cout << ")." << endl;

    cout << "The original deque d1 is ( " ;
    for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
        cout << *d1Iter1 << " ";
    cout << ")." << endl;

    int iii = 1;
    while ( iii <= d1.end( ) - d1.begin( ) ) {
        rotate ( d1.begin( ), d1.begin( ) + 1 , d1.end( ) );
        cout << "After the rotation of a single deque element to the back,\n d1 is   ( " ;
        for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
            cout << *d1Iter1 << " ";
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

## <a name="rotate_copy"></a>rotate_copy

Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.

```cpp
template<class ForwardIterator, class OutputIterator>
OutputIterator rotate_copy(
    ForwardIterator first,
    ForwardIterator middle,
    ForwardIterator last,
    OutputIterator result );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 rotate_copy(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 middle,
    ForwardIterator1 last,
    ForwardIterator2 result);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bir ileri Yineleyici, döndürülmek üzere aralıktaki ilk öğenin konumunu ele alıyor.

*Beceri*\
Aralığı içindeki ilk öğenin, öğeleri aralığın ilk bölümünde olacak şekilde değiştirilecek olan aralığın ikinci parçasındaki konumunu tanımlayan bir ileriye doğru yineleyici.

*soyadına*\
Bir ileri Yineleyici, döndürülmek üzere aralıktaki son öğeden sonraki konumu ele alıyor.

*kaynaklanan*\
Hedef aralıktaki ilk öğenin konumunu ele alarak çıkış Yineleyici.

### <a name="return-value"></a>Dönüş değeri

Hedef aralıktaki son öğeden sonraki konumu ele alarak çıkış Yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Karmaşıklık, en çok (`last` - `first`) değiştirmeleri ile doğrusal bir değer.

### <a name="example"></a>Örnek

```cpp
// alg_rotate_copy.cpp
// compile with: /EHsc
#include <vector>
#include <deque>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;
    vector<int> v1 , v2 ( 9 );
    deque<int> d1 , d2 ( 6 );
    vector<int>::iterator v1Iter , v2Iter;
    deque<int>::iterator d1Iter , d2Iter;

    int i;
    for ( i = -3 ; i <= 5 ; i++ )
        v1.push_back( i );

    int ii;
    for ( ii =0 ; ii <= 5 ; ii++ )
        d1.push_back( ii );

    cout << "Vector v1 is ( " ;
    for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
        cout << *v1Iter << " ";
    cout << ")." << endl;

    rotate_copy ( v1.begin( ), v1.begin( ) + 3 , v1.end( ), v2.begin( ) );
    cout << "After rotating, the vector v1 remains unchanged as:\n v1 = ( " ;
    for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ;v1Iter ++ )
        cout << *v1Iter << " ";
    cout << ")." << endl;

    cout << "After rotating, the copy of vector v1 in v2 is:\n v2 = ( " ;
    for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ;v2Iter ++ )
        cout << *v2Iter << " ";
    cout << ")." << endl;

    cout << "The original deque d1 is ( " ;
    for ( d1Iter = d1.begin( ) ; d1Iter != d1.end( ) ;d1Iter ++ )
        cout << *d1Iter << " ";
    cout << ")." << endl;

    int iii = 1;
    while ( iii <= d1.end( ) - d1.begin( ) )
    {
        rotate_copy ( d1.begin( ), d1.begin( ) + iii , d1.end( ), d2.begin( ) );
        cout << "After the rotation of a single deque element to the back,\n d2 is   ( " ;
        for ( d2Iter = d2.begin( ) ; d2Iter != d2.end( ) ;d2Iter ++ )
            cout << *d2Iter << " ";
        cout << ")." << endl;
        iii++;
    }
}
```

## <a name="sample"></a>örnekli

```cpp
template<class PopulationIterator, class SampleIterator, class Distance, class UniformRandomBitGenerator>
SampleIterator sample(
    PopulationIterator first,
    PopulationIterator last,
    SampleIterator out,
    Distance n,
    UniformRandomBitGenerator&& g);
```

## <a name="search"></a>aramanız

Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 search(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 search(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator1 search(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class BinaryPredicate>
ForwardIterator1 search(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    BinaryPredicate pred);

template <class ForwardIterator, class Searcher>
ForwardIterator search(
    ForwardIterator first,
    ForwardIterator last,
    const Searcher& searcher);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*last1*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*first2*\
Eşleştirilecek aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*last2*\
Bir ileri Yineleyici, eşleştirilecek aralıktaki son öğeden sonraki konumu ele alıyor.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

*Arayıcının*\
Aranacak kalıbı ve kullanılacak arama algoritmasını kapsülleyen Arayıcının.

### <a name="return-value"></a>Dönüş değeri

Bir ileri Yineleyici, belirtilen sırayla eşleşen veya bir ikili koşula göre belirtilen bir Sense ile eşdeğer olan ilk alt dizinin ilk öğesinin konumunu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçiler, her bir sırada bir kez başvurulmalıdır ve en son konum, artırılamadı tarafından ilk kez erişilebilir.

Ortalama karmaşıklık, aranan aralığın boyutuna göre doğrusal ve en kötü durum karmaşıklığının, aranmakta olan sıranın boyutuyla ilgili olarak doğrusal olması gerekir.

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

int main()
{
    using namespace std;
    vector<int> v1, v2;
    list<int> L1;
    vector<int>::iterator Iter1, Iter2;
    list<int>::iterator L1_Iter, L1_inIter;

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
    vector<int>::iterator result1;
    result1 = search (v1.begin( ), v1.end( ), L1.begin( ), L1.end( ) );

    if ( result1 == v1.end( ) )
        cout << "There is no match of L1 in v1."
            << endl;
    else
        cout << "There is at least one match of L1 in v1"
            << "\n and the first one begins at "
            << "position "<< result1 - v1.begin( ) << "." << endl;

    // Searching v1 for a match to L1 under the binary predicate twice
    vector<int>::iterator result2;
    result2 = search (v1.begin( ), v1.end( ), v2.begin( ), v2.end( ), twice );

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

## <a name="search_n"></a>search_n

Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.

```cpp
template<class ForwardIterator1, class Diff2, class Type>
ForwardIterator1 search_n(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    Diff2 count,
    const Type& value);

template<class ForwardIterator1, class Diff2, class Type, class BinaryPredicate>
ForwardIterator1 search_n(
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    Diff2 count,
    const Type& value,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator, class Size, class Type>
ForwardIterator search_n(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Size count,
    const Type& value);

template<class ExecutionPolicy, class ForwardIterator, class Size, class Type, class BinaryPredicate>
ForwardIterator search_n(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    Size count,
    const Type& value,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Aranacak aralıktaki ilk öğenin konumunu adresleyen ileri Yineleyici.

*last1*\
Bir ileriye doğru yineleyici, aranacak aralıktaki son öğeden sonraki konumu ele alıyor.

*biriktirme*\
Aranmakta olan alt dizinin boyutu.

*deeri*\
Aranan dizideki öğelerin değeri.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Bir ileri Yineleyici, belirtilen sırayla eşleşen veya bir ikili koşula göre belirtilen bir Sense ile eşdeğer olan ilk alt dizinin ilk öğesinin konumunu ele alıyor.

### <a name="remarks"></a>Açıklamalar

Bir `operator==` öğe ile belirtilen değer arasındaki eşleşmeyi belirlemede kullanılan, işlenenleri arasında bir denklik ilişkisi getirmelidir.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Karmaşıklık, arandığı boyuta göre doğrusal bir yoldur.

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
    vector<int> v1, v2;
    vector<int>::iterator Iter1;

    int i;
    for ( i = 0 ; i <= 5 ; i++ )
    {
        v1.push_back( 5 * i );
    }

    for ( i = 0 ; i <= 2 ; i++ )
    {
        v1.push_back( 5 );
    }

    for ( i = 0 ; i <= 5 ; i++ )
    {
        v1.push_back( 5 * i );
    }

    for ( i = 0 ; i <= 2 ; i++ )
    {
        v1.push_back( 10 );
    }

    cout << "Vector v1 = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")" << endl;

    // Searching v1 for first match to (5 5 5) under identity
    vector<int>::iterator result1;
    result1 = search_n ( v1.begin( ), v1.end( ), 3, 5 );

    if ( result1 == v1.end( ) )
        cout << "There is no match for a sequence ( 5 5 5 ) in v1."
            << endl;
    else
        cout << "There is at least one match of a sequence ( 5 5 5 )"
            << "\n in v1 and the first one begins at "
            << "position "<< result1 - v1.begin( ) << "." << endl;

    // Searching v1 for first match to (5 5 5) under one_half
    vector<int>::iterator result2;
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

## <a name="set_difference"></a>set_difference

Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class Compare>
OutputIterator set_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator>
ForwardIterator set_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class Compare>
ForwardIterator set_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İki kaynak aralığının farkını temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last1*\
İki kaynak aralığının farkını temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralığının ilk öğesinden bir kez geçen bir giriş Yineleyici.

*first2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında birinci öğenin konumunu ele alarak, iki kaynak aralığının farkını temsil eden tek bir aralığa göre bir giriş Yineleyici.

*last2*\
Art arda iki sıralı kaynak aralığının ikinci ve iki kaynak aralığının farkını temsil eden tek bir aralığa sıralanmış en son öğeden geçen bir giriş Yineleyici.

*kaynaklanan*\
İki kaynak aralığının iki kaynak aralığının farkını temsil eden tek bir sıralanmış aralığa Birleşik olarak bulunacağı, hedef aralıktaki ilk öğenin konumunu ele aldığı çıkış Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişkeni alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

İki kaynak aralığının farkını temsil eden sıralanmış hedef aralıktaki son öğeden sonraki konumu ele alarak bir çıkış yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Hedef Aralık, kaynak aralıklarından biriyle çakışmamalıdır ve ilk kaynak aralığını içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralıklarının her biri, algoritma tarafından Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya uygun `set_difference` olarak, algoritmanın uygulamasına bir ön koşul olarak düzenlenmelidir.

Her aralıktaki öğelerin göreli sırası hedef aralıkta korunduğu için işlem kararlı değildir. Kaynak aralıkları, algoritma birleştirme tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için daha az karşılaştırılabilir olması gerekir. böylece, iki öğe verildiğinde, eşdeğer oldukları (Yani bunlardan daha küçük olmadığı anlamda) veya birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, ilk aralıktaki öğeler, hedef aralıktaki ikinci kaynak aralığından öğeden önce gelmelidir. Kaynak aralıkları, ikinciden daha fazla ilk kaynak aralığında daha fazla olması gibi bir öğenin yinelemelerini içeriyorsa, hedef Aralık ilk kaynak aralıktaki bu öğelerin tekrarlarının oluşum sayısını aşacak şekilde ikinci kaynak aralıktaki öğeler.

Algoritmanın karmaşıklığı, boş olmayan kaynak aralıkları için en çok `2 * ((last1 - first1) - (last2 - first2)) - 1` karşılaştırmalar ile doğrusal bir şekilde yapılır.

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
    vector<int> v1a, v1b, v1 ( 12 );
    vector<int>::iterator Iter1a, Iter1b, Iter1, Result1;

    // Constructing vectors v1a & v1b with default less-than ordering
    int i;
    for ( i = -1 ; i <= 4 ; i++ )
    {
        v1a.push_back( i );
    }

    int ii;
    for ( ii =-3 ; ii <= 0 ; ii++ )
    {
        v1b.push_back( ii );
    }

    cout << "Original vector v1a with range sorted by the\n "
         << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
         << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vectors v2a & v2b with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
    vector<int>::iterator Iter2a, Iter2b, Iter2, Result2;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

    cout << "Original vector v2a with range sorted by the\n "
         << "binary predicate greater is   v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
         << "binary predicate greater is   v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
    vector<int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
    vector<int>::iterator Iter3a, Iter3b, Iter3, Result3;
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
         << "binary predicate mod_lesser is   v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
         << "binary predicate mod_lesser is   v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To combine into a difference in asscending
    // order with the default binary predicate less<int>( )
    Result1 = set_difference ( v1a.begin( ), v1a.end( ),
        v1b.begin( ), v1b.end( ), v1.begin( ) );
    cout << "Set_difference of source ranges with default order,"
         << "\n vector v1mod = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // To combine into a difference in descending
    // order specify binary predicate greater<int>( )
    Result2 = set_difference ( v2a.begin( ), v2a.end( ),
        v2b.begin( ), v2b.end( ),v2.begin( ), greater<int>( ) );
    cout << "Set_difference of source ranges with binary"
         << "predicate greater specified,\n vector v2mod = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // To combine into a difference applying a user
    // defined binary predicate mod_lesser
    Result3 = set_difference ( v3a.begin( ), v3a.end( ),
        v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
    cout << "Set_difference of source ranges with binary "
         << "predicate mod_lesser specified,\n vector v3mod = ( " ; ;
    for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

## <a name="set_intersection"></a>set_intersection

Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result);

template<class InputIterator1, class InputIterator2, class OutputIterator, class Compare>
OutputIterator set_intersection(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    Compare pred);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator>
ForwardIterator set_intersection(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class Compare>
ForwardIterator set_intersection(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İki kaynak aralığının kesişimini temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last1*\
İki kaynak aralığının kesişimini temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralığının ilk öğesinden bir kez geçen bir giriş Yineleyici.

*first2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında birinci öğenin konumunu ele alarak, iki kaynak aralığın kesişimini temsil eden tek bir aralığa göre bir giriş Yineleyici.

*last2*\
Art arda iki sıralı kaynak aralığının ikinci ve iki kaynak aralığının kesişimini temsil eden tek bir aralığa sıralanmış en son öğeden geçen bir giriş Yineleyici.

*kaynaklanan*\
İki kaynak aralığının iki kaynak aralığının kesişimini temsil eden tek bir sıralanmış aralığa Birleşik olarak bulunacağı, hedef aralıktaki ilk öğenin konumunu ele aldığı çıkış Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişkeni alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

İki kaynak aralığının kesişimini temsil eden sıralanmış hedef aralıktaki son öğeden geçen bir çıkış yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Hedef Aralık, kaynak aralıklarından biriyle çakışmamalıdır ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralıklarının her biri, birleştirilmiş aralıkları sıralamak için algoritma tarafından kullanılacak şekilde, birleştirme algoritmasının uygulamanın bir önkoşulu olarak düzenlenmelidir.

Her aralıktaki öğelerin göreli sırası hedef aralıkta korunduğu için işlem kararlı değildir. Kaynak aralıkları algoritma tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için kıyasla daha az olması gerekir, böylece iki öğe söz konusu olduğunda, eşdeğer oldukları (Yani bunlardan daha küçük olmayan) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, ilk aralıktaki öğeler, hedef aralıktaki ikinci kaynak aralığından öğeden önce gelmelidir. Kaynak aralıkları bir öğenin yinelemelerini içeriyorsa, hedef Aralık her iki kaynak aralığında gerçekleşen bu öğelerin en fazla sayısını içerir.

Algoritmanın karmaşıklığı, boş olmayan kaynak aralıkları için en çok `2 * ((last1 - first1) + (last2 - first2)) - 1` karşılaştırmalar ile doğrusal bir şekilde yapılır.

### <a name="example"></a>Örnek

```cpp
// alg_set_intersection.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>   // For greater<int>( )
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
    vector<int> v1a, v1b, v1 ( 12 );
    vector<int>::iterator Iter1a, Iter1b, Iter1, Result1;

    // Constructing vectors v1a & v1b with default less than ordering
    int i;
    for ( i = -1 ; i <= 3 ; i++ )
        v1a.push_back( i );

    int ii;
    for ( ii =-3 ; ii <= 1 ; ii++ )
        v1b.push_back( ii );

    cout << "Original vector v1a with range sorted by the\n "
         << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
         << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vectors v2a & v2b with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
    vector<int>::iterator Iter2a, Iter2b, Iter2, Result2;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

    cout << "Original vector v2a with range sorted by the\n "
         << "binary predicate greater is   v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
         << "binary predicate greater is   v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
    vector<int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
    vector<int>::iterator Iter3a, Iter3b, Iter3, Result3;
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
         << "binary predicate mod_lesser is   v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
         << "binary predicate mod_lesser is   v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To combine into an intersection in asscending order with the
    // default binary predicate less<int>( )
    Result1 = set_intersection ( v1a.begin( ), v1a.end( ),
        v1b.begin( ), v1b.end( ), v1.begin( ) );
    cout << "Intersection of source ranges with default order,"
         << "\n vector v1mod = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; ++Iter1 )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // To combine into an intersection in descending order, specify
    // binary predicate greater<int>( )
    Result2 = set_intersection ( v2a.begin( ), v2a.end( ),
        v2b.begin( ), v2b.end( ),v2.begin( ), greater<int>( ) );
    cout << "Intersection of source ranges with binary predicate"
            << " greater specified,\n vector v2mod = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; ++Iter2 )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // To combine into an intersection applying a user-defined
    // binary predicate mod_lesser
    Result3 = set_intersection ( v3a.begin( ), v3a.end( ),
        v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
    cout << "Intersection of source ranges with binary predicate "
            << "mod_lesser specified,\n vector v3mod = ( " ; ;
    for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; ++Iter3 )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

## <a name="set_symmetric_difference"></a>set_symmetric_difference

İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class Compare>
OutputIterator set_symmetric_difference(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator>
ForwardIterator set_symmetric_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class Compare>
ForwardIterator set_symmetric_difference(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İki kaynak aralığının simetrik farkını temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last1*\
İki kaynak aralığının simetrik farkını temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralığının ilk öğesinden bir kez geçen bir girdi yineleyicisi.

*first2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında birinci öğenin konumunu ele alarak, iki kaynak aralığının simetrik farkını temsil eden tek bir aralığa göre bir giriş Yineleyici.

*last2*\
Art arda iki sıralı kaynak aralığının ikinci ve iki kaynak aralığının simetrik farkını temsil eden tek bir aralığa sıralanmış en son öğeden geçen bir giriş Yineleyici.

*kaynaklanan*\
İki kaynak aralığının iki kaynak aralığının simetrik farkını temsil eden tek bir sıralanmış aralığa Birleşik olarak bulunacağı, hedef aralıktaki ilk öğenin konumunu ele aldığı çıkış yineleyicisi.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişkeni alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

İki kaynak aralığının simetrik farkını temsil eden sıralanmış hedef aralıktaki son öğeden geçen bir çıkış yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Hedef Aralık, kaynak aralıklarından biriyle çakışmamalıdır ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralıklarının her biri, algoritma tarafından Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya uygun `merge*` olarak, algoritmanın uygulamasına bir ön koşul olarak düzenlenmelidir.

Her aralıktaki öğelerin göreli sırası hedef aralıkta korunduğu için işlem kararlı değildir. Kaynak aralıkları, algoritma birleştirme tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için kıyasla daha az olması gerekir, böylece iki öğe söz konusu olduğunda, eşdeğer oldukları (Yani bunlardan daha küçük olmayan) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, ilk aralıktaki öğeler, hedef aralıktaki ikinci kaynak aralığından öğeden önce gelmelidir. Kaynak aralıkları bir öğenin yinelemelerini içeriyorsa, hedef Aralık, kaynak aralıklarından birindeki bu öğelerin oluşumlarının ikinci kaynaktaki bu öğelerin oluşumlarını aştığında sayının mutlak değerini içerir aralığı.

Algoritmanın karmaşıklığı, boş olmayan kaynak aralıkları için en çok `2 * ((last1 - first1) - (last2 - first2)) - 1` karşılaştırmalar ile doğrusal bir şekilde yapılır.

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
    vector<int> v1a, v1b, v1 ( 12 );
    vector<int>::iterator Iter1a, Iter1b, Iter1, Result1;

    // Constructing vectors v1a & v1b with default less-than ordering
    int i;
    for ( i = -1 ; i <= 4 ; i++ )
    {
        v1a.push_back( i );
    }

    int ii;
    for ( ii =-3 ; ii <= 0 ; ii++ )
    {
        v1b.push_back( ii );
    }

    cout << "Original vector v1a with range sorted by the\n "
         << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
         << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vectors v2a & v2b with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
    vector<int>::iterator Iter2a, Iter2b, Iter2, Result2;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

    cout << "Original vector v2a with range sorted by the\n "
         << "binary predicate greater is   v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
         << "binary predicate greater is   v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
    vector<int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
    vector<int>::iterator Iter3a, Iter3b, Iter3, Result3;
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
         << "binary predicate mod_lesser is   v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
         << "binary predicate mod_lesser is   v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To combine into a symmetric difference in ascending
    // order with the default binary predicate less<int>( )
    Result1 = set_symmetric_difference ( v1a.begin( ), v1a.end( ),
        v1b.begin( ), v1b.end( ), v1.begin( ) );
    cout << "Set_symmetric_difference of source ranges with default order,"
         << "\n vector v1mod = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // To combine into a symmetric difference in descending
    // order, specify binary predicate greater<int>( )
    Result2 = set_symmetric_difference ( v2a.begin( ), v2a.end( ),
        v2b.begin( ), v2b.end( ),v2.begin( ), greater<int>( ) );
    cout << "Set_symmetric_difference of source ranges with binary"
         << "predicate greater specified,\n vector v2mod = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // To combine into a symmetric difference applying a user
    // defined binary predicate mod_lesser
    Result3 = set_symmetric_difference ( v3a.begin( ), v3a.end( ),
        v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
    cout << "Set_symmetric_difference of source ranges with binary "
         << "predicate mod_lesser specified,\n vector v3mod = ( " ; ;
    for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

## <a name="set_union"></a>set_union

İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class InputIterator1, class InputIterator2, class OutputIterator>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result );

template<class InputIterator1, class InputIterator2, class OutputIterator, class Compare>
OutputIterator set_union(
    InputIterator1 first1,
    InputIterator1 last1,
    InputIterator2 first2,
    InputIterator2 last2,
    OutputIterator result,
    Compare pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator>
ForwardIterator set_union(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class Compare>
ForwardIterator set_union(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator2 last2,
    ForwardIterator result,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İki kaynak aralığın birleşimini temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralıktaki ilk öğenin konumunu ele almak için bir giriş Yineleyici.

*last1*\
İki kaynak aralığın birleşimini temsil eden tek bir aralığa Birleşik ve sıralanan iki sıralı kaynak aralığının ilk öğesinden bir kez geçen bir giriş Yineleyici.

*first2*\
Art arda iki sıralı kaynak aralığının ikinci kısmında birinci öğenin konumunu ele alarak, iki kaynak aralığın birleşimini temsil eden tek bir aralığa göre bir giriş Yineleyici.

*last2*\
Art arda iki sıralı kaynak aralığının ikincisine göre son öğeden geçen ve iki kaynak aralığının birleşimini temsil eden tek bir aralığa sıralanan bir giriş Yineleyici.

*kaynaklanan*\
İki kaynak aralığının iki kaynak aralığın birleşimini temsil eden tek bir sıralanmış aralığa Birleşik olarak bulunacağı, hedef aralıktaki ilk öğenin konumunu ele aldığı çıkış Yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişkeni alır ve ilk öğe ikinci öğeden küçük olduğunda **true** , aksi durumda **false** döndürmelidir.

### <a name="return-value"></a>Dönüş değeri

İki kaynak aralığının birleşimini temsil eden sıralanmış hedef aralıktaki son öğeden sonraki konumu ele alarak bir çıkış yineleyicisi.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralıkları geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır.

Hedef Aralık, kaynak aralıklarından biriyle çakışmamalıdır ve hedef aralığı içerecek kadar büyük olmalıdır.

Sıralanmış kaynak aralıklarının her biri, algoritma tarafından Birleşik aralıkları sıralamak için kullanılan aynı sıralamaya uygun `merge` olarak, algoritmanın uygulamasına bir ön koşul olarak düzenlenmelidir.

Her aralıktaki öğelerin göreli sırası hedef aralıkta korunduğu için işlem kararlı değildir. Kaynak aralıkları algoritma `merge`tarafından değiştirilmez.

Giriş yineleyicilerinin değer türlerinin sıralanabilmesi için kıyasla daha az olması gerekir, böylece iki öğe söz konusu olduğunda, eşdeğer oldukları (Yani bunlardan daha küçük olmayan) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Her iki kaynak aralığında da eşdeğer öğeler olduğunda, ilk aralıktaki öğeler, hedef aralıktaki ikinci kaynak aralığından öğeden önce gelmelidir. Kaynak aralıkları bir öğenin yinelemelerini içeriyorsa, hedef Aralık her iki kaynak aralığında gerçekleşen bu öğelerin en fazla sayısını içerir.

Algoritmanın karmaşıklığı, en çok `2 * ((last1 - first1) - (last2 - first2)) - 1` karşılaştırmalar ile doğrusal olarak belirlenir.

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
    vector<int> v1a, v1b, v1 ( 12 );
    vector<int>::iterator Iter1a, Iter1b, Iter1, Result1;

    // Constructing vectors v1a & v1b with default less than ordering
    int i;
    for ( i = -1 ; i <= 3 ; i++ )
    {
        v1a.push_back( i );
    }

    int ii;
    for ( ii =-3 ; ii <= 1 ; ii++ )
    {
        v1b.push_back( ii );
    }

    cout << "Original vector v1a with range sorted by the\n "
         << "binary predicate less than is v1a = ( " ;
    for ( Iter1a = v1a.begin( ) ; Iter1a != v1a.end( ) ; Iter1a++ )
        cout << *Iter1a << " ";
    cout << ")." << endl;

    cout << "Original vector v1b with range sorted by the\n "
         << "binary predicate less than is v1b = ( " ;
    for ( Iter1b = v1b.begin( ) ; Iter1b != v1b.end( ) ; Iter1b++ )
        cout << *Iter1b << " ";
    cout << ")." << endl;

    // Constructing vectors v2a & v2b with ranges sorted by greater
    vector<int> v2a ( v1a ) , v2b ( v1b ) , v2 ( v1 );
    vector<int>::iterator Iter2a, Iter2b, Iter2, Result2;
    sort ( v2a.begin( ), v2a.end( ), greater<int>( ) );
    sort ( v2b.begin( ), v2b.end( ), greater<int>( ) );

    cout << "Original vector v2a with range sorted by the\n "
         << "binary predicate greater is   v2a = ( " ;
    for ( Iter2a = v2a.begin( ) ; Iter2a != v2a.end( ) ; Iter2a++ )
        cout << *Iter2a << " ";
    cout << ")." << endl;

    cout << "Original vector v2b with range sorted by the\n "
         << "binary predicate greater is   v2b = ( " ;
    for ( Iter2b = v2b.begin( ) ; Iter2b != v2b.end( ) ; Iter2b++ )
        cout << *Iter2b << " ";
    cout << ")." << endl;

    // Constructing vectors v3a & v3b with ranges sorted by mod_lesser
    vector<int> v3a ( v1a ), v3b ( v1b ) , v3 ( v1 );
    vector<int>::iterator Iter3a, Iter3b, Iter3, Result3;
    sort ( v3a.begin( ), v3a.end( ), mod_lesser );
    sort ( v3b.begin( ), v3b.end( ), mod_lesser );

    cout << "Original vector v3a with range sorted by the\n "
         << "binary predicate mod_lesser is   v3a = ( " ;
    for ( Iter3a = v3a.begin( ) ; Iter3a != v3a.end( ) ; Iter3a++ )
        cout << *Iter3a << " ";
    cout << ")." << endl;

    cout << "Original vector v3b with range sorted by the\n "
         << "binary predicate mod_lesser is   v3b = ( " ;
    for ( Iter3b = v3b.begin( ) ; Iter3b != v3b.end( ) ; Iter3b++ )
        cout << *Iter3b << " ";
    cout << ")." << endl;

    // To combine into a union in ascending order with the default
        // binary predicate less<int>( )
    Result1 = set_union ( v1a.begin( ), v1a.end( ),
        v1b.begin( ), v1b.end( ), v1.begin( ) );
    cout << "Union of source ranges with default order,"
         << "\n vector v1mod = ( " ;
    for ( Iter1 = v1.begin( ) ; Iter1 != Result1 ; Iter1++ )
        cout << *Iter1 << " ";
    cout << ")." << endl;

    // To combine into a union in descending order, specify binary
    // predicate greater<int>( )
    Result2 = set_union ( v2a.begin( ), v2a.end( ),
        v2b.begin( ), v2b.end( ),v2.begin( ), greater<int>( ) );
    cout << "Union of source ranges with binary predicate greater "
         << "specified,\n vector v2mod = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != Result2 ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // To combine into a union applying a user-defined
    // binary predicate mod_lesser
    Result3 = set_union ( v3a.begin( ), v3a.end( ),
        v3b.begin( ), v3b.end( ), v3.begin( ), mod_lesser );
    cout << "Union of source ranges with binary predicate "
         << "mod_lesser specified,\n vector v3mod = ( " ; ;
    for ( Iter3 = v3.begin( ) ; Iter3 != Result3 ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

## <a name="shuffle"></a>çalmayı

Rastgele bir sayı Oluşturucu kullanarak belirli bir Aralık için öğeleri karışık (yeniden düzenler).

```cpp
template<class RandomAccessIterator, class UniformRandomNumberGenerator>
void shuffle(
    RandomAccessIterator first,
    RandomAccessIterator last,
    UniformRandomNumberGenerator&& gen);
```

### <a name="parameters"></a>Parametreler

*adı*\
Bir yineleyici, dahil olmak üzere, karıştırılan aralıktaki ilk öğe. , `RandomAccessIterator` Ve`ValueSwappable`gereksinimlerinin karşılanması gerekir.

*soyadına*\
Bir yineleyiciden, tek başına karıştırılmış ve dışlamalı son öğe. , `RandomAccessIterator` Ve`ValueSwappable`gereksinimlerinin karşılanması gerekir.

*alanına*\
`shuffle()` İşlevin işlem için kullanacağı rastgele sayı Oluşturucu. , Öğesinin `UniformRandomNumberGenerator`gereksinimleriyle Buluşmalıdır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve tarafından kullanılan `shuffle()`bir kod örneği için bkz [ \<. Random >](../standard-library/random.md).

## <a name="sort"></a>düzenine

Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class RandomAccessIterator>
void sort(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
void sort(
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);

template<class ExecutionPolicy, class RandomAccessIterator>
void sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
void sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Sıralanacak aralıktaki son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Bu ikili koşul iki bağımsız değişken alır ve iki bağımsız değişken sıradaysa **true** , aksi takdirde **false** döndürür. Bu karşılaştırıcı işlevi, dizideki öğe çiftlerine katı bir zayıf sıralama getirmelidir. Daha fazla bilgi için bkz. [algoritmalar](../standard-library/algorithms.md).

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Öğeler eşdeğer, ancak eşit değildir, ancak ikisi de küçüktür. `sort` Algoritma kararlı değildir ve bu nedenle denk öğelerin göreli sıralamasına karşı korunmayacağını garanti etmez. Algoritma `stable_sort` bu orijinal sıralamayı korur.

Sıralama karmaşıklığına `O( N log N )`ilişkin ortalama,*en son* -  *N* = *birinciden*oluşur.

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
    vector<int> v1;
    vector<int>::iterator Iter1;

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

## <a name="sort_heap"></a>sort_heap

Bir yığını sıralanmış bir aralığa dönüştürür.

```cpp
template<class RandomAccessIterator>
void sort_heap(
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class RandomAccessIterator, class Compare>
void sort_heap(
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Hedef yığında ilk öğenin konumunu ele alarak rastgele erişimli bir yineleyici.

*soyadına*\
Hedef yığında son öğeden sonraki konumu ele alarak rastgele erişimli bir yineleyici.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Heap 'ler iki özelliğe sahiptir:

- İlk öğe her zaman en büyüktür.

- Öğeler, logaritmik bir zamanda eklenebilir veya kaldırılabilir.

Uygulama bu algoritmadan sonra, uygulandığı Aralık artık bir yığın değildir.

Denk öğelerin göreli sırası korunmadığı için bu kararlı bir sıralama değildir.

Heap 'ler, öncelik kuyruklarını uygulamanın ideal bir yoludur ve C++ standart kitaplık kapsayıcı bağdaştırıcısı [priority_queue sınıfının](../standard-library/priority-queue-class.md)uygulamasında kullanılır.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Karmaşıklık en çok `N log N`, burada *N* = *son* - *ilk*.

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

void print(const string& s, const vector<int>& v)
{
    cout << s << ": ( ";

    for (auto i = v.begin(); i != v.end(); ++i)
    {
        cout << *i << " ";
    }

    cout << ")" << endl;
}

int main()
{
    vector<int> v;
    for (int i = 1; i <= 9; ++i)
    {
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

## <a name="stable_partition"></a>stable_partition

Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.

```cpp
template<class BidirectionalIterator, class UnaryPredicate>
BidirectionalIterator stable_partition(
    BidirectionalIterator first,
    BidirectionalIterator last,
    UnaryPredicate pred );

template<class ExecutionPolicy, class BidirectionalIterator, class UnaryPredicate>
BidirectionalIterator stable_partition(
    ExecutionPolicy&& exec,
    BidirectionalIterator first,
    BidirectionalIterator last,
    UnaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Bölümlendirilmek üzere aralıktaki ilk öğenin konumunu ele alarak çift yönlü bir yineleyici.

*soyadına*\
Bölümlendirilmek üzere aralıktaki son öğeden geçmiş bir konumu ele alarak çift yönlü bir yineleyici.

*pred*\
Bir öğe sınıflandırılabildiğinde karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. Birli koşul tek bir bağımsız değişken alır ve memnun olursa **true** , aksi takdirde **false** döndürür.

### <a name="return-value"></a>Dönüş değeri

Koşul koşulunu yerine getirmek için aralıktaki ilk öğenin konumunu ele alarak çift yönlü bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

*A* ve *b* öğeleri eşdeğerdir, ancak her ikisi de false ise eşit değildir `pred( a, b )` ve `pred( b, a )` false ise, her ikisi de parametre belirtilen *koşul olur.* `stable_partition` Algoritma kararlı olur ve denk öğelerin göreli sıralamasını korunacaktır. Algoritma `partition` bu orijinal sıralamayı korumayabilir.

### <a name="example"></a>Örnek

```cpp
// alg_stable_partition.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

bool greater5 ( int value )
{
    return value > 5;
}

int main()
{
    using namespace std;
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2, result;

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

## <a name="stable_sort"></a>stable_sort

Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.

```cpp
template<class BidirectionalIterator>
void stable_sort(
    BidirectionalIterator first,
    BidirectionalIterator last );

template<class BidirectionalIterator, class Compare>
void stable_sort(
    BidirectionalIterator first,
    BidirectionalIterator last,
    Compare pred );

template<class ExecutionPolicy, class RandomAccessIterator>
void stable_sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last);

template<class ExecutionPolicy, class RandomAccessIterator, class Compare>
void stable_sort(
    ExecutionPolicy&& exec,
    RandomAccessIterator first,
    RandomAccessIterator last,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Sıralanacak aralıktaki ilk öğenin konumunu ele alarak çift yönlü bir yineleyici.

*soyadına*\
Sıralanacak aralıktaki son öğeden bir tane olan konumu ele alarak çift yönlü bir yineleyici.

*pred*\
Sıralamada birbirini izleyen öğeler tarafından karşılanması gereken karşılaştırma ölçütünü tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir.

Öğeler eşdeğer, ancak eşit değildir, ancak ikisi de küçüktür. `sort` Algoritma kararlı olur ve denk öğelerin göreli sıralamasını korunacaktır.

Çalışma `stable_sort` zamanı karmaşıklığı kullanılabilir bellek miktarına bağlıdır, ancak en iyi durum (yeterli bellek verilir `O(N log N)` ) `O(N (log N)^2)`ve en kötü durum, burada *N* = *son*  -   *ilk*olarak. Genellikle, `sort` algoritma şundan `stable_sort`önemli ölçüde daha hızlıdır.

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
    vector<int> v1;
    vector<int>::iterator Iter1;

    int i;
    for ( i = 0 ; i <= 5 ; i++ )
    {
        v1.push_back( 2 * i );
    }

    for ( i = 0 ; i <= 5 ; i++ )
    {
        v1.push_back( 2 * i );
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

## <a name="swap"></a>Kur

İlk geçersiz kılma iki nesnenin değerlerini değiş tokuş eder. İkinci geçersiz kılma, iki nesne dizisi arasındaki değerleri değiş tokuş eder.

```cpp
template<class Type>
void swap(
    Type& left,
    Type& right);
template<class Type, size_t N>
void swap(
    Type (& left)[N],
    Type (& right)[N]);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlk geçersiz kılma için, içeriğini değiş tokuş eden ilk nesne. İkinci geçersiz kılma için, içeriklerinin değiş tokuş edilecek ilk nesne dizisi.

*Right*\
İlk geçersiz kılma için, içeriğini değiş tokuş eden ikinci nesne. İkinci geçersiz kılma için, içeriğini değiş tokuş edilecek ikinci nesne dizisi.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme ayrı nesneler üzerinde çalışacak şekilde tasarlanmıştır. İkinci aşırı yükleme, nesnelerin içeriğini iki dizi arasında değiştirir.

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
    vector<int> v1, v2;
    vector<int>::iterator Iter1, Iter2, result;

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

## <a name="swap_ranges"></a>swap_ranges

Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.

```cpp
template<class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 swap_ranges(
   ForwardIterator1 first1,
   ForwardIterator1 last1,
   ForwardIterator2 first2 );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 swap_ranges(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
İleri Yineleyici, öğeleri değiş tokuş edilecek ilk aralığın ilk konumunu işaret eder.

*last1*\
Öğeleri değiş tokuş edilecek ilk aralığın son konumunu işaret eden bir ileri Yineleyici.

*first2*\
İleri Yineleyici, öğeleri değiş tokuş edilecek ikinci aralığın ilk konumunu işaret eder.

### <a name="return-value"></a>Dönüş değeri

Bir ileri Yineleyici, öğeleri değiş tokuş edilecek ikinci aralığın son konumunu işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçiler, her bir sırada bir kez başvurulmalıdır ve en son konum, artırılamadı tarafından ilk kez erişilebilir. İkinci Aralık ilk Aralık kadar büyük olmalıdır.

Karmaşıklık, *last1* - *first1* takas gerçekleştirilen doğrusal bir şekilde karmaşıktır. Aynı türdeki kapsayıcılardan öğeler takas edilmekte ise, `swap` üye işlevi genellikle sabit karmaşıklığa sahip olduğundan, bu kapsayıcıdan üye işlevi kullanılmalıdır.

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
    vector<int> v1;
    deque<int> d1;
    vector<int>::iterator v1Iter1;
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
        cout << *v1Iter1 << " ";
    cout << ")." << endl;

    cout << "Deque d1 is  ( " ;
    for ( d1Iter1 = d1.begin( ) ; d1Iter1 != d1.end( ) ;d1Iter1 ++ )
        cout << *d1Iter1 << " ";
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

## <a name="transform"></a>Dönüşümler

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

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class UnaryOperation>
ForwardIterator2 transform(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    UnaryOperation op);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2, class ForwardIterator, class BinaryOperation>
ForwardIterator transform(
    ExecutionPolicy&& exec,
    ForwardIterator1 first1,
    ForwardIterator1 last1,
    ForwardIterator2 first2,
    ForwardIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*first1*\
Üzerinde çalıştırılacak ilk kaynak aralıktaki ilk öğenin konumunu ele alan bir giriş Yineleyici.

*last1*\
Üzerinde çalıştırılan ilk kaynak aralıktaki son öğeden önceki konumu ele alan bir giriş Yineleyici.

*first2*\
Üzerinde çalıştırılacak ikinci kaynak aralıktaki ilk öğenin konumunu ele alan bir giriş Yineleyici.

*kaynaklanan*\
Hedef aralıktaki ilk öğenin konumunu ele alarak çıkış Yineleyici.

*melerinin*\
İlk kaynak aralıktaki her bir öğeye veya bir Kullanıcı tanımlı (UD) ikili işlev nesnesine, bir ileriye doğru şekilde uygulanmış olan algoritmanın ikinci sürümünde kullanılan, algoritmanın ilk sürümünde kullanılan Kullanıcı tanımlı birli işlev nesnesi , iki kaynak aralığına.

### <a name="return-value"></a>Dönüş değeri

İşlev nesnesi tarafından dönüştürülen çıkış öğelerini alan hedef aralıktaki son öğeden önceki konumu ele alan bir çıkış Yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçilerin erişilebilir olması gerekir ve her bir dizide en son konum artırılamadı tarafından ilk kez ulaşılabilir olmalıdır. Hedef Aralık, dönüştürülmüş kaynak aralığını içerecek kadar büyük olmalıdır.

*Sonuç* , algoritmanın ilk sürümünde *first1* değerine eşitse, kaynak ve hedef aralıklar aynı olur ve sıra yerinde değiştirilir. Ancak *sonuç* [`first1` + 1, `last1`) aralığı içinde bir konumu ele vermeyebilir.

Karmaşıklık, en çok (`last1` - `first1`) karşılaştırmalarda doğrusal olarak belirlenir.

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
    MultValue ( const Type& value ) : Factor ( value ) { }

    // The function call for the element to be multiplied
    Type operator( ) ( Type& elem ) const
    {
        return elem * Factor;
    }
};

int main()
{
    using namespace std;
    vector<int> v1, v2 ( 7 ), v3 ( 7 );
    vector<int>::iterator Iter1, Iter2 , Iter3;

    // Constructing vector v1
    int i;
    for ( i = -4 ; i <= 2 ; i++ )
    {
        v1.push_back( i );
    }

    cout << "Original vector v1 = ( " ;
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
            << "by the factor 5 & copying to v2 gives:\n v2 = ( " ;
    for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
        cout << *Iter2 << " ";
    cout << ")." << endl;

    // The second version of transform used to multiply the
    // elements of the vectors v1mod & v2 pairwise
    transform ( v1.begin( ), v1.end( ), v2.begin( ), v3.begin( ),
        multiplies<int>( ) );

    cout << "Multiplying elements of the vectors v1mod and v2 pairwise "
            << "gives:\n v3 = ( " ;
    for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
        cout << *Iter3 << " ";
    cout << ")." << endl;
}
```

```Output
Original vector v1 = ( -4 -3 -2 -1 0 1 2 ).
The elements of the vector v1 multiplied by 2 in place gives:
v1mod = ( -8 -6 -4 -2 0 2 4 ).
Multiplying the elements of the vector v1mod
by the factor 5 & copying to v2 gives:
v2 = ( -40 -30 -20 -10 0 10 20 ).
Multiplying elements of the vectors v1mod and v2 pairwise gives:
v3 = ( 320 180 80 20 0 20 80 ).
```

## <a name="unique"></a>eşi

Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.

```cpp
template<class ForwardIterator>
ForwardIterator unique(
    ForwardIterator first,
    ForwardIterator last);

template<class ForwardIterator, class BinaryPredicate>
ForwardIterator unique(
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate pred);

template<class ExecutionPolicy, class ForwardIterator>
ForwardIterator unique(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last);

template<class ExecutionPolicy, class ForwardIterator, class BinaryPredicate>
ForwardIterator unique(
    ExecutionPolicy&& exec,
    ForwardIterator first,
    ForwardIterator last,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Yinelenen kaldırma için Taranacak aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*soyadına*\
Yinelenen kaldırma için taranacak olan aralıktaki son öğeden bir önceki konumu ele alarak ileriye doğru bir yineleyici.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Art arda yinelenen olmayan yineleme içermeyen değiştirilmiş sıranın yeni sonuna bir iletme yineleyicisi, son öğeden çıkarılan konumu ele alır.

### <a name="remarks"></a>Açıklamalar

Her iki algoritma formu, birbirini izleyen eşit öğelerin çiftinin ikinci yinelemesini kaldırır.

Algoritma işlemi, silinmeyen öğelerin göreli sırası değiştirilmemesi için kararlı bir işlemdir.

Başvurulan Aralık geçerli olmalıdır; Tüm işaretçiler, en son artırılamadı tarafından ilk konumdan erişilebilir olması gerekir. dizideki öğe sayısı, algoritma `unique` tarafından değiştirilmez ve değiştirilen sıranın sonundaki öğeler geçersiz olur ancak belirtilmez.

Karmaşıklık, karşılaştırmalar gerektiren `(last - first) - 1` doğrusal bir değer.

Liste, daha iyi gerçekleştirebilen daha verimli bir "Unique" üye işlevi sağlar.

Bu algoritmalar ilişkilendirilebilir bir kapsayıcıda kullanılamaz.

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
    vector<int> v1;
    vector<int>::iterator v1_Iter1, v1_Iter2, v1_Iter3,
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

## <a name="unique_copy"></a>unique_copy

Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.

```cpp
template<class InputIterator, class OutputIterator>
OutputIterator unique_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result );

template<class InputIterator, class OutputIterator, class BinaryPredicate>
OutputIterator unique_copy(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryPredicate pred );

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2>
ForwardIterator2 unique_copy(
    ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result);

template<class ExecutionPolicy, class ForwardIterator1, class ForwardIterator2,
class BinaryPredicate>
ForwardIterator2 unique_copy(ExecutionPolicy&& exec,
    ForwardIterator1 first,
    ForwardIterator1 last,
    ForwardIterator2 result,
    BinaryPredicate pred);
```

### <a name="parameters"></a>Parametreler

*Exec*\
Kullanılacak yürütme ilkesi.

*adı*\
Kopyalanacak kaynak aralıktaki ilk öğenin konumunu ele alarak ileriye doğru bir yineleyici.

*soyadına*\
Kaynak aralıktaki kopyalanacak son öğeden bir önceki konumu ele alarak ileriye doğru bir yineleyici.

*kaynaklanan*\
Bir çıkış yineleyicisi, bir kopyayı ardışık yinelemeler kaldırılmış şekilde alan hedef aralıktaki ilk öğenin konumunu ele alıyor.

*pred*\
İki öğenin eşdeğer olarak alınması durumunda karşılanması gereken koşulu tanımlayan Kullanıcı tanımlı koşul işlevi nesnesi. İkili koşul iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Arka arkaya yinelenen kopyaları kaldırılmış şekilde kopyayı alan hedef aralıktaki son öğeden bir önceki konumu ele alan çıkış Yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki algoritma formu, birbirini izleyen eşit öğelerin çiftinin ikinci yinelemesini kaldırır.

Algoritma işlemi, silinmeyen öğelerin göreli sırası değiştirilmemesi için kararlı bir işlemdir.

Başvurulan aralıklar geçerli olmalıdır; Tüm işaretçiler, bir dizi içinde ve en son konum ilk artırılamadı tarafından erişilebilir olmalıdır.

Karmaşıklık, doğrusal, (`last` - `first`) karşılaştırmaları gerektirir.

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
    vector<int> v1;
    vector<int>::iterator v1_Iter1, v1_Iter2,
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

## <a name="upper_bound"></a>upper_bound

Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.

```cpp
template<class ForwardIterator, class Type>
ForwardIterator upper_bound(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value);

template<class ForwardIterator, class Type, class Compare>
ForwardIterator upper_bound(
    ForwardIterator first,
    ForwardIterator last,
    const Type& value,
    Compare pred);
```

### <a name="parameters"></a>Parametreler

*adı*\
Aranacak aralıktaki ilk öğenin konumu.

*soyadına*\
Aranacak aralıktaki son öğeden geçen bir konum.

*deeri*\
Sıralanmış aralıktaki, döndürülen Yineleyici tarafından belirtilen öğenin değeri ile aşılması gereken değer.

*pred*\
Bir öğenin diğerinden küçük olduğu anlamlı olduğunu tanımlayan Kullanıcı tanımlı karşılaştırma koşulu işlev nesnesi. Karşılaştırma koşulu iki bağımsız değişken alır ve memnun olmadığında **true** ve **false** değeri döndürür.

### <a name="return-value"></a>Dönüş değeri

Belirtilen değerden daha büyük bir değere sahip ilk öğenin konumuna ileriye doğru bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Başvurulan sıralanmış kaynak aralığı geçerli olmalıdır; tüm yineleyiciler, en başta artırılamadı 'e başvurulamamalıdır.

Sıralanmış bir Aralık, kullanımı `upper_bound` ve sıralama ölçütünün karşılaştırma koşulu tarafından belirtilen şekilde aynı olduğu bir önkoşuludur.

Aralık tarafından `upper_bound`değiştirilmez.

İleriye doğru yineleyicilerin değer türlerinin sıralanabilmesi için kıyasla daha az karşılaştırılabilir olması gerekir. bu sayede, iki öğe verildiğinde, eşdeğer oldukları (Yani bunlardan daha küçük olmadığı anlamda) ya da birinin diğerinin daha küçük olduğu belirlenebilir. Bu, eşdeğer olmayan öğeler arasında bir sıralamaya neden olur

Algoritmanın karmaşıklığı Rastgele erişimli yineleyiciler ve doğrusal olarak, diğer bir deyişle, diğer bir deyişle, diğer bir deyişle, (`last - first`) ile orantılıdır.

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
        v1.push_back( i );
    }

    for ( auto ii =-3 ; ii <= 0 ; ++ii )
    {
        v1.push_back( ii );
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
        << "binary predicate mod_lesser is v3 = ( " ;
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

    // upper_bound of 3 in v3 with the binary predicate mod_lesser
    Result = upper_bound(v3.begin(), v3.end(), 3, mod_lesser);
    cout << "The upper_bound in v3 for the element with a value of 3 is: "
        << *Result << "." << endl;
}
```
