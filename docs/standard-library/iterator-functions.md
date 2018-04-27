---
title: '&lt;Yineleyici&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::advance
- xutility/std::back_inserter
- xutility/std::begin
- xutility/std::cbegin
- xutility/std::cend
- xutility/std::distance
- xutility/std::end
- xutility/std::front_inserter
- xutility/std::inserter
- xutility/std::make_checked_array_iterator
- xutility/std::make_move_iterator
- xutility/std::make_unchecked_array_iterator
- xutility/std::next
- xutility/std::prev
ms.assetid: 4a57c9a3-7e36-411f-8655-e0be2eec88e7
caps.latest.revision: 16
manager: ghogen
helpviewer_keywords:
- std::advance [C++]
- std::back_inserter [C++]
- std::begin [C++]
- std::cbegin [C++]
- std::cend [C++]
- std::distance [C++]
- std::end [C++]
- std::front_inserter [C++]
- std::inserter [C++]
- std::make_checked_array_iterator [C++]
- std::make_move_iterator [C++]
- std::make_unchecked_array_iterator [C++]
- std::next [C++]
- std::prev [C++]
ms.openlocfilehash: a57f1c03bc03c72238306e43056240e6d8571a73
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltiteratorgt-functions"></a>&lt;Yineleyici&gt; işlevleri

