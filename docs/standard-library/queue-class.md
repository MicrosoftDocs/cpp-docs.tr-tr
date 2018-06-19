---
title: Sınıf sıraya | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5442888e8e370892add687c21132e397ae683ac8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861509"
---
# <a name="queue-class"></a>queue Sınıfı

Ön ve arka öğelere erişimi sınırlandırma bazı temel kapsayıcı türü için bir kısıtlama işlevselliği sağlayan bir şablon kapsayıcı bağdaştırıcısının sınıfı. Öğeleri geri eklenemez veya önden kaldırıldı ve öğeleri ya da sıra sonunda denetlenecek.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container = deque <Type>>
class queue
```

### <a name="parameters"></a>Parametreler

*Tür* öğesi veri türü sırada depolanması

`Container` Sıranın uygulamak için kullanılan temel kapsayıcı türü.

## <a name="remarks"></a>Açıklamalar

Sınıfının öğeleri **türü** ilk şablon, belirlenen bir sıra nesnesi parametresi ile eşanlamlı [value_type](#value_type) ve arka plandaki kapsayıcı sınıfı öğetürüeşleşmelidir**Kapsayıcı** ikinci şablon parametresi tarafından belirlenen. **Türü** böylece bu tür nesneleri kopyalayın ve bu tür değişkenlere değerler atayın olası atanabilir, olması gerekir.

Sıra için uygun temel kapsayıcı sınıfları dahil [deque](../standard-library/deque-class.md) ve [listesi](../standard-library/list-class.md), veya işlemlerini destekleyen herhangi bir sıra kapsayıcısına `front`, **geri** , `push_back`, ve `pop_front`. Temel alınan kapsayıcı sınıfı yalnızca sıralı kapsayıcı üye işlevleri sınırlı sayıda ortak bir arabirim olarak kullanıma sunar kapsayıcı bağdaştırıcısı içinde kapsüllenir.

Sıranın nesneleri: eşitlik için karşılaştırılabilir IF ve yalnızca sınıfı öğelerini **türü** eşitlik için karşılaştırılabilir ve küçük-karşılaştırılabilir IF ve yalnızca'den sınıfı öğelerini **türü** küçüktür-daha karşılaştırılabilir.

C++ Standart Kitaplığı tarafından tanımlanan kapsayıcı bağdaştırıcıları üç tür vardır: yığın ve kuyruk priority_queue. Her bir standart veri yapısı için tam olarak denetlenen bir arabirim sağlamak için bazı temel kapsayıcı sınıfı işlevselliğini kısıtlar.

- [Yığın sınıfı](../standard-library/stack-class.md) son giren ilk çıkar (LIFO) veri yapısı destekler. Göz önünde bulundurmanız iyi bir analog kalıplarını yığınını olacaktır. Öğeleri (kalıplarını) eklenen, Denetlenmekte veya yalnızca en son öğe temel kapsayıcı sonunda yığınının kaldırıldı. Yalnızca üst öğesi erişmek için yığın sınıfını kullanarak nedeni kısıtlamadır.

- Queue sınıfı ilk çıkar (FIFO) veri yapısı destekler. Göz önünde bulundurmanız iyi bir analog banka teller için hizalama kişiler olacaktır. Öğeleri (kişiler) satırın arkasına eklenebilir ve satır Önden kaldırılır. Ön ve arka satırının denetlenecek. Yalnızca ön ve arka öğeleri bu şekilde erişmek için kısıtlama sıra sınıfını kullanarak nedenidir.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) en büyük öğe her zaman üst konumunda böylece öğeleri sıralar. Bir öğe ve İnceleme ekleme ve kaldırma üst öğesinin destekler. Göz önünde bulundurmanız iyi bir analog burada bunlar yaşı, yükseklik veya başka bir ölçüt göre düzenlenmiş yukarı hizalama kişiler olacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Sırası](#queue)|Oluşturan bir `queue` diğer bir deyişle boş ya da bir taban kapsayıcı nesnesinin kopyasıdır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Temel olarak uyarlanan kapsayıcıya sağlayan bir türü `queue`.|
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `queue`.|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil eden bir tür bir `queue`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Geri](#back)|Bir başvuru son en son eklenen ve öğenin adresindeki yedeklemesini döndürür `queue`.|
|[boş](#empty)|Varsa testleri `queue` boş.|
|[Ön](#front)|İlk öğe ön kısmında bir başvuru döndürür `queue`.|
|[POP](#pop)|Bir öğenin önüne kaldırır `queue`.|
|[push](#push)|Bir öğe için arkası ekler `queue`.|
|[Boyutu](#size)|Öğelerin sayısını döndürür `queue`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sıra >

**Namespace:** std

## <a name="back"></a>  Queue::Back

Eklenen son ve en son öğesi sıranın arkasındaki bir başvuru döndürür.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıranın son öğesi. Sıranın boş ise, dönüş değeri tanımlanmamıştır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerini **geri** atanmış bir `const_reference`, sıra nesnesi değiştirilemez. Varsa dönüş değerini **geri** atanmış bir **başvuru**, sıra nesnesinin değiştirilebilir.

Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) bir öğe boş bir sorgudaki erişmeyi denerseniz, 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası meydana gelir.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.

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

Temel uyarlanan kapsayıcıya sağlayan türü.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `Container`. İki C++ Standart Kitaplığı dizisi kapsayıcı sınıfları — listesi ve varsayılan deque sınıf — bir sıra nesnesi için temel kapsayıcı olarak kullanılacak gereksinimlerini. Kullanıcı tanımlı türler gereksinimleri karşılayan de kullanılabilir.

Daha fazla bilgi için `Container`, Açıklamalar bölümüne bakın [sınıfı sıraya](../standard-library/queue-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [sıra](#queue) bildirme ve kullanma konusunda bir örnek için `container_type`.

## <a name="empty"></a>  Queue::empty

Bir kuyruk boşsa, testleri.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** sıranın boşsa; **false** sıranın boş olmayan ise.

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

Sıranın önünü konumundaki ilk öğe için bir başvuru döndürür.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıranın ilk öğesi. Sıranın boş ise, dönüş değeri tanımlanmamıştır.

### <a name="remarks"></a>Açıklamalar

Varsa dönüş değerini `front` atanmış bir `const_reference`, sıra nesnesi değiştirilemez. Varsa dönüş değerini `front` atanmış bir **başvuru**, sıra nesnesinin değiştirilebilir.

Üye işlevi döndürür bir **başvuru** denetimli dizisinin ilk öğeye olması gerekir boş.

Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) bir öğe boş bir sorgudaki erişmeyi denerseniz, 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası meydana gelir.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.

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

Bir öğenin sıra Önden kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Sıranın üye fonksiyonu uygulamak için boş olmamalıdır. Üst sıra en son eklenen öğesi tarafından bulunulan konum ve kapsayıcı ucundaki son öğe.

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

Bir öğeyi sıranın arkasına ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

`val` Sıranın arkasına eklenen öğesi.

### <a name="remarks"></a>Açıklamalar

Sıranın geri en son eklenen öğesi tarafından bulunulan konum ve kapsayıcı ucundaki son öğe.

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

Boş veya temel kapsayıcı nesnesinin bir kopyasını olan bir sıra oluşturur.

```cpp
queue();

explicit queue(const container_type& right);
```

### <a name="parameters"></a>Parametreler

`right` **Const** oluşturulan sıra olduğu bir kopyasını olması için kapsayıcı.

### <a name="remarks"></a>Açıklamalar

Sıra için varsayılan taban kapsayıcı deque ' dir. Liste temel bir kapsayıcı olarak belirtebilirsiniz, ancak gerekli eksik olduğundan vektörü belirtemezsiniz `pop_front` üye işlevi.

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

Sırası uzunluğu.

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

Bir kuyruktaki öğelerin sayısı gösterebilir bir işaretsiz tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `size_type` sıranın uyarlanan temel kapsayıcısı.

### <a name="example"></a>Örnek

Örneğin bkz [queue::front](#front) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="value_type"></a>  Queue::value_type

Bir kuyruktaki bir öğe olarak depolanan nesne türünü temsil eden tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `value_type` sıranın uyarlanan temel kapsayıcısı.

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
