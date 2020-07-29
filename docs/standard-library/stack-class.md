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
ms.openlocfilehash: 8c1da5d45acd68838174d02305a246ba2d2c169b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224636"
---
# <a name="stack-class"></a>stack Sınıfı

Bazı temel kapsayıcı türlerine en son eklenen öğeye erişimi sınırlayan bir işlev kısıtlaması sağlayan şablon kapsayıcı bağdaştırıcı sınıfı. Yığın sınıfı, kapsayıcıda yalnızca yığın işlemlerinin gerçekleştirildiğinden emin olmak önemliyse kullanılır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type, class Container= deque <Type>>
class stack
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Yığında depolanacak öğe veri türü.

*Kapsayıcı*\
Yığını uygulamak için kullanılan temeldeki kapsayıcının türü. Varsayılan değer sınıfındır `deque` *\<Type>* .

## <a name="remarks"></a>Açıklamalar

`Type`Bir Stack nesnesinin ilk şablon parametresinde stıpulan sınıfının öğeleri [value_type](#value_type) ile eşanlamlıdır ve `Container` ikinci şablon parametresi tarafından belirlenen temeldeki kapsayıcı sınıfında öğe türüyle eşleşmelidir. , `Type` Bu türdeki nesneleri kopyalamak ve bu türdeki değişkenlere değer atamak mümkün olduğundan, atanabilir olmalıdır.

Yığın için uygun temel kapsayıcı sınıfları, [deque](../standard-library/deque-class.md), [list Class](../standard-library/list-class.md)ve [Vector sınıfı](../standard-library/vector-class.md)ya da, ve işlemlerini destekleyen herhangi bir sıra kapsayıcısını içerir `back` `push_back` `pop_back` . Temel alınan kapsayıcı sınıfı kapsayıcı bağdaştırıcısında kapsüllenir, bu da yalnızca ortak arabirim olarak dizi kapsayıcısı üye işlevlerinin sınırlı kümesini sunar.

Yığın nesneleri eşitlik karşılaştırılabilir ve yalnızca sınıf öğeleri `Type` eşitlik karşılaştırılabilir ise ve yalnızca sınıf öğeleri karşılaştırılabilir değilse küçüktür ve karşılaştırılabilir `Type` .

- Stack sınıfı, son bir ilk çıkar (LıFO) veri yapısını destekler. Göz önünde bulundurmanız gereken bir şey, bir levha yığını olacaktır. Öğeler (levhalar), temel kapsayıcının sonundaki son öğe olan yığının en üstünden eklenebilir, incelenebilir veya kaldırılabilir. Yalnızca Top öğesine erişme kısıtlaması, Stack sınıfının kullanılmasına neden olur.

- [Queue sınıfı](../standard-library/queue-class.md) , ilk kez ilk çıkar (FIFO) veri yapısını destekler. İnsanların bir banka teller için yukarı doğru tutulması yararlı olacaktır. Öğeler (kişiler) satırın arkasına eklenebilir ve satırın önüne kaldırılır. Bir çizginin ön ve arka ucu incelenebilir. Yalnızca ön ve geri öğelerine bu şekilde erişme kısıtlaması, kuyruk sınıfını kullanan bir nedenidir.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) öğelerini en büyük öğenin her zaman en üstteki konumda olacak şekilde sıralar. Bir öğenin eklenmesini ve en üstteki öğenin incelemesini ve kaldırılmasını destekler. İnsanların yaş, yükseklik veya diğer ölçütlere göre düzenlendikleri yere göz önünde bulundurmanız gereken iyi bir yoldur.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[yığın](#stack)|`stack`Boş veya temel kapsayıcı nesnesinin bir kopyası olan oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[container_type](#container_type)|Tarafından uyarlanabilen temel kapsayıcıyı sağlayan bir tür `stack` .|
|[size_type](#size_type)|İçindeki öğe sayısını temsil eden işaretsiz bir tamsayı türü `stack` .|
|[value_type](#value_type)|İçindeki bir öğe olarak depolanan nesne türünü temsil eden bir tür `stack` .|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[empty](#empty)|`stack`Boşsa sınar.|
|[cağımız](#pop)|Öğesini öğesinin üst öğesinden kaldırır `stack` .|
|[push](#push)|Öğesinin üstüne bir öğesi ekler `stack` .|
|[boyutla](#size)|İçindeki öğelerin sayısını döndürür `stack` .|
|[top](#top)|Öğesinin en üstündeki öğesine bir başvuru döndürür `stack` .|

## <a name="container_type"></a><a name="container_type"></a>container_type

Uyarlanabilen temel kapsayıcıyı sağlayan bir tür.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Container` . Tüm üç C++ standart kitaplık sırası kapsayıcı sınıfları — vektör sınıfı, liste sınıfı ve varsayılan Sınıf deque — bir yığın nesnesi için temel kapsayıcı olarak kullanılacak gereksinimleri karşılar. Bu gereksinimleri karşılayan Kullanıcı tanımlı türler de kullanılabilir.

Hakkında daha fazla bilgi için `Container` [Stack Class](../standard-library/stack-class.md) konusunun açıklamalar bölümüne bakın.

### <a name="example"></a>Örnek

Bildirme ve kullanma hakkında bir örnek için [Stack:: Stack](#stack) örneğine bakın `container_type` .

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Bir yığının boş olup olmadığını sınar.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** yığın boşsa; **`false`** yığın boş değilse.

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

## <a name="pop"></a><a name="pop"></a>cağımız

Öğeyi yığının en üstünden kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulamak için yığının boş olması gerekir. Yığının en üst öğesi, en son eklenen öğe tarafından bulunan ve kapsayıcının sonundaki son öğe olan konumudur.

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

## <a name="push"></a><a name="push"></a>hareketle

Yığının en üstüne bir öğe ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Yığın üst kısmına eklenen öğe.

### <a name="remarks"></a>Açıklamalar

Yığının en üst öğesi, en son eklenen öğe tarafından bulunan ve kapsayıcının sonundaki son öğe olan konumudur.

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

## <a name="size"></a><a name="size"></a>boyutla

Yığındaki öğe sayısını döndürür.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığının geçerli uzunluğu.

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

## <a name="size_type"></a><a name="size_type"></a>size_type

Bir yığındaki öğelerin sayısını temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `size_type` yığın tarafından uyarlanan taban kapsayıcının eşanlamlısıdır.

### <a name="example"></a>Örnek

Nasıl bildirilemeyeceğini ve kullanılacağına ilişkin bir örnek için [Boyut](#size) örneğine bakın `size_type` .

## <a name="stack"></a><a name="stack"></a>yığın

Boş olan veya temel kapsayıcı sınıfının kopyası olan bir yığın oluşturur.

```cpp
stack();

explicit stack(const container_type& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Oluşturulan yığının bir kopya olduğu kapsayıcı.

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

## <a name="top"></a><a name="top"></a>Sayfanın Üstü

Yığının en üstünde bir öğeye bir başvuru döndürür.

```cpp
reference top();

const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yığının en üstündeki kapsayıcıda bulunan son öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulamak için yığının boş olması gerekir. Yığının en üst öğesi, en son eklenen öğe tarafından bulunan ve kapsayıcının sonundaki son öğe olan konumudur.

Dönüş değeri `top` öğesine atanırsa `const_reference` , yığın nesnesi değiştirilemez. Dönüş değeri `top` öğesine atanırsa `reference` , yığın nesnesi değiştirilebilir.

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

## <a name="value_type"></a><a name="value_type"></a>value_type

Bir yığında bir öğe olarak depolanan nesne türünü temsil eden bir tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `value_type` yığın tarafından uyarlanan taban kapsayıcının eşanlamlısıdır.

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
