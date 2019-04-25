---
title: '&lt;Yineleyici&gt; işlevleri'
ms.date: 11/04/2016
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
ms.openlocfilehash: f6ea1ac49dabbfc34af9c8ddd020543f606d37a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224148"
---
# <a name="ltiteratorgt-functions"></a>&lt;Yineleyici&gt; işlevleri

||||
|-|-|-|
|[İlerlet](#advance)|[back_inserter](#back_inserter)|[başlayın](#begin)|
|[cbegin](#cbegin)|[cend](#cend)|[uzaklık](#distance)|
|[Son](#end)|[front_inserter](#front_inserter)|[inserter](#inserter)|
|[make_checked_array_iterator](#make_checked_array_iterator)|[make_move_iterator](#make_move_iterator)|[make_unchecked_array_iterator](#make_unchecked_array_iterator)|
|[Sonraki](#next)|[önceki](#prev)|

## <a name="advance"></a>  İlerlet

Belirtilen bir konum sayısıyla yineleyiciyi artırır.

```cpp
template <class InputIterator, class Distance>
void advance(
    InputIterator& InIt,
    Distance Off);
```

### <a name="parameters"></a>Parametreler

*InIt*<br/>
Artırılacak ve bir girişi yineleyicisinin gereksinimleri karşılaması gereken yineleyici.

*Kapalı*<br/>
Yineleyicinin fark türüne dönüştürülebilir ve yineleyici konumunun yükseltileceği artış sayısını belirten integral türü.

### <a name="remarks"></a>Açıklamalar

Aralık gelişimi tekil olmamalıdır, burada yineleyicilerin başvurusu kaldırılmalı veya sonu aşmalıdır.

Varsa `InputIterator` ardından bir çift yönlü yineleyici türü için gereksinimleri karşılayan *kapalı* negatif olabilir. Varsa `InputIterator` bir girişse veya ileri yönlü yineleyici türüyse *kapalı* negatif olmamalıdır.

İleri işlevinde sabit karmaşası vardır, `InputIterator` bir rastgele erişim yineleyici; gereksinimlerini karşılayan Aksi halde doğrusal karmaşıklığa sahiptir ve bu nedenle olası çok maliyetlidir.

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

*_Cont*<br/>
İçine geri ekleme yürütülecek kapsayıcısı.

### <a name="return-value"></a>Dönüş Değeri

A `back_insert_iterator` kapsayıcı nesneyle ilişkili *_Cont*.

### <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı bağımsız değişken bir üye işlevi olan üç dizi kapsayıcılarının başvurmalıdır `push_back`: [deque sınıfı](../standard-library/deque-class.md), [list sınıfı](../standard-library/list-class.md), veya [vektör Sınıf](../standard-library/vector-class.md).

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

## <a name="begin"></a>  başlayın

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

*devamı*<br/>
Bir kapsayıcı.

*Dizi*<br/>
Bir dizi türünde nesne `Ty`.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevi `cont.begin()`. Birinci işlev sabit değil; ikinci sabittir.

Üçüncü şablon işlevinin döndürdüğü *dizi*.

### <a name="example"></a>Örnek

Kapsayıcı üyesi yerine bu şablon işlevi kullanmanızı öneririz `begin()` daha genel davranış zaman gereklidir.

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

İşlev `reverse_sort` normal dizilerin yanı sıra her türde destekler, bu üye olmayan sürümünü çağırdığından `begin()`. Varsa `reverse_sort` kapsayıcı üyesini kullanacak şekilde kodlandıysa `begin()`:

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

*devamı*<br/>
Bir kapsayıcı ya da initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Bir sabit `cont.begin()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev tümüyle çalışır C++ standart kitaplığı kapsayıcıları ile [initializer_list](../standard-library/initializer-list-class.md).

Bu üye işlevi yerine kullanabileceğiniz `begin()` dönüş değeri olacağını garanti etmek için şablon işlevi `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) kapsayıcı veya `initializer_list` destekleyen herhangi bir türdeki `begin()` ve `cbegin()`.

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

*devamı*<br/>
Bir kapsayıcı ya da initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Bir sabit `cont.end()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev tümüyle çalışır C++ standart kitaplığı kapsayıcıları ile [initializer_list](../standard-library/initializer-list-class.md).

Bu üye işlevi yerine kullanabileceğiniz [end()](../standard-library/iterator-functions.md#end) dönüş değeri olacağını garanti etmek için şablon işlevi `const_iterator`. Genellikle birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesinti anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` değiştirilebilir (olmayan **const**) kapsayıcı veya `initializer_list` destekleyen herhangi bir türdeki `end()` ve `cend()`.

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

*ilk*<br/>
Belirlenecek olan ikinci mesafe olan ilk yineleyicisi.

*Son*<br/>
İlk uzaklığı belirlenecek olan ikinci yineleyicisi.

### <a name="return-value"></a>Dönüş Değeri

Sayısı çarpı *ilk* eşit bu kadar artırılması gereken *son*.

### <a name="remarks"></a>Açıklamalar

Uzaklık işlevinde sabit karmaşası vardır, `InputIterator` bir rastgele erişim yineleyici; gereksinimlerini karşılayan Aksi halde doğrusal karmaşıklığa sahiptir ve bu nedenle olası çok maliyetlidir.

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

## <a name="end"></a>  Son

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

*devamı*<br/>
Bir kapsayıcı.

*Dizi*<br/>
Bir dizi türünde nesne `Ty`.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevi `cont.end()` (ilki sabit değil ve ikincisi sabittir).

Üçüncü şablon işlevinin döndürdüğü `array + Size`.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz: [başlamak](../standard-library/iterator-functions.md#begin).

## <a name="front_inserter"></a>  front_inserter

Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
template <class Container>
front_insert_iterator<Container> front_inserter(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*<br/>
Olan ön öğeye sahip kapsayıcı nesnesi eklenir.

### <a name="return-value"></a>Dönüş Değeri

A `front_insert_iterator` kapsayıcı nesneyle ilişkili *_Cont*.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [front_insert_iterator](../standard-library/front-insert-iterator-class.md#front_insert_iterator) front_insert_iterator sınıfı ayrıca kullanılabilir.

C++ Standart Kitaplığı bağımsız değişken bir üye işlevi olan iki dizi kapsayıcılarının başvurmalıdır `push_back`: [deque sınıfı](../standard-library/deque-class.md) veya "Sınıf listesi".

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

## <a name="inserter"></a>  inserter

Kullanmanıza olanak sağlayan bir yardımcı şablon işlevi `inserter(_Cont, _Where)` yerine `insert_iterator<Container>(_Cont, _Where)`.

```cpp
template <class Container>
insert_iterator<Container>
inserter(
    Container& _Cont,
    typename Container::iterator _Where);
```

### <a name="parameters"></a>Parametreler

*_Cont*<br/>
Yeni öğeleri eklenecek olan kapsayıcı.

*_Where*<br/>
Ekleme noktasını bulmak için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü [insert_iterator](../standard-library/insert-iterator-class.md#insert_iterator)`<Container>(_Cont, _Where)`.

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

Oluşturur bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) diğer algoritmalarda kullanılabilen.

> [!NOTE]
> Bu işlev, C++ Standart Kitaplığı'nın bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
checked_array_iterator<Iter>
    make_checked_array_iterator(
Iter Ptr,
    size_t Size,
    size_t Index = 0);
```

### <a name="parameters"></a>Parametreler

*PTR*<br/>
Hedef dizi için işaretçi.

*Boyutu*<br/>
Hedef dizinin boyutu.

*Index*<br/>
Diziye isteğe bağlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Örneği `checked_array_iterator`.

### <a name="remarks"></a>Açıklamalar

`make_checked_array_iterator` İşlevi tanımlanmış `stdext` ad alanı.

Bu işlev, ham bir işaretçiyi alır; önemli sınır taşmasıyla ilgili endişelere neden — ve içine sarmalar bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) sınıfında. C++ Standart Kitaplığı, o sınıf denetlenmiş olarak işaretlendiğinden, bu konuda uyarı vermez. Daha fazla bilgi ve kod örnekleri için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulur ve 10 öğeyle doldurulur. Vektör içeriği kopyalama algoritması kullanılarak bir diziye kopyalanır ve ardından `make_checked_array_iterator` hedef belirtmek için kullanılır. Bunun ardından sınırların denetiminin bilerek ihlali gelir, böylece bir hata ayıklama onaylama işlemi hatası tetiklenir.

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

Oluşturur bir `move iterator` sağlanan yineleyicisi olarak içeren `stored` yineleyici.

```cpp
template <class Iterator>
move_iterator<Iterator>
make_move_iterator(const Iterator& _It);
```

### <a name="parameters"></a>Parametreler

*_Bt*<br/>
Yeni taşıma yineleyicisi depolanan yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `move_iterator` `<Iterator>(_It)`.

## <a name="make_unchecked_array_iterator"></a>  make_unchecked_array_iterator

Oluşturur bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) diğer algoritmalarda kullanılabilen.

> [!NOTE]
> Bu işlev, C++ Standart Kitaplığı'nın bir Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
unchecked_array_iterator<Iter>
    make_unchecked_array_iterator(Iter Ptr);
```

### <a name="parameters"></a>Parametreler

*PTR*<br/>
Hedef dizi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Örneği `unchecked_array_iterator`.

### <a name="remarks"></a>Açıklamalar

`make_unchecked_array_iterator` İşlevi tanımlanmış `stdext` ad alanı.

Bu işlev, ham bir işaretçiyi alır ve hiçbir denetim gerçekleştirmeyen ve bu nedenle hemen bir şey en iyi duruma getirir sınıfında sarmalar, ancak bunu gibi Derleyici uyarılarını da susturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Bu nedenle, denetlenmemiş işaretçi uyarılarıyla onları genel olarak susturmadan veya denetleme maliyeti oluşturmadan baş etmek için hedeflenmiş bir yoldur. Daha fazla bilgi ve kod örnekleri için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulur ve 10 öğeyle doldurulur. Vektör içeriği kopyalama algoritması kullanılarak bir diziye kopyalanır ve ardından `make_unchecked_array_iterator` hedef belirtmek için kullanılır.

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

*ilk*<br/>
Geçerli konumu.

*_Off*<br/>
Kaç kez yinelemek için.

### <a name="return-value"></a>Dönüş Değeri

Yineleme sonra yeni yineleyici konumunu döndürür *_Off* kez.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `next` artan *_Off* saatleri

## <a name="prev"></a>  önceki

Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.

```cpp
template <class BidirectionalIterator>
BidirectionalIterator prev(
    BidirectionalIterator first,
    typename iterator_traits<BidirectionalIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Geçerli konumu.

*_Off*<br/>
Kaç kez yinelemek için.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `next` indirildiği `off` kez.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
