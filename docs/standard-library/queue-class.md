---
title: queue Sınıfı
ms.date: 11/04/2016
f1_keywords:
- queue/std::queue::container_type
- queue/std::queue::size_type
- queue/std::queue::value_type
- queue/std::queue::back
- queue/std::queue::empty
- queue/std::queue::front
- queue/std::queue::pop
- queue/std::queue::push
- queue/std::queue::size
helpviewer_keywords:
- std::queue [C++], container_type
- std::queue [C++], size_type
- std::queue [C++], value_type
- std::queue [C++], back
- std::queue [C++], empty
- std::queue [C++], front
- std::queue [C++], pop
- std::queue [C++], push
- std::queue [C++], size
ms.assetid: 28c20ab0-3a72-4185-9e0f-5a44eea0e204
ms.openlocfilehash: e0bfa4ab037b52b237bd674d5f705de4e9699383
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832613"
---
# <a name="queue-class"></a>queue Sınıfı

Ön ve geri öğelerine erişimi sınırlayan, bazı temel kapsayıcı türleri için bir işlev kısıtlaması sağlayan bir şablon kapsayıcı bağdaştırıcı sınıfı. Öğeler geri eklenebilir veya ön öğeden kaldırılabilir ve öğeler sıranın her iki ucundan de incelenebilir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type, class Container = deque <Type>>
class queue
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Kuyrukta depolanacak öğe veri türü

*Kapsayıcı*\
Kuyruğu uygulamak için kullanılan temeldeki kapsayıcının türü.

## <a name="remarks"></a>Açıklamalar

