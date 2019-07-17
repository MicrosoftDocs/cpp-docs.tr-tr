---
title: stack Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stack/std::stack::container_type
- stack/std::stack::size_type
- stack/std::stack::value_type
- stack/std::stack::empty
- stack/std::stack::pop
- stack/std::stack::push
- stack/std::stack::size
- stack/std::stack::top
helpviewer_keywords:
- std::stack [C++], container_type
- std::stack [C++], size_type
- std::stack [C++], value_type
- std::stack [C++], empty
- std::stack [C++], pop
- std::stack [C++], push
- std::stack [C++], size
- std::stack [C++], top
ms.assetid: 02151c1e-eab0-41b8-be94-a839ead78ecf
ms.openlocfilehash: 36074f75830f92ba3fb9e5edb4e1507aa5ae1407
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241058"
---
# <a name="stack-class"></a>stack Sınıfı

Bir kısıtlama bazı temel alınan bir kapsayıcı türü için en son eklenen öğeye erişimi sınırlandırma işlevsellik sağlayan şablon kapsayıcı bağdaştırıcı sınıfı. Stack sınıfı yalnızca yığın işlemleri kapsayıcı üzerinde gerçekleştirilen açık olması önemli olduğunda kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container= deque <Type>>
class stack
```

### <a name="parameters"></a>Parametreler

*Türü*\
Yığın içinde depolanacak öğe veri türü.

*Kapsayıcı*\
Yığın uygulamak için kullanılan temel alınan kapsayıcı türü. Varsayılan değer sınıfı, `deque`  *\<türü >* .

## <a name="remarks"></a>Açıklamalar

Sınıfına ait öğelerin `Type` ilk şablon, belirlenen bir yığın nesnesinin parametresi işlevlerindeki [value_type](#value_type) ve temel alınan kapsayıcı sınıfı bir öğenin türüyle eşleşmelidir `Container` tarafından görünürlüğe İkinci şablon parametresi. `Type` Türündeki nesnelerin kopyalayın ve bu türün değişkenlerine değer atamak için mümkün olması atanabilir, olmalıdır.

Yığın için uygun alt kapsayıcı sınıflarını içerir [deque](../standard-library/deque-class.md), [listesinde sınıfı](../standard-library/list-class.md), ve [vector sınıfı](../standard-library/vector-class.md), ya da işlemleri destekleyen herhangi bir dizisi kapsayıcısına `back`, `push_back`, ve `pop_back`. Temel alınan kapsayıcı sınıfı, ortak bir arabirim olarak sıralı kapsayıcı üye işlevleri sınırlı sayıda yalnızca sunan kapsayıcı bağdaştırıcısı içinde kapsüllenir.

Yığın nesneleri: eşitlik için karşılaştırılabilir ise ve yalnızca sınıfın öğelerine `Type` eşitlik benzerdir ve küçük-karşılaştırılabilir ve yalnızca daha sınıfına ait öğelerin `Type` küçüktür-daha karşılaştırılabilir.

- Stack sınıfı, bir son giren ilk çıkar (LIFO) veri yapısını destekler. Akılda tutulması için iyi bir analog kalıplarını yığınını olacaktır. Öğeleri (kalıplarını) eklendiğinde, inceledi veya yalnızca en son öğe temel kapsayıcı sonunda yığın kaldırılır. Yalnızca üst öğesi erişme kısıtlamasını stack sınıfı kullanarak nedenidir.

- [Kuyruk sınıfı](../standard-library/queue-class.md) bir ilk giren ilk çıkar (FIFO) veri yapısını destekler. Akılda tutulması için iyi bir analog bir banka gişe için hizalama kişi olacaktır. Öğeleri (kişi), satırın geri eklenebilir ve satır önünden kaldırılır. Hem ön hem de bir satırın geri inceledi. Bu şekilde yalnızca ön ve arka öğelere erişme kısıtlamasını queue sınıfı kullanarak nedeni kürk ' dir.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) en büyük öğe her zaman üst konumunda olması, öğeleri sıralar. Bu, bir öğe ve inceleme, ekleme ve kaldırma üst öğenin destekler. Burada, yaş, yüksekliğe veya diğer bir ölçüte göre düzenlenmiş yukarı hizalama kişiler akılda tutulması için iyi bir analog olacaktır.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[Yığın](#stack)|Oluşturur bir `stack` boş veya bir temel kapsayıcı nesnesinin bir kopyasını başka bir deyişle olduğu.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[container_type](#container_type)|Temel olarak uyarlanabilen kapsayıcıya sağlayan bir tür bir `stack`.|
|[size_type](#size_type)|İçindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü bir `stack`.|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil eden bir tür bir `stack`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[boş](#empty)|Olmadığını test eder `stack` boştur.|
|[POP](#pop)|Öğe üst kısmından kaldırır `stack`.|
|[push](#push)|Bir öğe üstüne ekler `stack`.|
|[Boyutu](#size)|İçindeki öğelerin sayısını döndürür `stack`.|
|[Sayfanın Üstü](#top)|Üst kısmında bir öğeye bir başvuru döndürür `stack`.|

## <a name="container_type"></a> container_type

Temel uyarlanabilen kapsayıcıya sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Container`. Üç tüm C++ Standart Kitaplığı dizisi kapsayıcı sınıfları — vector sınıfı, liste sınıfı ve varsayılan sınıf deque — gereksinimlerini bir yığın nesnesi için temel bir kapsayıcı olarak kullanılacak. Bu gereksinimlerin karşılanması kullanıcı tanımlı türler de kullanılabilir.

