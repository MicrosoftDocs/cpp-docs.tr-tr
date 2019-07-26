---
title: priority_queue Sınıfı
ms.date: 11/04/2016
f1_keywords:
- queue/std::priority_queue::container_type
- queue/std::priority_queue::size_type
- queue/std::priority_queue::value_type
- queue/std::priority_queue::empty
- queue/std::priority_queue::pop
- queue/std::priority_queue::push
- queue/std::priority_queue::size
- queue/std::priority_queue::top
helpviewer_keywords:
- std::priority_queue [C++], container_type
- std::priority_queue [C++], size_type
- std::priority_queue [C++], value_type
- std::priority_queue [C++], empty
- std::priority_queue [C++], pop
- std::priority_queue [C++], push
- std::priority_queue [C++], size
- std::priority_queue [C++], top
ms.assetid: 69fca9cc-a449-4be4-97b7-02ca5db9cbb2
ms.openlocfilehash: 3591264efec87c2c3454d0f885c19b30b73ae51c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458423"
---
# <a name="priorityqueue-class"></a>priority_queue Sınıfı

Her zaman en büyük veya en yüksek önceliğe sahip olan, temel alınan kapsayıcı türünün üst öğesine erişimi sınırlayan bir işlev kısıtlaması sağlayan bir şablon kapsayıcı bağdaştırıcı sınıfı. Yeni öğeler priority_queue eklenebilir ve priority_queue öğesinin üst öğesi incelenebilir veya kaldırılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>
class priority_queue
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Priority_queue içinde depolanacak öğe veri türü.

*Kapsayıcı*\
Priority_queue uygulamak için kullanılan temeldeki kapsayıcının türü.

*Karşılaştır*\
Priority_queue içinde göreli sıralarını belirleyebilmek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<typename Container::value_type>` varsayılan değerdir.

## <a name="remarks"></a>Açıklamalar

Bir kuyruk nesnesinin ilk `Type` Şablon parametresinde stıpulan sınıfının öğeleri, [value_type](#value_type) ile eşanlamlı ve ikinci şablon tarafından kullanılan temeldeki kapsayıcı sınıfında `Container` öğe türüyle eşleşmesi gerekir parametresinin. , `Type` Bu türdeki nesneleri kopyalamak ve bu türdeki değişkenlere değer atamak mümkün olduğundan, atanabilir olmalıdır.

Priority_queue, sınıfının `Traits`saklı işlev nesnesini çağırarak denetlediği diziyi sıralar. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur.

Priority_queue için uygun temel kapsayıcı sınıfları, [deque Sınıfı](../standard-library/deque-class.md) ve varsayılan [vektör sınıfı](../standard-library/vector-class.md) ya da, `front` `push_back`, ve `pop_back` ' nin işlemlerini destekleyen başka herhangi bir dizi kapsayıcısı içerir. Rastgele erişimli Yineleyici. Temel alınan kapsayıcı sınıfı kapsayıcı bağdaştırıcısında kapsüllenir, bu da yalnızca ortak arabirim olarak dizi kapsayıcısı üye işlevlerinin sınırlı kümesini sunar.

`priority_queue` Her ikisinde de öğe eklemek ve öğeleri kaldırmak Logaritmik karmaşıklığa sahiptir. İçindeki öğelerine erişmek sabit `priority_queue` karmaşıklığa sahiptir.

C++ Standart kitaplık tarafından tanımlanan üç tür kapsayıcı bağdaştırıcısı vardır: yığın, kuyruk ve priority_queue. Her biri, standart bir veri yapısına tam denetimli bir arabirim sağlamak için bazı temel kapsayıcı sınıfının işlevlerini kısıtlar.

- [Stack sınıfı](../standard-library/stack-class.md) , son bir ilk çıkar (LIFO) veri yapısını destekler. Göz önünde bulundurmanız gereken bir şey, bir levha yığını olacaktır. Öğeler (levhalar), temel kapsayıcının sonundaki son öğe olan yığının en üstünden eklenebilir, incelenebilir veya kaldırılabilir. Yalnızca Top öğesine erişme kısıtlaması, Stack sınıfının kullanılmasına neden olur.

- [Queue sınıfı](../standard-library/queue-class.md) , ilk kez ilk çıkar (FIFO) veri yapısını destekler. İnsanların bir banka teller için yukarı doğru tutulması yararlı olacaktır. Öğeler (kişiler) satırın arkasına eklenebilir ve satırın önüne kaldırılır. Bir çizginin ön ve arka ucu incelenebilir. Yalnızca ön ve arka öğelerine bu şekilde erişme kısıtlaması, Queue sınıfının kullanılmasına neden olur.

- Priority_queue sınıfı, öğelerini en büyük öğenin her zaman en üstteki konumda olacak şekilde sıralar. Bir öğenin eklenmesini ve en üstteki öğenin incelemesini ve kaldırılmasını destekler. İnsanların yaş, yükseklik veya diğer ölçütlere göre düzenlendikleri yere göz önünde bulundurmanız gereken iyi bir yoldur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[priority_queue](#priority_queue)|Boş olan veya bir taban kapsayıcı nesnesi aralığının bir kopyası olan veya diğer `priority_queue`bir sürümü olan oluşturur. `priority_queue`|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Tarafından uyarlanabilen temel kapsayıcıyı sağlayan bir tür `priority_queue`.|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `priority_queue`.|
|[value_type](#value_type)|İçindeki bir öğe olarak depolanan nesne türünü temsil eden bir tür `priority_queue`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[empty](#empty)|`priority_queue` Boşsa sınar.|
|[cağımız](#pop)|Üst konumundan en büyük öğesini `priority_queue` kaldırır.|
|[push](#push)|< İşleçten öğe önceliğine göre öncelik sırasına bir öğe ekler.|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `priority_queue`.|
|[Sayfanın Üstü](#top)|En üstündeki `priority_queue`en büyük öğeye bir const başvurusu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sıra >

**Ad alanı:** std

## <a name="container_type"></a>priority_queue::container_type

Uyarlanabilen temel kapsayıcıyı sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Container`için bir eş anlamlı. C++ Standart kitaplık sırası kapsayıcı sınıfı `deque` ve varsayılan sınıf `vector` , bir priority_queue nesnesi için temel kapsayıcı olarak kullanılacak gereksinimleri karşılar. Gereksinimleri karşılayan Kullanıcı tanımlı türler de kullanılabilir.

