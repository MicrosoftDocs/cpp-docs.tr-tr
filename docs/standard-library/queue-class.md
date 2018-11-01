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
ms.openlocfilehash: 2b82e4237a525b09758323ae2483d8818fc938af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429737"
---
# <a name="queue-class"></a>queue Sınıfı

Ön ve arka öğelere erişim sınırlama bazı temel alınan kapsayıcı türü için bir kısıtlama işlevsellik sağlayan şablon kapsayıcı bağdaştırıcı sınıfı. Öğe geri eklenebilir veya önünden kaldırıldı ve öğeleri ya da sıranın sonunda denetlenecek.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container = deque <Type>>
class queue
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Kuyrukta depolanacak öğe veri türü

*Kapsayıcı*<br/>
Sıranın uygulamak için kullanılan temel alınan kapsayıcı türü.

## <a name="remarks"></a>Açıklamalar

Sınıfına ait öğelerin `Type` ilk şablon, belirlenen bir sıra nesnesi parametresinin işlevlerindeki [value_type](#value_type) ve temel alınan kapsayıcı sınıfı bir öğenin türüyle eşleşmelidir `Container` tarafından görünürlüğe İkinci şablon parametresi. `Type` Türündeki nesnelerin kopyalayın ve bu türün değişkenlerine değer atamak için mümkün olması atanabilir, olmalıdır.

Sıra için uygun alt kapsayıcı sınıflarını içerir [deque](../standard-library/deque-class.md) ve [listesi](../standard-library/list-class.md), ya da işlemleri destekleyen herhangi bir dizisi kapsayıcısına `front`, `back`, `push_back`, ve `pop_front`. Temel alınan kapsayıcı sınıfı, ortak bir arabirim olarak sıralı kapsayıcı üye işlevleri sınırlı sayıda yalnızca sunan kapsayıcı bağdaştırıcısı içinde kapsüllenir.

Sıranın nesnelerini: eşitlik için karşılaştırılabilir ise ve yalnızca sınıfın öğelerine `Type` eşitlik benzerdir ve küçük-karşılaştırılabilir ve yalnızca daha sınıfına ait öğelerin `Type` küçüktür-daha karşılaştırılabilir.

Kapsayıcı bağdaştırıcıları C++ Standart Kitaplığı tarafından tanımlanan üç tür vardır: priority_queue yığın ve kuyruk. Her bir standart veri yapısı için kesin bir şekilde denetlenen bir arabirim sağlamak üzere temel alınan bazı kapsayıcı sınıfı işlevselliğini kısıtlar.

- [Yığın sınıfı](../standard-library/stack-class.md) son giren ilk çıkar (LIFO) veri yapısı destekler. Akılda tutulması için iyi bir analog kalıplarını yığınını olacaktır. Öğeleri (kalıplarını) eklendiğinde, inceledi veya yalnızca en son öğe temel kapsayıcı sonunda yığın kaldırılır. Yalnızca üst öğesi erişme kısıtlamasını stack sınıfı kullanarak nedenidir.

- Queue sınıfı bir ilk giren ilk çıkar (FIFO) veri yapısını destekler. Akılda tutulması için iyi bir analog bir banka gişe için hizalama kişi olacaktır. Öğeleri (kişi), satırın geri eklenebilir ve satır önünden kaldırılır. Hem ön hem de bir satırın geri inceledi. Bu şekilde yalnızca ön ve arka öğelere erişme kısıtlamasını queue sınıfı kullanarak nedenidir.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) en büyük öğe her zaman üst konumunda olması, öğeleri sıralar. Bu, bir öğe ve inceleme, ekleme ve kaldırma üst öğenin destekler. Burada, yaş, yüksekliğe veya diğer bir ölçüte göre düzenlenmiş yukarı hizalama kişiler akılda tutulması için iyi bir analog olacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Kuyruk](#queue)|Oluşturur bir `queue` boş veya bir temel kapsayıcı nesnesinin bir kopyasını başka bir deyişle olduğu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Temel olarak uyarlanabilen kapsayıcıya sağlayan bir tür `queue`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `queue`.|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil eden bir tür bir `queue`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Geri](#back)|Döndürür bir başvuru son ve en son eklenen öğenin konumundaki yedeklemesini `queue`.|
|[boş](#empty)|Olmadığını test eder `queue` boştur.|
|[Ön](#front)|Önündeki ilk öğeye bir başvuru döndürür `queue`.|
|[POP](#pop)|Bir öğeyi önünden kaldırır `queue`.|
|[push](#push)|Bir öğe geri ekler `queue`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `queue`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kuyruk >

**Namespace:** std

## <a name="back"></a>  Queue::Back

Başvuru öğesi kuyruk arkasına son ve en son eklenen döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıranın son öğesi. Sıranın boş ise, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `back` atanan bir `const_reference`, kuyruk nesnesi değiştirilemez. Varsa dönüş değerinin `back` atanan bir `reference`, kuyruk nesnesi değiştirilebilir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir sorgudaki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

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

## <a name="container_type"></a>  Queue::container_type

Temel uyarlanabilen kapsayıcıya sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Container`. İki C++ Standart Kitaplığı dizisi kapsayıcı sınıfları — listesi sınıfı ve varsayılan deque sınıfı — gereksinimlerini sıra nesnesi için temel bir kapsayıcı olarak kullanılacak. Kullanıcı tanımlı türler gereksinimlerini karşılamadığınızı de kullanılabilir.

Daha fazla bilgi için `Container`, Açıklamalar bölümüne bakın [sınıfı sıra](../standard-library/queue-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [kuyruk](#queue) bildirme ve kullanma konusunda bir örnek için `container_type`.

## <a name="empty"></a>  Queue::empty

Bir kuyruğu boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın boşsa; **false** sıranın boş ise.

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

## <a name="front"></a>  Queue::Front

Kuyruğun önündeki ilk öğeye bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruğun ilk öğe. Sıranın boş ise, dönüş değeri tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerinin `front` atanan bir `const_reference`, kuyruk nesnesi değiştirilemez. Varsa dönüş değerinin `front` atanan bir `reference`, kuyruk nesnesi değiştirilebilir.

Üye işlevi döndürür bir `reference` değerinin denetlenen dizideki ilk öğeye olması gereken boş.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) 1 veya 2 ' tanımlı, boş bir sorgudaki bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

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

## <a name="pop"></a>  Queue::POP

Bir öğenin sıra önünden kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Sıranın üye işlevi uygulamak için boş olmamalıdır. Sıranın üstüne en son eklenen öğe tarafından kullanılan konumu ve kapsayıcı sonunda son bir öğedir.

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

## <a name="push"></a>  Queue::push

Kuyruğun arkasına bir öğe ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Kuyruğun geri eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Geri kuyruğun en son eklenen öğe tarafından kullanılan konumu ve son öğe kapsayıcı sonunda.

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

## <a name="queue"></a>  Queue::Queue

Bir kuyruğu boş olan veya bir temel kapsayıcı nesnesinin bir kopyasını oluşturur.

```cpp
queue();

explicit queue(const container_type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
**Const** kapsayıcı oluşturulan kuyruk olduğu kopyası olacak.

### <a name="remarks"></a>Açıklamalar

Varsayılan temel kuyruk deque kapsayıcıdır. Liste temel bir kapsayıcı olarak da belirtebilirsiniz, ancak gerekli olmadığı için vektör, belirtemezsiniz `pop_front` üye işlevi.

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

## <a name="size"></a>  Queue::size

Sırasındaki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruk uzunluğu.

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

## <a name="size_type"></a>  Queue::size_type

Kuyruktaki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `size_type` tarafından sıraya göre uyarlanmış temel kapsayıcının.

### <a name="example"></a>Örnek

Örneğin bakın [queue::front](#front) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="value_type"></a>  Queue::value_type

Kuyruktaki bir öğe olarak depolanan nesne türünü temsil eden tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `value_type` tarafından sıraya göre uyarlanmış temel kapsayıcının.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
