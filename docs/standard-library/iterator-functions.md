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
ms.openlocfilehash: 69f1007f0c7f587e81313f5de97947410bf243df
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874063"
---
# <a name="ltiteratorgt-functions"></a>&lt;Yineleyici&gt; işlevleri

## <a name="advance"></a>ilerler

Belirtilen bir konum sayısıyla yineleyiciyi artırır.

```cpp
template <class InputIterator, class Distance>
    void advance(InputIterator& InIt, Distance Off);
```

### <a name="parameters"></a>Parametreler

*InIt*\
Artırılacak ve bir girişi yineleyicisinin gereksinimleri karşılaması gereken yineleyici.

*Kapalı*\
Yineleyicinin fark türüne dönüştürülebilir ve yineleyici konumunun yükseltileceği artış sayısını belirten integral türü.

### <a name="remarks"></a>Açıklamalar

Aralık gelişimi tekil olmamalıdır, burada yineleyicilerin başvurusu kaldırılmalı veya sonu aşmalıdır.

`InputIterator` çift yönlü Yineleyici türü için gereksinimleri karşılıyorsa *kapalı* olabilir. `InputIterator` bir giriş veya iletme Yineleyici türü ise *kapalı* olması negatif olmalıdır.

`InputIterator`, Rastgele erişimli bir yineleyici için gereksinimleri karşılıyorsa, Advance işlevinin sabit karmaşıklığı vardır; Aksi takdirde, doğrusal karmaşıklığa sahiptir ve büyük olasılıkla pahalıdır.

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

## <a name="back_inserter"></a>back_inserter

