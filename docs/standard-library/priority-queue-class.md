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
ms.openlocfilehash: cef85eafaa3aab1c448234399f146191de957b8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323001"
---
# <a name="priority_queue-class"></a>priority_queue Sınıfı

Her zaman en büyük veya en yüksek önceliğe sahip olan bazı temel kapsayıcı türündeki en üst öğeye erişimi sınırlayan işlevsellik kısıtlaması sağlayan şablon kapsayıcı bağdaştırıcı sınıfı. priority_queue yeni öğeler eklenebilir ve priority_queue üst öğesi incelenebilir veya kaldırılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>
class priority_queue
```

### <a name="parameters"></a>Parametreler

*Türü*\
priority_queue depolanacak öğe veri türü.

*Kapsayıcı*\
priority_queue uygulamak için kullanılan temel kapsayıcının türü.

*Karşılaştırmak*\
priority_queue göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır `less<typename Container::value_type>` ve ikili yüklem varsayılan değerdir.

## <a name="remarks"></a>Açıklamalar

Bir sıra `Type` nesnesinin ilk şablon parametresinde öngörülen sınıf öğeleri [value_type](#value_type) eş anlamlıdır ve ikinci şablon `Container` parametresi tarafından öngörülen temel kapsayıcı sınıfındaki öğe türüyle eşleşmelidir. Bu `Type` tür nesneleri kopyalamak ve bu tür değişkenlere değerler atamak mümkün böylece atanabilir olmalıdır.

priority_queue, sınıfın `Traits`depolanan işlev nesnesini çağırarak denetlenen sırayı sıralar. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur.

priority_queue için uygun temel kapsayıcı sınıfları [deque Sınıf](../standard-library/deque-class.md) ve varsayılan [vektör](../standard-library/vector-class.md) Sınıf `front` `push_back`veya `pop_back` işlemleri destekleyen başka bir sıra kapsayıcı içerir , ve rasgele erişim yineleyici. Altta yatan kapsayıcı sınıfı, ortak arabirim olarak yalnızca sınırlı sayıda sıra kapsayıcı üye işlevini ortaya çıkaran kapsayıcı bağdaştırıcısının içinde kapsüllenir.

Öğelerin eklenmesi ve her `priority_queue` ikisinden öğeleri kaldırmalogaritmik karmaşıklığa sahiptir. Öğelere erişim `priority_queue` in sabit bir karmaşıklığı vardır.

C++ Standart Kitaplığı tarafından tanımlanan üç tür kapsayıcı bağdaştırıcısı vardır: yığın, sıra ve priority_queue. Her standart bir veri yapısı için tam olarak denetlenen bir arabirim sağlamak için bazı temel kapsayıcı sınıfının işlevselliğini kısıtlar.

- [Yığın Sınıfı,](../standard-library/stack-class.md) son,ilk çıkan (LIFO) veri yapısını destekler. Akılda tutulması gereken iyi bir analog tabak yığını olacaktır. Öğeler (plakalar) yalnızca temel kapsayıcının sonundaki son öğe olan yığının üst kısmından eklenebilir, denetlenebilir veya kaldırılabilir. Yalnızca üst öğeye erişim kısıtlaması yığın sınıfını kullanma nedenidir.

- [Sıra Sınıfı,](../standard-library/queue-class.md) ilk gelen, ilk çıkan (FIFO) veri yapısını destekler. Akılda tutulması gereken iyi bir analog insanlar bir banka vezneiçin sıraya olacaktır. Öğeler (kişiler) satırın arkasına eklenebilir ve satırın önünden kaldırılır. Bir hattın hem ön hem de arka cephesi denetlenebilir. Bu şekilde yalnızca ön ve arka öğelere erişme kısıtlaması, sıra sınıfını kullanma nedenidir.

- priority_queue sınıf, en büyük öğenin her zaman en üst konumda olması için öğelerini emreder. Bir öğenin eklenmesini ve üst öğenin incelenmesini ve kaldırılmasını destekler. Akılda tutulması gereken iyi bir analog insanlar nerede yaş, boy, ya da başka bir kriter tarafından düzenlenir sıraya olacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Priority_queue](#priority_queue)|Boş olan `priority_queue` veya bir temel kapsayıcı nesnesinin veya diğer `priority_queue`bir aralığın kopyası olan bir yapıyı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Baz kapsayıcının bir . tarafından uyarlanmasını sağlayan bir `priority_queue`tür|
|[size_type](#size_type)|Bir 'deki öğe sayısını temsil eden imzasız `priority_queue`bir tamsayı türü|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil `priority_queue`eden bir tür .|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[empty](#empty)|Boş olup `priority_queue` olmadığını test edin.|
|[Pop](#pop)|En büyük öğeyi `priority_queue` üst konumdan kaldırır.|
|[Itme](#push)|İşleç< öğenin önceliğine göre öncelik sırasına bir öğe ekler.|
|[Boyutu](#size)|`priority_queue`'deki öğe sayısını verir.|
|[Sayfanın Üstü](#top)|`priority_queue`En üstteki en büyük öğeye const başvurusu verir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<sıra>

**Ad alanı:** std

## <a name="priority_queuecontainer_type"></a><a name="container_type"></a>priority_queue:container_type

Temel kapsayıcının uyarlanmasını sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Container`ile eş anlamlıdır. C++ Standart Kitaplık `deque` sıralı kapsayıcı `vector` sınıfı ve varsayılan sınıf, priority_queue bir nesne için temel kapsayıcı olarak kullanılacak gereksinimleri karşılar. Gereksinimleri karşılayan kullanıcı tanımlı türleri de kullanılabilir.