Daha fazla bilgi için `Container`, Açıklamalar bölümüne bakın [stack sınıfı](../standard-library/stack-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bakın [stack::stack](#stack) bildirme ve kullanma konusunda bir örnek için `container_type`.

## <a name="empty"></a> boş

Bir yığını boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığın boşsa; **false** yığını boş ise.

### <a name="example"></a>Örnek

```cpp
// stack_empty.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   // Declares stacks with default deque base container
   stack <int> s1, s2;

   s1.push( 1 );

   if ( s1.empty( ) )
      cout << "The stack s1 is empty." << endl;
   else
      cout << "The stack s1 is not empty." << endl;

   if ( s2.empty( ) )
      cout << "The stack s2 is empty." << endl;
   else
      cout << "The stack s2 is not empty." << endl;
}
```

```Output
The stack s1 is not empty.
The stack s2 is empty.
```

## <a name="pop"></a> POP

Öğeyi yığın üst kısmından kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Yığın, üye işlevi uygulamak için boş olmamalıdır. Yığının üstü en son eklenen öğe tarafından kullanılan konumu ve son öğe kapsayıcı sonunda.

### <a name="example"></a>Örnek

```cpp
// stack_pop.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1, s2;

   s1.push( 10 );
   s1.push( 20 );
   s1.push( 30 );

   stack <int>::size_type i;
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   i = s1.top( );
   cout << "The element at the top of the stack is "
        << i << "." << endl;

   s1.pop( );

   i = s1.size( );
   cout << "After a pop, the stack length is "
        << i << "." << endl;

   i = s1.top( );
   cout << "After a pop, the element at the top of the stack is "
        << i << "." << endl;
}
```

```Output
The stack length is 3.
The element at the top of the stack is 30.
After a pop, the stack length is 2.
After a pop, the element at the top of the stack is 20.
```

## <a name="push"></a> anında iletme

Bir öğeyi yığın üstüne ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL*\
Yığın üstüne eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Yığının üstü en son eklenen öğe tarafından kullanılan konumu ve son öğe kapsayıcı sonunda.

### <a name="example"></a>Örnek

```cpp
// stack_push.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1;

   s1.push( 10 );
   s1.push( 20 );
   s1.push( 30 );

   stack <int>::size_type i;
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   i = s1.top( );
   cout << "The element at the top of the stack is "
        << i << "." << endl;
}
```

```Output
The stack length is 3.
The element at the top of the stack is 30.
```

## <a name="size"></a> Boyutu

Yığın içinde öğelerin sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığın geçerli uzunluğu.

### <a name="example"></a>Örnek

```cpp
// stack_size.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1, s2;
   stack <int>::size_type i;

   s1.push( 1 );
   i = s1.size( );
   cout << "The stack length is " << i << "." << endl;

   s1.push( 2 );
   i = s1.size( );
   cout << "The stack length is now " << i << "." << endl;
}
```

```Output
The stack length is 1.
The stack length is now 2.
```

## <a name="size_type"></a> size_type

Bir yığın içindeki öğelerin sayısını temsil edebilen bir işaretsiz tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `size_type` yığını tarafından uyarlanmış temel kapsayıcının.

### <a name="example"></a>Örnek

Örneğin bakın [boyutu](#size) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="stack"></a> Yığın

Bir yığını boş olan veya bir temel kapsayıcı sınıfı bir kopyasını oluşturur.

```cpp
stack();

explicit stack(const container_type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Oluşturulan yığın kopyası olacak olduğu kapsayıcı.

### <a name="example"></a>Örnek

```cpp
// stack_stack.cpp
// compile with: /EHsc
#include <stack>
#include <vector>
#include <list>
#include <iostream>

int main( )
{
   using namespace std;

   // Declares stack with default deque base container
   stack <char> dsc1;

   //Explicitly declares a stack with deque base container
   stack <char, deque<char> > dsc2;

   // Declares a stack with vector base containers
   stack <int, vector<int> > vsi1;

   // Declares a stack with list base container
   stack <int, list<int> > lsi;

   // The second member function copies elements from a container
   vector<int> v1;
   v1.push_back( 1 );
   stack <int, vector<int> > vsi2( v1 );
   cout << "The element at the top of stack vsi2 is "
        << vsi2.top( ) << "." << endl;
}
```

```Output
The element at the top of stack vsi2 is 1.
```

## <a name="top"></a> Sayfanın Üstü

Yığının üst öğeye bir başvuru döndürür.

```cpp
reference top();

const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığının üst kapsayıcı içindeki son öğeden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yığın, üye işlevi uygulamak için boş olmamalıdır. Yığının üstü en son eklenen öğe tarafından kullanılan konumu ve son öğe kapsayıcı sonunda.

Varsa dönüş değerinin `top` atanan bir `const_reference`, yığın nesnesi değiştirilemez. Varsa dönüş değerinin `top` atanan bir `reference`, yığın nesnesi değiştirilebilir.

### <a name="example"></a>Örnek

```cpp
// stack_top.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   stack <int> s1;

   s1.push( 1 );
   s1.push( 2 );

   int& i = s1.top( );
   const int& ii = s1.top( );

   cout << "The top integer of the stack s1 is "
        << i << "." << endl;
   i--;
   cout << "The next integer down is "<< ii << "." << endl;
}
```

```Output
The top integer of the stack s1 is 2.
The next integer down is 1.
```

## <a name="value_type"></a> value_type

Bir yığın içinde bir öğe olarak depolanan nesne türünü temsil eden tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `value_type` yığını tarafından uyarlanmış temel kapsayıcının.

### <a name="example"></a>Örnek

```cpp
// stack_value_type.cpp
// compile with: /EHsc
#include <stack>
#include <iostream>

int main( )
{
   using namespace std;
   // Declares stacks with default deque base container
   stack<int>::value_type AnInt;

   AnInt = 69;
   cout << "The value_type is AnInt = " << AnInt << endl;

   stack<int> s1;
   s1.push( AnInt );
   cout << "The element at the top of the stack is "
        << s1.top( ) << "." << endl;
}
```

```Output
The value_type is AnInt = 69
The element at the top of the stack is 69.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