Belirtilen kapsayıcının arkasında öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
template <class Container>
back_insert_iterator<Container> back_inserter(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
Geri eklenen nesnenin yürütüleceği kapsayıcı.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı nesnesiyle ilişkili bir `back_insert_iterator` *_Cont*.

### <a name="remarks"></a>Açıklamalar

C++ Standart kitaplık içinde bağımsız değişken, üye işlevi `push_back`: [deque Class](../standard-library/deque-class.md), [list Class](../standard-library/list-class.md)veya [Vector sınıfı](../standard-library/vector-class.md)olan üç sıra kapsayıcılarından birine başvurmalıdır.

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

## <a name="begin"></a>başladı

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

*devamı*\
Bir kapsayıcı.

*dizi*\
`Ty`türünde bir nesne dizisi.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevi `cont.begin()`döndürür. Birinci işlev sabit değil; ikinci sabittir.

Üçüncü şablon işlevi *diziyi*döndürür.

### <a name="example"></a>Örnek

Daha genel davranış gerektiğinde bu şablon işlevini kapsayıcı üyesi `begin()` yerine kullanmanızı öneririz.

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

İşlev `reverse_sort`, normal dizilere ek olarak, `begin()`üye olmayan sürümünü çağırdığı için, her türlü kapsayıcıları destekler. `reverse_sort` kapsayıcı üyesini kullanmak üzere kodlandıysanız `begin()`:

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

## <a name="cbegin"></a>cbegin

Belirtilen kapsayıcıdaki ilk öğeyi izleyen öğeye sabit bir yineleyici alır.

```cpp
template <class Container>
auto cbegin(const Container& cont)
   -> decltype(cont.begin());
```

### <a name="parameters"></a>Parametreler

*devamı*\
Bir kapsayıcı ya da initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Sabit bir `cont.begin()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev tüm C++ standart kitaplık kapsayıcılarıyla ve [initializer_list](../standard-library/initializer-list-class.md)çalışır.

Dönüş değerinin `const_iterator`olduğundan emin olmak için `begin()` Template işlevinin yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `Container` değiştirilebilir ( **const**olmayan) bir kapsayıcı veya `begin()` ve `cbegin()`destekleyen herhangi bir türde `initializer_list` olacak şekilde düşünün.

```cpp
auto i1 = Container.begin();
// i1 is Container<T>::iterator
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator
```

## <a name="cend"></a>cend

Belirtilen kapsayıcıdaki son öğeyi izleyen öğe için sabit bir yineleyici alır.

```cpp
template <class Container>
auto cend(const Container& cont)
   -> decltype(cont.end());
```

### <a name="parameters"></a>Parametreler

*devamı*\
Bir kapsayıcı ya da initializer_list.

### <a name="return-value"></a>Dönüş Değeri

Sabit bir `cont.end()`.

### <a name="remarks"></a>Açıklamalar

Bu işlev tüm C++ standart kitaplık kapsayıcılarıyla ve [initializer_list](../standard-library/initializer-list-class.md)çalışır.

Dönüş değerinin `const_iterator`olduğundan emin olmak için [End ()](../standard-library/iterator-functions.md#end) şablon işlevi yerine bu üye işlevi kullanabilirsiniz. Genellikle, aşağıdaki örnekte gösterildiği gibi [Otomatik](../cpp/auto-cpp.md) tür kesintisi anahtar sözcüğüyle birlikte kullanılır. Örnekte, `Container` değiştirilebilir ( **const**olmayan) bir kapsayıcı veya `end()` ve `cend()`destekleyen herhangi bir türde `initializer_list` olacak şekilde düşünün.

```cpp
auto i1 = Container.end();
// i1 is Container<T>::iterator
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator
```

## <a name="crbegin"></a>crbegin

```cpp
template <class C> constexpr auto crbegin(const C& c) -> decltype(std::rbegin(c));
```

## <a name="crend"></a>crend

```cpp
template <class C> constexpr auto crend(const C& c) -> decltype(std::rend(c));
```

## <a name="data"></a>verileri

```cpp
template <class C> constexpr auto data(C& c) -> decltype(c.data());
template <class C> constexpr auto data(const C& c) -> decltype(c.data());
template <class T, size_t N> constexpr T* data(T (&array)[N]) noexcept;
template <class E> constexpr const E* data(initializer_list<E> il) noexcept;
```

## <a name="distance"></a>Uzaklık

İki yineleyici tarafından ele alınan konumlar arasındaki artış sayısını belirler.

```cpp
template <class InputIterator>
typename iterator_traits<InputIterator>::difference_type distance(InputIterator first, InputIterator last);
```

### <a name="parameters"></a>Parametreler

*ilk*\
İkinciden uzaklığı belirlenecek olan ilk Yineleyici.

*son*\
Birinciden uzaklığı belirlenecek ikinci Yineleyici.

### <a name="return-value"></a>Dönüş Değeri

*En son*eşit olana kadar *ilk* kaç kez artırılması gerektiği.

### <a name="remarks"></a>Açıklamalar

`InputIterator`, bir rastgele erişim Yineleyici için gereksinimleri karşılıyorsa uzaklık işlevinin sabit karmaşıklığı vardır; Aksi takdirde, doğrusal karmaşıklığa sahiptir ve büyük olasılıkla pahalıdır.

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

## <a name="empty"></a>olmamalıdır

```cpp
template <class C> constexpr auto empty(const C& c) -> decltype(c.empty());
template <class T, size_t N> constexpr bool empty(const T (&array)[N]) noexcept;
template <class E> constexpr bool empty(initializer_list<E> il) noexcept;
```

## <a name="end"></a>erer

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

*devamı*\
Bir kapsayıcı.

*dizi*\
`Ty`türünde bir nesne dizisi.

### <a name="return-value"></a>Dönüş Değeri

İlk iki şablon işlevi `cont.end()` döndürür (ilki sabit değildir ve ikincisi sabittir).

Üçüncü şablon işlevi `array + Size`döndürür.

### <a name="remarks"></a>Açıklamalar

Kod örneği için bkz. [Begin](../standard-library/iterator-functions.md#begin).

## <a name="front_inserter"></a>front_inserter

Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.

```cpp
template <class Container>
front_insert_iterator<Container> front_inserter(Container& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
Önünden bir öğesi bulunan kapsayıcı nesne.

### <a name="return-value"></a>Dönüş Değeri

Kapsayıcı nesnesiyle ilişkili bir `front_insert_iterator` *_Cont*.

### <a name="remarks"></a>Açıklamalar

Front_insert_iterator sınıfının üye işlevi [front_insert_iterator](../standard-library/front-insert-iterator-class.md#front_insert_iterator) de kullanılabilir.

C++ Standart kitaplık içinde bağımsız değişken, üye işlevi `push_back`: [deque Class](../standard-library/deque-class.md) veya "list Class" olan iki dizi kapsayıcılarından birine başvurmalıdır.

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

## <a name="inserter"></a>inserter

`insert_iterator<Container>(_Cont, _Where)`yerine `inserter(_Cont, _Where)` kullanmanıza olanak sağlayan bir yardımcı şablon işlevi.

```cpp
template <class Container>
insert_iterator<Container>
inserter(
    Container& _Cont,
    typename Container::iterator _Where);
```

### <a name="parameters"></a>Parametreler

*_Cont*\
Yeni öğelerin ekleneceği kapsayıcı.

*_Where*\
Ekleme noktasını bulmak için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi [insert_iterator](../standard-library/insert-iterator-class.md#insert_iterator)`<Container>(_Cont, _Where)`döndürür.

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

## <a name="make_checked_array_iterator"></a>make_checked_array_iterator

Diğer algoritmalar tarafından kullanılabilen bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) oluşturur.

> [!NOTE]
> Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
checked_array_iterator<Iter>
    make_checked_array_iterator(
Iter Ptr,
    size_t Size,
    size_t Index = 0);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Hedef dizi için işaretçi.

*Boyut*\
Hedef dizinin boyutu.

*Dizin*\
Diziye isteğe bağlı dizin.

### <a name="return-value"></a>Dönüş Değeri

`checked_array_iterator` öğesinin bir örneği.

### <a name="remarks"></a>Açıklamalar

`make_checked_array_iterator` işlevi `stdext` ad alanında tanımlanmıştır.

Bu işlev, bir ham işaretçi alır — bu, normalde sınır taşmasına neden olur ve bunu denetleyen bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) sınıfında sarmalar. Bu sınıf işaretli olarak işaretlendiğinden, C++ standart kitaplık onunla ilgili uyarı vermez. Daha fazla bilgi ve kod örnekleri için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulup 10 öğeyle doldurulur. Vektör içeriği, kopyalama algoritmasını kullanarak bir diziye kopyalanır ve sonra `make_checked_array_iterator` hedefi belirtmek için kullanılır. Bunun ardından sınırların denetiminin bilerek ihlali gelir, böylece bir hata ayıklama onaylama işlemi hatası tetiklenir.

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

## <a name="make_move_iterator"></a>make_move_iterator

`stored` Yineleyici olarak belirtilen yineleyiciyi içeren bir `move iterator` oluşturur.

```cpp
template <class Iterator>
move_iterator<Iterator>
make_move_iterator(const Iterator& _It);
```

### <a name="parameters"></a>Parametreler

*_It*\
Yeni taşıma yineleyicisinin içinde depolanan yineleyici.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `move_iterator` `<Iterator>(_It)`döndürür.

## <a name="make_unchecked_array_iterator"></a>make_unchecked_array_iterator

Diğer algoritmalar tarafından kullanılabilen bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) oluşturur.

> [!NOTE]
> Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.

```cpp
template <class Iter>
unchecked_array_iterator<Iter>
    make_unchecked_array_iterator(Iter Ptr);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Hedef dizi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`unchecked_array_iterator` öğesinin bir örneği.

### <a name="remarks"></a>Açıklamalar

`make_unchecked_array_iterator` işlevi `stdext` ad alanında tanımlanmıştır.

Bu işlev, ham bir işaretçi alır ve bunu denetim olmayan bir sınıfta sarmalayıp hiçbir şey yapmaz, ancak [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)gibi derleyici uyarılarını da susturun. Bu nedenle, denetlenmemiş işaretçi uyarılarıyla onları genel olarak susturmadan veya denetleme maliyeti oluşturmadan baş etmek için hedeflenmiş bir yoldur. Daha fazla bilgi ve kod örnekleri için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, bir [vektör](../standard-library/vector-class.md) oluşturulup 10 öğeyle doldurulur. Vektör içeriği, kopyalama algoritmasını kullanarak bir diziye kopyalanır ve sonra `make_unchecked_array_iterator` hedefi belirtmek için kullanılır.

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

## <a name="next"></a>ileri

Belirtilen sayıda yineler ve yeni yineleyici konumunu döndürür.

```cpp
template <class InputIterator>
InputIterator next(
    InputIterator first,
    typename iterator_traits<InputIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Parametreler

*ilk*\
Geçerli konum.

*_Off*\
Yinelenme sayısı.

### <a name="return-value"></a>Dönüş Değeri

*_Off* kez yineledikten sonra yeni Yineleyici konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `next` artan *_Off* kez döndürür

## <a name="prev"></a>önceki

Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.

```cpp
template <class BidirectionalIterator>
BidirectionalIterator prev(
    BidirectionalIterator first,
    typename iterator_traits<BidirectionalIterator>::difference_type _Off = 1);
```

### <a name="parameters"></a>Parametreler

*ilk*\
Geçerli konum.

*_Off*\
Yinelenme sayısı.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `next` azaltma `off` zaman döndürür.

## <a name="rbegin"></a>rbegin

```cpp
template <class C> constexpr auto rbegin(C& c) -> decltype(c.rbegin());
template <class C> constexpr auto rbegin(const C& c) -> decltype(c.rbegin());
```

## <a name="rend"></a>rend

```cpp
template <class C> constexpr auto rend(C& c) -> decltype(c.rend());
template <class C> constexpr auto rend(const C& c) -> decltype(c.rend());
```

## <a name="size"></a>boyutla

```cpp
template <class C> constexpr auto size(const C& c) -> decltype(c.size());
template <class T, size_t N> constexpr size_t size(const T (&array)[N]) noexcept;
```
