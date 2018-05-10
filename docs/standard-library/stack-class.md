---
title: stack sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stack/std::stack::container_type
- stack/std::stack::size_type
- stack/std::stack::value_type
- stack/std::stack::empty
- stack/std::stack::pop
- stack/std::stack::push
- stack/std::stack::size
- stack/std::stack::top
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c162f6092c127277e2af992eda1e47c00c7cb43
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="stack-class"></a>stack Sınıfı

Bazı temel kapsayıcı türü eklenen en son öğesine erişimi sınırlandırma işlevlerin bir kısıtlama sağlayan bir şablon kapsayıcı bağdaştırıcısının sınıfı. Stack sınıfı yalnızca yığın işlemleri kapsayıcısında gerçekleştiriliyor açık bir şekilde anlaşılması önemlidir kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Container= deque <Type>>
class stack
```

### <a name="parameters"></a>Parametreler

*Tür* öğesi veri türü yığında depolanacak.

`Container` Yığın uygulamak için kullanılan temel kapsayıcı türü. Varsayılan değer sınıftır `deque`  *\<türü >*.

## <a name="remarks"></a>Açıklamalar

Sınıfının öğeleri **türü** ilk şablon, belirlenen bir yığın nesnesi parametresi ile eşanlamlı [value_type](#value_type) ve arka plandaki kapsayıcı sınıfı öğetürüeşleşmelidir**Kapsayıcı** ikinci şablon parametresi tarafından belirlenen. **Türü** böylece bu tür nesneleri kopyalayın ve bu tür değişkenlere değerler atayın olası atanabilir, olması gerekir.

Yığın için uygun temel kapsayıcı sınıfları dahil [deque](../standard-library/deque-class.md), [listesinde sınıfı](../standard-library/list-class.md), ve [vector sınıfı](../standard-library/vector-class.md), veya işlemlerini destekleyen herhangi bir sıra kapsayıcısına **geri**, `push_back`, ve `pop_back`. Temel alınan kapsayıcı sınıfı yalnızca sıralı kapsayıcı üye işlevleri sınırlı sayıda ortak bir arabirim olarak kullanıma sunar kapsayıcı bağdaştırıcısı içinde kapsüllenir.

Yığın nesneleri: eşitlik için karşılaştırılabilir IF ve yalnızca sınıfı öğelerini **türü** eşitlik için karşılaştırılabilir ve daha az-karşılaştırılabilir IF ve yalnızca'den sınıfı öğelerini **türü** küçüktür-daha karşılaştırılabilir.

- Stack sınıfı son giren ilk çıkar (LIFO) veri yapısı destekler. Göz önünde bulundurmanız iyi bir analog kalıplarını yığınını olacaktır. Öğeleri (kalıplarını) eklenen, Denetlenmekte veya yalnızca en son öğe temel kapsayıcı sonunda yığınının kaldırıldı. Yalnızca üst öğesi erişmek için yığın sınıfını kullanarak nedeni kısıtlamadır.

- [Sıraya sınıfı](../standard-library/queue-class.md) ilk çıkar (FIFO) veri yapısı destekler. Göz önünde bulundurmanız iyi bir analog banka teller için hizalama kişiler olacaktır. Öğeleri (kişiler) satırın arkasına eklenebilir ve satır Önden kaldırılır. Ön ve arka satırının denetlenecek. Yalnızca ön ve arka öğeleri bu şekilde erişmek için sıra sınıfını kullanarak neden fur kısıtlamadır.

- [Priority_queue sınıfı](../standard-library/priority-queue-class.md) en büyük öğe her zaman üst konumunda böylece öğeleri sıralar. Bir öğe ve İnceleme ekleme ve kaldırma üst öğesinin destekler. Göz önünde bulundurmanız iyi bir analog burada bunlar yaşı, yükseklik veya başka bir ölçüt göre düzenlenmiş yukarı hizalama kişiler olacaktır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yığını](#stack)|Oluşturan bir `stack` diğer bir deyişle boş ya da bir taban kapsayıcı nesnesinin kopyasıdır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[container_type](#container_type)|Temel olarak uyarlanan kapsayıcıya sağlayan bir türü bir `stack`.|
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `stack`.|
|[value_type](#value_type)|Bir öğe olarak depolanan nesne türünü temsil eden bir tür bir `stack`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[boş](#empty)|Varsa testleri `stack` boş.|
|[POP](#pop)|Öğe üst kısmından kaldırır `stack`.|
|[push](#push)|Bir öğenin üst kısmına ekler `stack`.|
|[Boyutu](#size)|Öğelerin sayısını döndürür `stack`.|
|[Sayfanın Üstü](#top)|Öğenin üst kısmında bir başvuru döndürür `stack`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yığın >

**Namespace:** std

## <a name="container_type"></a>  Stack::container_type

Temel uyarlanan kapsayıcıya sağlayan türü.

```cpp
typedef Container container_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `Container`. Tüm üç C++ Standart Kitaplığı dizisi kapsayıcı sınıfları — vector sınıfı, liste sınıfı ve varsayılan sınıf deque — bir yığın nesnesi için temel kapsayıcı olarak kullanılacak gereksinimlerini. Kullanıcı tanımlı türler bu gereksinimleri karşılayan de kullanılabilir.

