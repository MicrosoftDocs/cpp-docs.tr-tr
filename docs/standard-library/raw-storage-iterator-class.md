---
title: raw_storage_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
ms.openlocfilehash: 062a3db5c28bc463d6346a26cf1385adecd41183
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217642"
---
# <a name="raw_storage_iterator-class"></a>raw_storage_iterator Sınıfı

Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class OutputIterator, class Type>
    class raw_storage_iterator
```

### <a name="parameters"></a>Parametreler

*OutputIterator*\
Saklanacak nesne için çıkış yineleyicisini belirtir.

*Türüyle*\
Depolamanın ayrıldığı nesnenin türü.

## <a name="remarks"></a>Açıklamalar

Sınıfı, oluşturduğu dizide türünde nesneler oluşturan bir çıkış yineleyicisini açıklar `Type` . Sınıfının bir nesnesi `raw_storage_iterator` \< **ForwardIterator**, **Type**> `ForwardIterator` , nesnesini oluştururken belirttiğiniz bir ileriye doğru yineleyici nesnesi aracılığıyla depolamaya erişir. Sınıfın ilk bir nesnesi için `ForwardIterator` , ** & \* ilk** olarak ifadesi oluşturulan dizideki bir sonraki nesne (tür) için oluşturulmamış depolamayı belirlemelidir `Type` .

Bu bağdaştırıcı sınıfı, bellek ayırmayı ve nesne oluşturmayı ayırmak için gerekliyse kullanılır. , `raw_storage_iterator` İşlevi kullanılarak ayrılan bellek gibi başlatılmamış depolamaya nesneleri kopyalamak için kullanılabilir `malloc` .

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|Belirtilen temel alınan çıkış yineleyicisini içeren bir ham depolama yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[element_type](#element_type)|Ham depolama yineleyici depolanacak bir öğeyi açıklayan bir tür sağlar.|
|[iter_type](#iter_type)|Ham depolama yineleyici içeren bir yineleyiciyi açıklayan bir tür sağlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde](#op_star)|Çıkış Yineleyici ifadesini uygulamak için kullanılan bir başvuru kaldırma işleci \* `ii`  =  `x` .|
|[işleç =](#op_eq)|\* `i`  =  `x` Bellekte depolamaya yönelik ham depolama yineleyici ifadesini uygulamak için kullanılan atama işleci.|
|[işleç + +](#op_add_add)|Ham depolama yineleyiciler için preıncrement ve postıncrement işleçleri.|

### <a name="element_type"></a><a name="element_type"></a>element_type

Ham depolama yineleyici depolanacak bir öğeyi açıklayan bir tür sağlar.

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, raw_storage_iterator sınıfı şablon parametresi için bir eş anlamlı `Type` .

### <a name="iter_type"></a><a name="iter_type"></a>iter_type

Ham depolama yineleyici içeren bir yineleyiciyi açıklayan bir tür sağlar.

```cpp
typedef ForwardIterator iter_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `ForwardIterator` .

### <a name="operator"></a><a name="op_star"></a>işlecinde\*

Ham depolama yineleyici ifadesi \* *II*  =  *x*'i uygulamak için kullanılan bir başvuru kaldırma işleci.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

#### <a name="return-value"></a>Dönüş Değeri

Ham depolama yineleyici başvurusu

#### <a name="remarks"></a>Açıklamalar

Bir için gereksinimler, `ForwardIterator` ham depolama yineleyicisinin yalnızca ifade \* *II*'nin  =  *t* geçerli olması ve **`operator`** ya da `operator=` kendi üzerinde veya kendi üzerinde hiçbir şey yazmadığını gerektirmelidir. Bu uygulamadaki üye işleçleri ** \* bunu**döndürür, böylece [operator =](#op_eq)(**constType**&), gerçek depoyu PTR gibi bir ifadede gerçekleştirebilir \* *ptr*  =  `val` .

#### <a name="example"></a>Örnek

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
*pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_eq"></a>işleç =

\* *i*  =  Bellekte depolamaya yönelik ham depolama yineleyici ifadesi ı*x* 'i uygulamak için kullanılan atama işleci.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

#### <a name="parameters"></a>Parametreler

*Acil*\
Belleğe eklenecek türü nesnenin değeri `Type` .

#### <a name="return-value"></a>Dönüş Değeri

İşleci belleğe eklenir `val` ve ham depolama yineleyici için bir başvuru döndürür.

#### <a name="remarks"></a>Açıklamalar

`ForwardIterator`Ham depolama yineleyicisinin karşılaması gereken bir durum için gereksinimler yalnızca ifade \* *II*'nin  =  *t* geçerli olması ve **`operator`** ya da `operator=` kendi üzerinde veya kendi üzerinde hiçbir şey yazmadığını gerektirir. Bu üye işleçleri döndürülür **`*this`** .

Atama işleci, `first` yerleştirme yeni ifadesini değerlendirerek, depolanan yineleyici değerini kullanarak çıkış dizisinde bir sonraki nesneyi oluşturur `new ( (void*) & *first ) Type( val )` .

#### <a name="example"></a>Örnek

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
*it = 5;
}
```

```Output
Not constructed.
Copying 5
Constructing 5
```

### <a name="operator"></a><a name="op_add_add"></a>işleç + +

Ham depolama yineleyiciler için preıncrement ve postıncrement işleçleri.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

#### <a name="return-value"></a>Dönüş Değeri

Ham depolama yineleyici veya ham depolama yineleyici başvurusu.

#### <a name="remarks"></a>Açıklamalar

İlk operatör sonunda, ilişkili giriş akışından bir nesne türünü ayıklamaya ve depolamaya çalışır `CharType` . İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

İlk preıncrement işleci, depolanan çıkış yineleyici nesnesini artırır ve ** \* bunu**döndürür.

İkinci postıncrement işleci ** \* bunun**bir kopyasını oluşturur, depolanan çıkış yineleyici nesnesini artırır ve sonra kopyayı döndürür.

Oluşturucu `first` Çıkış yineleyici nesnesi olarak depolar.

#### <a name="example"></a>Örnek

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
      *it = 2 * i;
   };

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
```

```Output
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
```

### <a name="raw_storage_iterator"></a><a name="raw_storage_iterator"></a>raw_storage_iterator

Belirtilen temel alınan çıkış yineleyicisini içeren bir ham depolama yineleyici oluşturur.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

#### <a name="parameters"></a>Parametreler

*adı*\
Oluşturulmakta olan nesneyi düşük olan ileri Yineleyici `raw_storage_iterator` .

#### <a name="example"></a>Örnek

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
```

```Output
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
```
