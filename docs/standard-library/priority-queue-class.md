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
ms.openlocfilehash: d8f2b4ab788c82e531d1121f04dd0d422efb17cd
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51333221"
---
# <a name="priorityqueue-class"></a>priority_queue Sınıfı

Bir kısıtlama üst öğe her zaman en büyük olduğu bazı temel alınan bir kapsayıcı türü veya en yüksek öncelikli erişimi sınırlandırma işlevsellik sağlayan şablon kapsayıcı bağdaştırıcısı sınıf. Yeni öğeler için priority_queue eklenebilir ve priority_queue üst öğesinin inceledi veya kaldırıldı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container= vector <Type>, class Compare= less <typename Container ::value_type>>
class priority_queue
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Priority_queue içinde depolanacak öğe veri türü.

*Kapsayıcı*<br/>
Priority_queue uygulamak için kullanılan temel alınan kapsayıcı türü.

*Compare*<br/>
İki öğenin değerlerini priority_queue kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<typename Container::value_type>` varsayılan değerdir.

## <a name="remarks"></a>Açıklamalar

Sınıfına ait öğelerin `Type` ilk şablon, belirlenen bir sıra nesnesi parametresinin işlevlerindeki [value_type](#value_type) ve temel alınan kapsayıcı sınıfı bir öğenin türüyle eşleşmelidir `Container` tarafından görünürlüğe İkinci şablon parametresi. `Type` Türündeki nesnelerin kopyalayın ve bu türün değişkenlerine değer atamak için mümkün olması atanabilir, olmalıdır.

Priority_queue sınıfı bir depolanmış bir işlev nesnesi çağırarak denetlediği diziyi sıralar `Traits`. Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur.

Priority_queue için uygun alt kapsayıcı sınıflarını içerir [deque sınıfı](../standard-library/deque-class.md) ve varsayılan [vector sınıfı](../standard-library/vector-class.md) veya işlemlerini destekleyen herhangi bir dizisi kapsayıcısına `front`, `push_back`, ve `pop_back` ve bir rasgele erişim yineleyicisi. Temel alınan kapsayıcı sınıfı, ortak bir arabirim olarak sıralı kapsayıcı üye işlevleri sınırlı sayıda yalnızca sunan kapsayıcı bağdaştırıcısı içinde kapsüllenir.

Öğeleri eklemek ve öğeleri kaldırma bir `priority_queue` Logaritmik karmaşıklığı her ikisi de sahiptir. Öğeleri erişen bir `priority_queue` sabit karmaşası vardır.

Kapsayıcı bağdaştırıcıları C++ Standart Kitaplığı tarafından tanımlanan üç tür vardır: priority_queue yığın ve kuyruk. Her bir standart veri yapısı için kesin bir şekilde denetlenen bir arabirim sağlamak üzere temel alınan bazı kapsayıcı sınıfı işlevselliğini kısıtlar.

- [Stack sınıfı](../standard-library/stack-class.md) son giren ilk çıkar (LIFO) veri yapısı destekler. Akılda tutulması için iyi bir analog kalıplarını yığınını olacaktır. Öğeleri (kalıplarını) eklendiğinde, inceledi veya yalnızca en son öğe temel kapsayıcı sonunda yığın kaldırılır. Yalnızca üst öğesi erişme kısıtlamasını stack sınıfı kullanarak nedenidir.

- [Sınıfı sıra](../standard-library/queue-class.md) bir ilk giren ilk çıkar (FIFO) veri yapısını destekler. Akılda tutulması için iyi bir analog bir banka gişe için hizalama kişi olacaktır. Öğeleri (kişi), satırın geri eklenebilir ve satır önünden kaldırılır. Hem ön hem de bir satırın geri inceledi. Bu şekilde yalnızca ön ve arka öğelere erişme kısıtlamasını queue sınıfı kullanarak nedenidir.

- Priority_queue sınıfı, en büyük öğe her zaman üst konumda olmasını sağlayın, öğeleri sıralar. Bu, bir öğe ve inceleme, ekleme ve kaldırma üst öğenin destekler. Burada, yaş, yüksekliğe veya diğer bir ölçüte göre düzenlenmiş yukarı hizalama kişiler akılda tutulması için iyi bir analog olacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[priority_queue](#priority_queue)|Oluşturur bir `priority_queue` boş veya diğer bir deyişle bir aralığı temel kapsayıcı nesnesinin veya diğer kopyası olan `priority_queue`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Temel olarak uyarlanabilen kapsayıcıya sağlayan bir tür bir `priority_queue`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `priority_queue`.|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil eden bir tür bir `priority_queue`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[boş](#empty)|Olmadığını test eder `priority_queue` boştur.|
|[POP](#pop)|En büyük öğenin kaldırır `priority_queue` üst konum.|
|[push](#push)|Bir öğeyi işleci öğesinden önceliğini göre öncelik sırasına ekler <.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `priority_queue`.|
|[Sayfanın Üstü](#top)|Döndürür bir const başvuru en üstündeki en büyük öğeyi `priority_queue`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<kuyruk >

**Namespace:** std

## <a name="container_type"></a>  priority_queue::container_type

Temel uyarlanabilen kapsayıcıya sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Container`. C++ Standart Kitaplığı dizisi kapsayıcı sınıfı `deque` ve varsayılan sınıf `vector` gereksinimlerini priority_queue nesnesi için temel bir kapsayıcı olarak kullanılacak. Kullanıcı tanımlı türler gereksinimlerini karşılamadığınızı de kullanılabilir.