`Type`Bir kuyruk nesnesinin ilk şablon parametresinde ifade edilen sınıfın öğeleri, [value_type](#value_type) ile eşanlamlıdır ve `Container` ikinci şablon parametresi tarafından belirlenen temeldeki kapsayıcı sınıfında öğe türüyle eşleşmelidir. , `Type` Bu türdeki nesneleri kopyalamak ve bu türdeki değişkenlere değer atamak mümkün olduğundan, atanabilir olmalıdır.

Sıra için uygun temel kapsayıcı sınıfları, [deque](../standard-library/deque-class.md) ,, ve işlemlerini destekleyen herhangi bir sıra kapsayıcısını ve [Listeyi](../standard-library/list-class.md)içerir `front` `back` `push_back` `pop_front` . Temel alınan kapsayıcı sınıfı kapsayıcı bağdaştırıcısında kapsüllenir, bu da yalnızca ortak arabirim olarak dizi kapsayıcısı üye işlevlerinin sınırlı kümesini sunar.

Sıra nesneleri eşitlik karşılaştırılabilir ve yalnızca sınıf öğelerinin `Type` eşitlik karşılaştırılabilir olması halinde ve yalnızca sınıf öğeleri karşılaştırılabilir değilse küçüktür ve karşılaştırılabilir `Type` .

C++ standart kitaplığı tarafından tanımlanan üç tür kapsayıcı bağdaştırıcısı vardır: yığın, kuyruk ve priority_queue. Her biri, standart bir veri yapısına tam denetimli bir arabirim sağlamak için bazı temel kapsayıcı sınıfının işlevlerini kısıtlar.

- [Stack sınıfı](../standard-library/stack-class.md) , son bir ilk çıkar (LIFO) veri yapısını destekler. Göz önünde bulundurmanız gereken bir şey, bir levha yığını olacaktır. Öğeler (levhalar), temel kapsayıcının sonundaki son öğe olan yığının en üstünden eklenebilir, incelenebilir veya kaldırılabilir. Yalnızca Top öğesine erişme kısıtlaması, Stack sınıfının kullanılmasına neden olur.

- Queue sınıfı, ilk kez ilk çıkar (FıFO) veri yapısını destekler. İnsanların bir banka teller için yukarı doğru tutulması yararlı olacaktır. Öğeler (kişiler) satırın arkasına eklenebilir ve satırın önüne kaldırılır. Bir çizginin ön ve arka ucu incelenebilir. Yalnızca ön ve arka öğelerine bu şekilde erişme kısıtlaması, Queue sınıfının kullanılmasına neden olur.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) öğelerini en büyük öğenin her zaman en üstteki konumda olacak şekilde sıralar. Bir öğenin eklenmesini ve en üstteki öğenin incelemesini ve kaldırılmasını destekler. İnsanların yaş, yükseklik veya diğer ölçütlere göre düzenlendikleri yere göz önünde bulundurmanız gereken iyi bir yoldur.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[Sıradaki](#queue)|`queue`Boş veya temel kapsayıcı nesnesinin bir kopyası olan oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[container_type](#container_type)|Tarafından uyarlanabilen temel kapsayıcıyı sağlayan bir tür `queue` .|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `queue` .|
|[value_type](#value_type)|İçindeki bir öğe olarak depolanan nesne türünü temsil eden bir tür `queue` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Geri](#back)|Öğesinin arkasında son ve en son eklenen öğeye bir başvuru döndürür `queue` .|
|[empty](#empty)|`queue`Boşsa sınar.|
|[yapılan](#front)|Öğesinin önündeki ilk öğesine bir başvuru döndürür `queue` .|
|[cağımız](#pop)|Öğesinin önüne bir öğe kaldırır `queue` .|
|[push](#push)|Öğesinin arkasına bir öğesi ekler `queue` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `queue` .|

## <a name="back"></a><a name="back"></a> Geri

Sıranın arkasında son ve en son eklenen öğeye bir başvuru döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruğun son öğesi. Sıra boşsa, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `back` öğesine atanmışsa `const_reference` , kuyruk nesnesi değiştirilemez. Dönüş değeri `back` öğesine atanmışsa `reference` , kuyruk nesnesi değiştirilebilir.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir kuyruktaki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

```cpp
// queue_back.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 11 );

   int& i = q1.back( );
   const int& ii = q1.front( );

   cout << "The integer at the back of queue q1 is " << i
        << "." << endl;
   cout << "The integer at the front of queue q1 is " << ii
        << "." << endl;
}
```

## <a name="container_type"></a><a name="container_type"></a> container_type

Uyarlanabilen temel kapsayıcıyı sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Container` . İki C++ standart kitaplık sırası kapsayıcı sınıfı — List sınıfı ve varsayılan deque Sınıfı — bir kuyruk nesnesi için temel kapsayıcı olarak kullanılacak gereksinimleri karşılar. Gereksinimleri karşılayan Kullanıcı tanımlı türler de kullanılabilir.

Hakkında daha fazla bilgi için `Container` [Queue Class](../standard-library/queue-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için bkz. [kuyruk](#queue) örneği `container_type` .

## <a name="empty"></a><a name="empty"></a> olmamalıdır

Bir kuyruğun boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** sıra boşsa; **`false`** sıra boş değilse.

### <a name="example"></a>Örnek

```cpp
// queue_empty.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
using namespace std;

   // Declares queues with default deque base container
   queue <int> q1, q2;

   q1.push( 1 );

   if ( q1.empty( ) )
      cout << "The queue q1 is empty." << endl;
   else
      cout << "The queue q1 is not empty." << endl;

   if ( q2.empty( ) )
      cout << "The queue q2 is empty." << endl;
   else
      cout << "The queue q2 is not empty." << endl;
}
```

```Output
The queue q1 is not empty.
The queue q2 is empty.
```

## <a name="front"></a><a name="front"></a> yapılan

Kuyruğun önündeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruğun ilk öğesi. Sıra boşsa, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri `front` öğesine atanmışsa `const_reference` , kuyruk nesnesi değiştirilemez. Dönüş değeri `front` öğesine atanmışsa `reference` , kuyruk nesnesi değiştirilebilir.

Üye işlevi, `reference` boş olmayan olması gereken denetlenen sıranın ilk öğesine döndürür.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, boş bir kuyruktaki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

```cpp
// queue_front.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main() {
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   int& ii = q1.back( );
   int& iii = q1.front( );

   cout << "The integer at the back of queue q1 is " << ii
        << "." << endl;
   cout << "The integer at the front of queue q1 is " << iii
        << "." << endl;
}
```

## <a name="pop"></a><a name="pop"></a> cağımız

Bir öğeyi kuyruğun önünden kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulamak için sıranın boş olması gerekir. Kuyruğun en üstü, en son eklenen öğe tarafından bulunan ve kapsayıcının sonundaki son öğe olan pozisyondır.

### <a name="example"></a>Örnek

```cpp
// queue_pop.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, s2;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   i = q1.front( );
   cout << "The element at the front of the queue is "
        << i << "." << endl;

   q1.pop( );

   i = q1.size( );
   cout << "After a pop the queue length is "
        << i << "." << endl;

   i = q1. front ( );
   cout << "After a pop, the element at the front of the queue is "
        << i << "." << endl;
}
```

```Output
The queue length is 3.
The element at the front of the queue is 10.
After a pop the queue length is 2.
After a pop, the element at the front of the queue is 20.
```

## <a name="push"></a><a name="push"></a> hareketle

Kuyruğun arkasına bir öğe ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Sıranın arkasına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Kuyruğun geri dönmesi, en son eklenen öğe tarafından bulunan ve kapsayıcının sonundaki son öğe olan konumudur.

### <a name="example"></a>Örnek

```cpp
// queue_push.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   queue <int>::size_type i;
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   i = q1.front( );
   cout << "The element at the front of the queue is "
        << i << "." << endl;
}
```

```Output
The queue length is 3.
The element at the front of the queue is 10.
```

## <a name="queue"></a><a name="queue"></a> Sıradaki

Boş olan veya temel kapsayıcı nesnesinin bir kopyası olan bir kuyruk oluşturur.

```cpp
queue();

explicit queue(const container_type& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
**`const`** Oluşturulan kuyruğun bir kopya olduğu kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Sıra için varsayılan temel kapsayıcı deque ' tır. Ayrıca, liste temel kapsayıcı olarak belirtebilirsiniz, ancak gerekli üye işlevine sahip olmadığından vektör belirtemezsiniz `pop_front` .

### <a name="example"></a>Örnek

```cpp
// queue_queue.cpp
// compile with: /EHsc
#include <queue>
#include <vector>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares queue with default deque base container
   queue <char> q1;

   // Explicitly declares a queue with deque base container
   queue <char, deque<char> > q2;

   // These lines don't cause an error, even though they
   // declares a queue with a vector base container
   queue <int, vector<int> > q3;
   q3.push( 10 );
   // but the following would cause an error because vector has
   // no pop_front member function
   // q3.pop( );

   // Declares a queue with list base container
   queue <int, list<int> > q4;

   // The second member function copies elements from a container
   list<int> li1;
   li1.push_back( 1 );
   li1.push_back( 2 );
   queue <int, list<int> > q5( li1 );
   cout << "The element at the front of queue q5 is "
        << q5.front( ) << "." << endl;
   cout << "The element at the back of queue q5 is "
        << q5.back( ) << "." << endl;
}
```

```Output
The element at the front of queue q5 is 1.
The element at the back of queue q5 is 2.
```

## <a name="size"></a><a name="size"></a> boyutla

Kuyruktaki öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruğun geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// queue_size.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   queue <int> q1, q2;
   queue <int>::size_type i;

   q1.push( 1 );
   i = q1.size( );
   cout << "The queue length is " << i << "." << endl;

   q1.push( 2 );
   i = q1.size( );
   cout << "The queue length is now " << i << "." << endl;
}
```

```Output
The queue length is 1.
The queue length is now 2.
```

## <a name="size_type"></a><a name="size_type"></a> size_type

Bir kuyruktaki öğelerin sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `size_type` kuyruğa göre uyarlanan taban kapsayıcının eşanlamlısıdır.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için [Queue:: Front](#front) örneğine bakın `size_type` .

## <a name="value_type"></a><a name="value_type"></a> value_type

Bir kuyrukta öğe olarak depolanan nesne türünü temsil eden bir tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `value_type` kuyruğa göre uyarlanan taban kapsayıcının eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// queue_value_type.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
using namespace std;

   // Declares queues with default deque base container
   queue<int>::value_type AnInt;

   AnInt = 69;
   cout << "The value_type is AnInt = " << AnInt << endl;

   queue<int> q1;
   q1.push(AnInt);
   cout << "The element at the front of the queue is "
        << q1.front( ) << "." << endl;
}
```

```Output
The value_type is AnInt = 69
The element at the front of the queue is 69.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