||||
|-|-|-|
|[Gelişmiş](#advance)|[back_inserter](#back_inserter)|[Başlangıç](#begin)|
|[cbegin](#cbegin)|[cend](#cend)|[uzaklık](#distance)|
|[Bitiş](#end)|[front_inserter](#front_inserter)|[inserter](#inserter)|
|[make_checked_array_iterator](#make_checked_array_iterator)|[make_move_iterator](#make_move_iterator)|[make_unchecked_array_iterator](#make_unchecked_array_iterator)|
|[Sonraki](#next)|[Önceki](#prev)|

## <a name="advance"></a>  Gelişmiş

Belirtilen bir konum sayısıyla yineleyiciyi artırır.

```cpp
template <class InputIterator, class Distance>
void advance(
    InputIterator& InIt,
    Distance Off);
```

### <a name="parameters"></a>Parametreler

`InIt` Yineleyici artırılması olan ve giriş yineleyici gereksinimlerini karşılaması gerekir.

`Off` Yineleyici'nın fark türüne dönüştürülebilir ve artışlarla sayısını belirleyen bir tam sayı yineleyici konumunu Gelişmiş türüdür.

### <a name="remarks"></a>Açıklamalar

Aralık gelişimi tekil olmamalıdır, burada yineleyicilerin başvurusu kaldırılmalı veya sonu aşmalıdır.

Varsa **InputIterator** sonra bir çift yönlü yineleyici türü için gereksinimleri karşılayan `Off` negatif olabilir. Varsa **InputIterator** bir giriş veya İleri yineleyici türü `Off` negatif olmayan olması gerekir.

Sabit karmaşıklık advance işlevi sahip olduğunda **InputIterator** rasgele erişim yineleyici; gereksinimlerini karşılayan Aksi halde, doğrusal karmaşıklık varsa ve bu nedenle olası pahalıdır.

### <a name="example"></a>Örnek

```cpp
// iterator_advance.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   list<int> L;
   for ( i = 1 ; i < 9 ; ++i )
   {
      L.push_back ( i );
   }
   list <int>::iterator L_Iter, LPOS = L.begin ( );

   cout << "The list L is: ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   cout << "The iterator LPOS initially points to the first element: "
        << *LPOS << "." << endl;

   advance ( LPOS , 4 );
   cout << "LPOS is advanced 4 steps forward to point"
        << " to the fifth element: "
        << *LPOS << "." << endl;

   advance ( LPOS , -3 );
   cout << "LPOS is moved 3 steps back to point to the "
        << "2nd element: " << *LPOS << "." << endl;
}
```

```Output
The list L is: ( 1 2 3 4 5 6 7 8 ).
The iterator LPOS initially points to the first element: 1.
LPOS is advanced 4 steps forward to point to the fifth element: 5.
LPOS is moved 3 steps back to point to the 2nd element: 2.
```

## <a name="back_inserter"></a>  back_inserter

Belirtilen kapsayıcının arkasında öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
template <class Container>
back_insert_iterator<Container> back_inserter(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

`_Cont` İçine geri ekleme yürütülecek kapsayıcısı.

### <a name="return-value"></a>Dönüş Değeri

A `back_insert_iterator` kapsayıcı nesneyle ilişkili `_Cont`.

### <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı içinde bağımsız değişkeni bir üye fonksiyonu sahip üç dizisi kapsayıcıları başvurmalıdır `push_back`: [deque sınıfı](../standard-library/deque-class.md), [sınıf listesi](../standard-library/list-class.md), veya [vektör Sınıf](../standard-library/vector-class.md).

### <a name="example"></a>Örnek

```cpp
// iterator_back_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 3 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Insertions can be done with template function
   back_insert_iterator<vector<int> > backiter ( vec );
 *backiter = 30;
   backiter++;
 *backiter = 40;

   // Alternatively, insertions can be done with the
   // back_insert_iterator member function
   back_inserter ( vec ) = 500;
   back_inserter ( vec ) = 600;

   cout << "After the insertions, the vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The initial vector vec is: ( 0 1 2 ).
After the insertions, the vector vec is: ( 0 1 2 30 40 500 600 ).
```

## <a name="begin"></a>  Başlangıç

Belirtilen bir kapsayıcıdaki ilk öğe için bir yineleyici alır.

```cpp
template <class Container>
auto begin(Container& cont)  `
   -> decltype(cont.begin());

template <class Container>
auto begin(const Container& cont)   `
   -> decltype(cont.begin());

template <class Ty, class Size>
Ty *begin(Ty (& array)[Size]);
```

### <a name="parameters"></a>Parametreler

`cont` Bir kapsayıcı.

`array` Türündeki nesneler dizisi `Ty`.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevleri dönmek `cont.begin()`. Birinci işlev sabit değil; ikinci sabittir.

Üçüncü şablon işlevi döndürür `array`.

### <a name="example"></a>Örnek

Bu şablon işlevi kapsayıcı üye yerine kullanmanızı öneririz `begin()` daha genel davranış zaman gereklidir.

```cpp
// cl.exe /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <vector>

template <typename C> void reverse_sort(C& c) {
    using std::begin;
    using std::end;

    std::sort(begin(c), end(c), std::greater<>());
}

template <typename C> void print(const C& c) {
    for (const auto& e : c) {
        std::cout << e << " ";
    }

    std::cout << "\n";
}

int main() {
    std::vector<int> v = { 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, 8, 4, 2, 1 };

    print(v);
    reverse_sort(v);
    print(v);

    std::cout << "--\n";

    int arr[] = { 23, 70, 35, 106, 53, 160, 80, 40, 20, 10, 5, 16, 8, 4, 2, 1 };

    print(arr);
    reverse_sort(arr);
    print(arr);
}
```

```Output
11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
52 40 34 26 20 17 16 13 11 10 8 5 4 2 1
--
23 70 35 106 53 160 80 40 20 10 5 16 8 4 2 1
160 106 80 70 53 40 35 23 20 16 10 8 5 4 2 1
```

İşlev `reverse_sort` üyesi olmayan sürümü çağırdığı için normal diziler yanı sıra herhangi bir türde kapsayıcıları destekler `begin()`. Varsa `reverse_sort` kapsayıcı üye kullanılacak kodlanmış `begin()`:

```cpp
template <typename C>
void reverse_sort(C& c) {
    using std::begin;
    using std::end;

    std::sort(c.begin(), c.end(), std::greater<>());

}
```

Ona bir dizi göndermek, bu derleyicinin hata vermesine neden olur:

```Output
error C2228: left of '.begin' must have class/struct/union
```

## <a name="cbegin"></a>  cbegin

Belirtilen kapsayıcıdaki ilk öğeyi izleyen öğeye sabit bir yineleyici alır.

```cpp
template <class Container>
auto cbegin(const Container& cont)
   -> decltype(cont.begin());
```

### <a name="parameters"></a>Parametreler

`cont` Bir kapsayıcı veya initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Bir sabit `cont.begin()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev ile tüm C++ Standart Kitaplığı kapsayıcıları ile çalışır [initializer_list](../standard-library/initializer-list-class.md).

Bu üye işlevi yerine kullanabileceğiniz `begin()` şablon işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) kapsayıcı veya `initializer_list` destekleyen herhangi bir türde `begin()` ve `cbegin()`.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>  cend

Belirtilen kapsayıcıdaki son öğeyi izleyen öğe için sabit bir yineleyici alır.

```cpp
template <class Container>
auto cend(const Container& cont)
   -> decltype(cont.end());
```

### <a name="parameters"></a>Parametreler

`cont` Bir kapsayıcı veya initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Bir sabit `cont.end()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev ile tüm C++ Standart Kitaplığı kapsayıcıları ile çalışır [initializer_list](../standard-library/initializer-list-class.md).

Bu üye işlevi yerine kullanabileceğiniz [end()](../standard-library/iterator-functions.md#end) şablon işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) kapsayıcı veya `initializer_list` destekleyen herhangi bir türde `end()` ve `cend()`.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

## <a name="distance"></a>  uzaklık

İki yineleyici tarafından ele alınan konumlar arasındaki artış sayısını belirler.

```cpp
template <class InputIterator>
typename iterator_traits<InputIterator>::difference_type distance(InputIterator first, InputIterator last);
```

### <a name="parameters"></a>Parametreler

`first` Belirlenecek olan ikinci mesafe olan ilk yineleyici.

`last` Belirlenecek olan ilk mesafe olan ikinci yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Sayısı zaman `first` eşit bu kadar artırılması gereken `last`.

### <a name="remarks"></a>Açıklamalar

Distance işlevi sabit karmaşıklık sahip olduğunda **InputIterator** rasgele erişim yineleyici; gereksinimlerini karşılayan Aksi halde, doğrusal karmaşıklık varsa ve bu nedenle olası pahalıdır.

### <a name="example"></a>Örnek

```cpp
// iterator_distance.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   list<int> L;
   for ( i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( 2 * i );
   }
   list <int>::iterator L_Iter, LPOS = L.begin ( );

   cout << "The list L is: ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   cout << "The iterator LPOS initially points to the first element: "
        << *LPOS << "." << endl;

   advance ( LPOS , 7 );
   cout << "LPOS is advanced 7 steps forward to point "
        << " to the eighth element: "
        << *LPOS << "." << endl;

   list<int>::difference_type Ldiff ;
   Ldiff = distance ( L.begin ( ) , LPOS );
   cout << "The distance from L.begin( ) to LPOS is: "
        << Ldiff << "." << endl;
}
```

```Output
The list L is: ( -2 0 2 4 6 8 10 12 14 16 ).
The iterator LPOS initially points to the first element: -2.
LPOS is advanced 7 steps forward to point  to the eighth element: 12.
The distance from L.begin( ) to LPOS is: 7.
```

## <a name="end"></a>  Bitiş

Belirtilen kapsayıcıdaki son öğeyi izleyen öğeye bir yineleyici alır.

```cpp
template <class Container>
auto end(Container& cont)
   -> decltype(cont.end());

template <class Container>
auto end(const Container& cont)
   -> decltype(cont.end());

template <class Ty, class Size>
Ty *end(Ty (& array)[Size]);
```

### <a name="parameters"></a>Parametreler

`cont` Bir kapsayıcı.

`array` Türündeki nesneler dizisi `Ty`.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevleri dönmek `cont.end()` (sabit olmayan ilk ve ikinci sabittir).

Üçüncü şablon işlevi döndürür `array + Size`.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz: [başlamak](../standard-library/iterator-functions.md#begin).

## <a name="front_inserter"></a>  front_inserter

Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
template <class Container>
front_insert_iterator<Container> front_inserter(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

`_Cont` Bir öğe olan ön sahip olmak kapsayıcı nesnesinin eklenir.

### <a name="return-value"></a>Dönüş Değeri

A `front_insert_iterator` kapsayıcı nesneyle ilişkili `_Cont`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini [front_insert_iterator](../standard-library/front-insert-iterator-class.md#front_insert_iterator) front_insert_iterator sınıfı de kullanılabilir.

C++ Standart Kitaplığı içinde bağımsız değişkeni bir üye fonksiyonu sahip olan iki sırası kapsayıcıları başvurmalıdır `push_back`: [deque sınıfı](../standard-library/deque-class.md) veya "List sınıfı".

### <a name="example"></a>Örnek

```cpp
// iterator_front_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for ( i = -1 ; i < 9 ; ++i )
   {
      L.push_back ( i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the template function to insert an element
   front_insert_iterator< list < int> > Iter(L);
 *Iter = 100;

   // Alternatively, you may use the front_insert member function
   front_inserter ( L ) = 200;

   cout << "After the front insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The list L is:
 ( -1 0 1 2 3 4 5 6 7 8 ).
After the front insertions, the list L is:
 ( 200 100 -1 0 1 2 3 4 5 6 7 8 ).
```

## <a name="inserter"></a>  ekleyici

Kullanmanıza olanak sağlayan bir yardımcı şablon işlevi `inserter(_Cont, _Where)` yerine `insert_iterator<Container>(_Cont, _Where)`.

```cpp
template <class Container>
insert_iterator<Container>
inserter(
    Container& _Cont,
    typename Container::iterator _Where);
```

### <a name="parameters"></a>Parametreler

`_Cont` Yeni öğeler eklemek için olan kapsayıcı.

`_Where` Yineleyici ekleme noktası bulunuyor.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür [insert_iterator](../standard-library/insert-iterator-class.md#insert_iterator)`<Container>(_Cont, _Where)`.

### <a name="example"></a>Örnek

```cpp
// iterator_inserter.cpp
// compile with: /EHsc
#include <iterator>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   list <int>::iterator L_Iter;

   list<int> L;
   for (i = 2 ; i < 5 ; ++i )
   {
      L.push_back ( 10 * i );
   }

   cout << "The list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )
      cout << *L_Iter << " ";
   cout << ")." << endl;

   // Using the template version to insert an element
   insert_iterator<list <int> > Iter( L, L.begin ( ) );
 *Iter = 1;

   // Alternatively, using the member function to insert an element
   inserter ( L, L.end ( ) ) = 500;

   cout << "After the insertions, the list L is:\n ( ";
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)
      cout << *L_Iter << " ";
   cout << ")." << endl;
}
```

```Output
The list L is:
 ( 20 30 40 ).
After the insertions, the list L is:
 ( 1 20 30 40 500 ).
```

## <a name="make_checked_array_iterator"></a>  make_checked_array_iterator

Oluşturur bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) diğer algoritmalar tarafından kullanılabilir.

> [!NOTE]
> Bu işlev, C++ Standart Kitaplığı, bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
checked_array_iterator<Iter>
    make_checked_array_iterator(
 Iter Ptr,
    size_t Size,
    size_t Index = 0);
```

### <a name="parameters"></a>Parametreler

`Ptr` Hedef dizi için bir işaretçi.

`Size` Hedef dizi büyüklüğü.

`Index` Dizi isteğe bağlı dizine.

### <a name="return-value"></a>Dönüş Değeri

Örneği `checked_array_iterator`.

### <a name="remarks"></a>Açıklamalar

`make_checked_array_iterator` İşlevi tanımlanmış `stdext` ad alanı.

Bu işlev bir ham işaretçi alır — hangi normalde neden taşması sınırları ilgili endişeleri — ve içinde saran bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) denetimi yapar sınıfı. Bu sınıf işaretli olarak işaretlendiğinden, C++ Standart Kitaplığı hakkında uyarmak değil. Daha fazla bilgi ve kod örnekleri için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulur ve 10 öğe ile doldurulur. Vektör içeriğini kopyalama algoritması kullanılarak bir diziye kopyalanır ve ardından `make_checked_array_iterator` hedef belirtmek için kullanılır. Bunun ardından sınırların denetiminin bilerek ihlali gelir, böylece bir hata ayıklama onaylama işlemi hatası tetiklenir.

```cpp
// make_checked_array_iterator.cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iterator> // stdext::make_checked_array_iterator
#include <memory> // std::make_unique
#include <iostream>
#include <vector>
#include <string>

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
    const size_t dest_size = 10;
    // Old-school but not exception safe, favor make_unique<int[]>
    // int* dest = new int[dest_size];
    unique_ptr<int[]> updest = make_unique<int[]>(dest_size);
    int* dest = updest.get(); // get a raw pointer for the demo

    vector<int> v;

    for (int i = 0; i < dest_size; ++i) {
        v.push_back(i);
    }
    print("vector v: ", v);

    copy(v.begin(), v.end(), stdext::make_checked_array_iterator(dest, dest_size));

    cout << "int array dest: ";
    for (int i = 0; i < dest_size; ++i) {
        cout << dest[i] << " ";
    }
    cout << endl;

    // Add another element to the vector to force an overrun.
    v.push_back(10);
    // The next line causes a debug assertion when it executes.
    copy(v.begin(), v.end(), stdext::make_checked_array_iterator(dest, dest_size));
}

```

## <a name="make_move_iterator"></a>  make_move_iterator

Oluşturur bir `move iterator` olarak sağlanan yineleyici içeren `stored` yineleyici.

```cpp
template <class Iterator>
move_iterator<Iterator>
make_move_iterator(const Iterator& _It);
```

### <a name="parameters"></a>Parametreler

`_It` Yeni taşıma yineleyici depolanan yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `move_iterator` `<Iterator>(_It)`.

## <a name="make_unchecked_array_iterator"></a>  make_unchecked_array_iterator

Oluşturur bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) diğer algoritmalar tarafından kullanılabilir.

> [!NOTE]
> Bu işlev, C++ Standart Kitaplığı, bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
unchecked_array_iterator<Iter>
    make_unchecked_array_iterator(Iter Ptr);
```

### <a name="parameters"></a>Parametreler

`Ptr` Hedef dizi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Örneği `unchecked_array_iterator`.

### <a name="remarks"></a>Açıklamalar

`make_unchecked_array_iterator` İşlevi tanımlanmış `stdext` ad alanı.

Bu işlev bir ham işaretçi alır ve hiçbir denetimi gerçekleştirir ve bu nedenle hemen bir şey en iyi duruma getirir sınıfında sarmalar, ancak aynı zamanda derleyici uyarıları gibi kapatır [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu nedenle, denetlenmemiş işaretçi uyarılarıyla onları genel olarak susturmadan veya denetleme maliyeti oluşturmadan baş etmek için hedeflenmiş bir yoldur. Daha fazla bilgi ve kod örnekleri için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulur ve 10 öğe ile doldurulur. Vektör içeriğini kopyalama algoritması kullanılarak bir diziye kopyalanır ve ardından `make_unchecked_array_iterator` hedef belirtmek için kullanılır.

```cpp
// make_unchecked_array_iterator.cpp
// compile with: /EHsc /W4 /MTd

#include <algorithm>
#include <iterator> // stdext::make_unchecked_array_iterator
#include <iostream>
#include <vector>
#include <string>

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
    const size_t dest_size = 10;
    int *dest = new int[dest_size];
    vector<int> v;

    for (int i = 0; i < dest_size; ++i) {
        v.push_back(i);
    }
    print("vector v: ", v);

    // COMPILER WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode
    // (it performs no checking, so an overrun will trigger undefined behavior)
    copy(v.begin(), v.end(), stdext::make_unchecked_array_iterator(dest));

    cout << "int array dest: ";
    for (int i = 0; i < dest_size; ++i) {
        cout << dest[i] << " ";
    }
    cout << endl;

    delete[] dest;
}

```

## <a name="next"></a>  Sonraki

Belirtilen sayıda yineler ve yeni yineleyici konumunu döndürür.

```cpp
template <class InputIterator>
InputIterator next(
    InputIterator first,
    typename iterator_traits<InputIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Parametreler

`first` Geçerli konumu.

`_Off` Kaç kez yinelemek için.

### <a name="return-value"></a>Dönüş Değeri

Yineleme sonra yeni yineleyici konumunu döndürür `_Off` kez.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `next` artırılır `_Off` saatleri

## <a name="prev"></a>  Önceki

Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.

```cpp
template <class BidirectionalIterator>
BidirectionalIterator prev(
    BidirectionalIterator first,
    typename iterator_traits<BidirectionalIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Parametreler

`first` Geçerli konumu.

`_Off` Kaç kez yinelemek için.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `next` indirildiği `off` kez.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