Hakkında `Container`daha fazla bilgi için [priority_queue Class](../standard-library/priority-queue-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma `container_type`hakkında bir örnek için bkz. [priority_queue](#priority_queue) .

## <a name="empty"></a>priority_queue:: Empty

Bir priority_queue boş ise sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

priority_queue boşsa **doğru** ; Priority_queue boş değilse **false** .

### <a name="example"></a>Örnek

```cpp
// pqueue_empty.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares priority_queues with default deque base container
   priority_queue <int> q1, s2;

   q1.push( 1 );

   if ( q1.empty( ) )
      cout << "The priority_queue q1 is empty." << endl;
   else
      cout << "The priority_queue q1 is not empty." << endl;

   if ( s2.empty( ) )
      cout << "The priority_queue s2 is empty." << endl;
   else
      cout << "The priority_queue s2 is not empty." << endl;
}
```

```Output
The priority_queue q1 is not empty.
The priority_queue s2 is empty.
```

## <a name="pop"></a>priority_queue::p op

En büyük priority_queue öğesini üst konumdan kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulamak için priority_queue boş olmamalıdır. Priority_queue üst öğesi her zaman kapsayıcıdaki en büyük öğe tarafından kullanılır.

### <a name="example"></a>Örnek

```cpp
// pqueue_pop.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   priority_queue <int> q1, s2;

   q1.push( 10 );
   q1.push( 20 );
   q1.push( 30 );

   priority_queue <int>::size_type i, iii;
   i = q1.size( );
   cout << "The priority_queue length is " << i << "." << endl;

   const int& ii = q1.top( );
   cout << "The element at the top of the priority_queue is "
        << ii << "." << endl;

   q1.pop( );

   iii = q1.size( );
   cout << "After a pop, the priority_queue length is "
        << iii << "." << endl;

   const int& iv = q1.top( );
   cout << "After a pop, the element at the top of the "
        << "priority_queue is " << iv << "." << endl;
}
```

```Output
The priority_queue length is 3.
The element at the top of the priority_queue is 30.
After a pop, the priority_queue length is 2.
After a pop, the element at the top of the priority_queue is 20.
```

## <a name="priority_queue"></a>priority_queue::p riority_queue

Boş olan veya bir taban kapsayıcı nesnesi aralığının veya başka bir priority_queue kopyası olan bir priority_queue oluşturur.

```cpp
priority_queue();

explicit priority_queue(const Traits& _comp);

priority_queue(const Traits& _comp, const container_type& _Cont);

priority_queue(const priority_queue& right);

template <class InputIterator>
priority_queue(InputIterator first, InputIterator last);

template <class InputIterator>
priority_queue(InputIterator first, InputIterator last, const Traits& _comp);

template <class InputIterator>
priority_queue(InputIterator first, InputIterator last, const Traits& _comp, const container_type& _Cont);
```

### <a name="parameters"></a>Parametreler

*_Comp*\
**ConstTraits** türünün, temel kapsayıcının işlevine varsayılan olarak karşılaştırılacak olan priority_queue öğelerini sıralamak için kullanılan karşılaştırma işlevi.

*_Devamı*\
Oluşturulan priority_queue bir kopya olması gereken temel kapsayıcı.

*Right*\
Oluşturulan kümesinin bir kopya olması priority_queue.

*adı*\
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*soyadına*\
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

İlk üç oluşturucuların her biri boş bir başlangıç priority_queue belirtir; ikinci olarak, öğelerin sırasını ve üçüncü açıkça şunu belirtmek`comp` `container_type`içinkullanılacakkarşılaştırmaişlevitürünü()debelirtin.(`_Cont`) kullanılacak. **Explicit** anahtar sözcüğü, bazı otomatik tür dönüştürme türlerini bastırır.

Dördüncü Oluşturucu priority_queue *Right*'nin bir kopyasını belirtir.

Son üç Oluşturucu, bazı \[kapsayıcının *ilk*, *son*) aralığını kopyalar ve sınıfının `Traits` karşılaştırma işlevinin türünü belirtirken açıkça artarak bir priority_queue başlatmak için değerleri kullanır ve `container_type`.

### <a name="example"></a>Örnek

```cpp
// pqueue_ctor.cpp
// compile with: /EHsc
#include <queue>
#include <vector>
#include <deque>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function declares priority_queue
   // with a default vector base container
   priority_queue <int> q1;
   cout << "q1 = ( ";
   while ( !q1.empty( ) )
   {
      cout << q1.top( ) << " ";
      q1.pop( );
   }
   cout << ")" << endl;

   // Explicitly declares a priority_queue with nondefault
   // deque base container
   priority_queue <int, deque <int> > q2;
   q2.push( 5 );
   q2.push( 15 );
   q2.push( 10 );
   cout << "q2 = ( ";
   while ( !q2.empty( ) )
   {
      cout << q2.top( ) << " ";
      q2.pop( );
   }
   cout << ")" << endl;

   // This method of printing out the elements of a priority_queue
   // removes the elements from the priority queue, leaving it empty
   cout << "After printing, q2 has " << q2.size( ) << " elements." << endl;

   // The third member function declares a priority_queue
   // with a vector base container and specifies that the comparison
   // function greater is to be used for ordering elements
   priority_queue <int, vector<int>, greater<int> > q3;
   q3.push( 2 );
   q3.push( 1 );
   q3.push( 3 );
   cout << "q3 = ( ";
   while ( !q3.empty( ) )
   {
      cout << q3.top( ) << " ";
      q3.pop( );
   }
   cout << ")" << endl;

   // The fourth member function declares a priority_queue and
   // initializes it with elements copied from another container:
   // first, inserting elements into q1, then copying q1 elements into q4
   q1.push( 100 );
   q1.push( 200 );
   priority_queue <int> q4( q1 );
   cout << "q4 = ( ";
   while ( !q4.empty( ) )
   {
      cout << q4.top( ) << " ";
      q4.pop( );
   }
   cout << ")" << endl;

   // Creates an auxiliary vector object v5 to be used to initialize q5
   vector <int> v5;
   vector <int>::iterator v5_Iter;
   v5.push_back( 10 );
   v5.push_back( 30 );
   v5.push_back( 20 );
   cout << "v5 = ( " ;
   for ( v5_Iter = v5.begin( ) ; v5_Iter != v5.end( ) ; v5_Iter++ )
      cout << *v5_Iter << " ";
   cout << ")" << endl;

   // The fifth member function declares and
   // initializes a priority_queue q5 by copying the
   // range v5[ first,  last) from vector v5
   priority_queue <int> q5( v5.begin( ), v5.begin( ) + 2 );
   cout << "q5 = ( ";
   while ( !q5.empty( ) )
   {
      cout << q5.top( ) << " ";
      q5.pop( );
   }
   cout << ")" << endl;

   // The sixth member function declares a priority_queue q6
   // with a comparison function greater and initializes q6
   // by copying the range v5[ first,  last) from vector v5
   priority_queue <int, vector<int>, greater<int> >
      q6( v5.begin( ), v5.begin( ) + 2 );
   cout << "q6 = ( ";
   while ( !q6.empty( ) )
   {
      cout << q6.top( ) << " ";
      q6.pop( );
   }
   cout << ")" << endl;
}
```

## <a name="push"></a>priority_queue::p USH

< İşleçten öğe önceliğine göre öncelik sırasına bir öğe ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Priority_queue üst öğesine eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Priority_queue üst öğesi, kapsayıcıda en büyük öğe tarafından bulunan pozisyondır.

### <a name="example"></a>Örnek

```cpp
// pqueue_push.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   priority_queue<int> q1;

   q1.push( 10 );
   q1.push( 30 );
   q1.push( 20 );

   priority_queue<int>::size_type i;
   i = q1.size( );
   cout << "The priority_queue length is " << i << "." << endl;

   const int& ii = q1.top( );
   cout << "The element at the top of the priority_queue is "
        << ii << "." << endl;
}
```

```Output
The priority_queue length is 3.
The element at the top of the priority_queue is 30.
```

## <a name="size"></a>priority_queue:: size

Priority_queue içindeki öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Priority_queue geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// pqueue_size.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   priority_queue <int> q1, q2;
   priority_queue <int>::size_type i;

   q1.push( 1 );
   i = q1.size( );
   cout << "The priority_queue length is " << i << "." << endl;

   q1.push( 2 );
   i = q1.size( );
   cout << "The priority_queue length is now " << i << "." << endl;
}
```

```Output
The priority_queue length is 1.
The priority_queue length is now 2.
```

## <a name="size_type"></a>priority_queue::size_type

Bir priority_queue içindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, priority_queue tarafından uyarlanmış taban kapsayıcının `size_type` bir eş anlamlısıdır.

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve [](#size) `size_type`kullanılacağına ilişkin bir örnek için boyut örneğine bakın.

## <a name="top"></a>priority_queue:: top

Priority_queue en büyük öğesine bir const başvurusu döndürür.

```cpp
const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

Priority_queue nesnesinin `Traits` işlevi tarafından belirlendiği şekilde en büyük öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulamak için priority_queue boş olmamalıdır.

### <a name="example"></a>Örnek

```cpp
// pqueue_top.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;
   priority_queue<int> q1;

   q1.push( 10 );
   q1.push( 30 );
   q1.push( 20 );

   priority_queue<int>::size_type i;
   i = q1.size( );
   cout << "The priority_queue length is " << i << "." << endl;

   const int& ii = q1.top( );
   cout << "The element at the top of the priority_queue is "
        << ii << "." << endl;
}
```

```Output
The priority_queue length is 3.
The element at the top of the priority_queue is 30.
```

## <a name="value_type"></a>priority_queue::value_type

Bir priority_queue içinde bir öğe olarak depolanan nesne türünü temsil eden bir tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, priority_queue tarafından uyarlanmış taban kapsayıcının `value_type` bir eş anlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// pqueue_value_type.cpp
// compile with: /EHsc
#include <queue>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares priority_queues with default deque base container
   priority_queue<int>::value_type AnInt;

   AnInt = 69;
   cout << "The value_type is AnInt = " << AnInt << endl;

   priority_queue<int> q1;
   q1.push( AnInt );
   cout << "The element at the top of the priority_queue is "
        << q1.top( ) << "." << endl;
}
```

```Output
The value_type is AnInt = 69
The element at the top of the priority_queue is 69.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