Daha fazla bilgi için `Container`, Açıklamalar bölümüne bakın [stack sınıfı](../standard-library/stack-class.md) konu.

### <a name="example"></a>Örnek

Örneğin bkz [stack::stack](#stack) bildirme ve kullanma konusunda bir örnek için `container_type`.

## <a name="empty"></a>  Stack::empty

Bir yığın boşsa, testleri.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yığın boşsa; **false** yığın boş olmayan ise.

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

## <a name="pop"></a>  Stack::POP

Öğeyi yığın üst kısmından kaldırır.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Yığın üye fonksiyonu uygulamak için boş olmamalıdır. Yığının en üst en son eklenen öğesi tarafından bulunulan konum ve kapsayıcı ucundaki son öğe.

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

## <a name="push"></a>  Stack::push

Bir öğenin üst yığının sonuna ekler.

```cpp
void push(const Type& val);
```

### <a name="parameters"></a>Parametreler

`val` Yığının en üst eklenen öğesi.

### <a name="remarks"></a>Açıklamalar

Yığının en üst en son eklenen öğesi tarafından bulunulan konum ve kapsayıcı ucundaki son öğe.

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

## <a name="size"></a>  Stack::size

Yığında öğe sayısını döndürür.

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

## <a name="size_type"></a>  Stack::size_type

Bir yığın öğe sayısı gösterebilir bir işaretsiz tamsayı türü.

```cpp
typedef typename Container::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `size_type` yığını tarafından uyarlanan temel kapsayıcısı.

### <a name="example"></a>Örnek

Örneğin bkz [boyutu](#size) bildirme ve kullanma konusunda bir örnek için `size_type`.

## <a name="stack"></a>  Stack::Stack

Boş veya temel kapsayıcı sınıfı kopyası olan bir yığın oluşturur.

```cpp
stack();

explicit stack(const container_type& right);
```

### <a name="parameters"></a>Parametreler

`right` Oluşturulan yığın kopyasını olmasını olduğu kapsayıcı.

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

## <a name="top"></a>  Stack::Top

Yığının üst öğeye bir başvuru döndürür.

```cpp
reference top();

const_reference top() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son yığının üst kapsayıcı öğesi referansı.

### <a name="remarks"></a>Açıklamalar

Yığın üye fonksiyonu uygulamak için boş olmamalıdır. Yığının en üst en son eklenen öğesi tarafından bulunulan konum ve kapsayıcı ucundaki son öğe.

Varsa dönüş değerini **üst** atanmış bir `const_reference`, yığın nesnesi değiştirilemez. Varsa dönüş değerini **üst** atanmış bir **başvuru**, stack nesnesi değiştirilebilir.

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

## <a name="value_type"></a>  Stack::value_type

Bir yığın bir öğe olarak depolanan nesne türünü temsil eden tür.

```cpp
typedef typename Container::value_type value_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `value_type` yığını tarafından uyarlanan temel kapsayıcısı.

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