Daha fazla bilgi için `Container`, Açıklamalar bölümüne bakın [priority_queue sınıfı](../standard-library/priority-queue-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [priority_queue](#priority_queue) bildirme ve kullanma konusunda bir örnek için `container_type`.

## <a name="empty"></a>  priority_queue::empty

Bir priority_queue boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** priority_queue boşsa; **false** priority_queue boş ise.

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

## <a name="pop"></a>  priority_queue::POP

Priority_queue, en büyük öğe üst konumu kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Priority_queue üyesi işlevi uygulamak için boş olmamalıdır. Priority_queue üst her zaman kapsayıcısında en büyük öğe tarafından kullanılıyor.

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

## <a name="priority_queue"></a>  priority_queue::priority_queue

Boş veya bir aralığı temel kapsayıcı nesnesinin veya başka bir priority_queue kopyası olan bir priority_queue oluşturur.

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

*_comp*<br/>
Karşılaştırma işlevi türü **constTraits** işlevi temel kapsayıcının karşılaştırmak için varsayılan olarak priority_queue içinde öğeleri sıralamak için kullanılan.

*_Cont*<br/>
Oluşturulan priority_queue kopyası olacak olduğu temel kapsayıcı.

*sağ*<br/>
Priority_queue oluşturulmuş kümesi kopyası olacak olduğu.

*ilk*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*Son*<br/>
Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Her ilk üç oluşturucular ikinci de karşılaştırma işlevinin türü belirten bir boş bir başlangıç priority_queue belirtir (`comp`) öğeleri ve üçüncüsü sırasını açıkça oluşturmada kullanılacak belirtme`container_type`(`_Cont`) kullanılacak. Anahtar sözcüğü **açık** otomatik tür dönüştürme belirli türdeki bastırır.

Dördüncü Oluşturucu priority_queue bir kopyasını belirtir *doğru*.

Son üç oluşturucular aralığını kopyalamaktadır \[ *ilk*, *son*) bazı kapsayıcısının ve türünü belirtilirken explicitness artan bir priority_queue başlatmak için değerleri kullanın sınıfı, karşılaştırma işlevi `Traits` ve `container_type`.

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

## <a name="push"></a>  priority_queue::push

Bir öğeyi işleci öğesinden önceliğini göre öncelik sırasına ekler <.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Priority_queue üstüne eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Priority_queue üstüne kapsayıcısında en büyük öğe tarafından kaplanan konumdur.

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

## <a name="size"></a>  priority_queue::size

Priority_queue öğelerin sayısını döndürür.

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

## <a name="size_type"></a>  priority_queue::size_type

Bir priority_queue içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `size_type` priority_queue göre uyarlanmış temel kapsayıcının.

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="top"></a>  priority_queue::Top

Priority_queue en büyük öğe için sabit bir başvuru döndürür.

```cpp
const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

En büyük öğe tarafından belirlendiği şekilde, bir başvuru `Traits` işlevi, priority_queue nesne.

### <a name="remarks"></a>Açıklamalar

Priority_queue üyesi işlevi uygulamak için boş olmamalıdır.

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

## <a name="value_type"></a>  priority_queue::value_type

Bir öğe bir priority_queue olarak depolanan nesne türünü temsil eden tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `value_type` priority_queue göre uyarlanmış temel kapsayıcının.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