Daha fazla `Container`bilgi için [priority_queue Sınıfı](../standard-library/priority-queue-class.md) konusunun Açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Nasıl beyan priority_queue ve nasıl kullanılacağına `container_type`bir örnek için örneğe bakın. [priority_queue](#priority_queue)

## <a name="priority_queueempty"></a><a name="empty"></a>priority_queue::boş

priority_queue boşolup priority_queue.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

priority_queue boşsa **doğrudur;** priority_queue boş değilse **yanlış.**

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

## <a name="priority_queuepop"></a><a name="pop"></a>priority_queue::pop

priority_queue en büyük öğesini üst konumdan kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi uygulamak için priority_queue boş olmaması gerekir. priority_queue üst her zaman kapsayıcıda en büyük öğe tarafından işgal edilir.

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

## <a name="priority_queuepriority_queue"></a><a name="priority_queue"></a>priority_queue::priority_queue

Boş veya bir temel kapsayıcı nesnesinin veya başka bir priority_queue aralığının kopyası olan bir priority_queue sağlar.

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

*_comp*\
Priority_queue öğeleri ni sipariş etmek için kullanılan tür **constTraits** karşılaştırma işlevi, hangi temel kapsayıcının işlevini karşılaştırmak için varsayılan.

*_Cont*\
Yapılandırılan priority_queue temel kapsayıcı bir kopyası olmaktır.

*Doğru*\
Yapılandırılan kümenin priority_queue bir kopyası olmaktır.

*Ilk*\
Kopyalanacak öğeler aralığındaki ilk öğenin konumu.

*Son*\
İlk öğenin kopyalanacak öğe aralığının ötesindeki konumu.

### <a name="remarks"></a>Açıklamalar

İlk üç oluşturucunun her biri boş bir başlangıç priority_queue belirtir, ikincisi de`comp`elementlerin sırasını oluştururken kullanılacak karşılaştırma işlevinin türünü belirtir, üçüncüsü ise kullanılacak `container_type` ( )`_Cont`belirtilir. Anahtar kelime **açık** otomatik tür dönüştürme belirli türleri bastırır.

Dördüncü oluşturucu priority_queue *sağ*bir kopyasını belirtir.

Son üç oluşturucu, bazı \[kapsayıcının *aralığını ,* *son*) kopyalar ve sınıfın `Traits` karşılaştırma işlevinin türünü belirtirken artan `container_type`açıklıkla priority_queue başlatılması için değerleri kullanır ve .

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

## <a name="priority_queuepush"></a><a name="push"></a>priority_queue::push

İşleç< öğenin önceliğine göre öncelik sırasına bir öğe ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Öğe nin üstüne eklenen priority_queue.

### <a name="remarks"></a>Açıklamalar

priority_queue üst kapsayıcıdaki en büyük öğe tarafından işgal edilen konumdur.

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

## <a name="priority_queuesize"></a><a name="size"></a>priority_queue::boyut

priority_queue'daki öğe sayısını verir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

priority_queue geçerli uzunluğu.

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

## <a name="priority_queuesize_type"></a><a name="size_type"></a>priority_queue:size_type

priority_queue'daki öğe sayısını temsil eden imzasız bir tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, priority_queue tarafından uyarlanan `size_type` temel kapsayıcının eşanlamlısiyidir.

### <a name="example"></a>Örnek

Nasıl bildirilir [size](#size) ve kullanılacağına `size_type`bir örnek için boyut örneği bakın.

## <a name="priority_queuetop"></a><a name="top"></a>priority_queue::üst

priority_queue üst kısmındaki en büyük öğeye const başvurusu verir.

```cpp
const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

Priority_queue `Traits` işlevi tarafından belirlenen en büyük öğeye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi uygulamak için priority_queue boş olmaması gerekir.

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

## <a name="priority_queuevalue_type"></a><a name="value_type"></a>priority_queue::value_type

Bir priority_queue öğe olarak depolanan nesne türünü temsil eden bir tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, priority_queue tarafından uyarlanan `value_type` temel kapsayıcının eşanlamlısiyidir.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
