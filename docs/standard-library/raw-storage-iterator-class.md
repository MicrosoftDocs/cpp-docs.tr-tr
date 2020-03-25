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
ms.openlocfilehash: 9372fa884d75e10c1a0f2ec92d6cca9caa65808e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167621"
---
# <a name="raw_storage_iterator-class"></a>raw_storage_iterator Sınıfı

Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class OutputIterator, class Type>
    class raw_storage_iterator
```

### <a name="parameters"></a>Parametreler

*OutputIterator*\
Saklanacak nesne için çıkış yineleyicisini belirtir.

*Tür*\
Depolamanın ayrıldığı nesnenin türü.

## <a name="remarks"></a>Açıklamalar

Sınıfı, oluşturduğu dizide `Type` türünde nesneler oluşturan bir çıkış yineleyicisini açıklar. `raw_storage_iterator`\< **ForwardIterator**sınıfının bir nesnesi **, > nesne**oluştururken belirttiğiniz bir ileri Yineleyici `ForwardIterator`nesnesi aracılığıyla depolama alanına erişir. `ForwardIterator`sınıfının ilk bir nesnesi için, **&\*ifadesi ilk** olarak oluşturulan dizideki bir sonraki nesne (tür `Type`) için oluşturulmamış depolamayı belirlemelidir.

Bu bağdaştırıcı sınıfı, bellek ayırmayı ve nesne oluşturmayı ayırmak için gerekliyse kullanılır. `raw_storage_iterator`, `malloc` işlevi kullanılarak ayrılan bellek gibi başlatılmamış depolamaya nesneleri kopyalamak için kullanılabilir.

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
|[işlecinde](#op_star)|\* `ii` = `x`çıkış yineleyici ifadesini uygulamak için kullanılan bir başvuru kaldırma işleci.|
|[işleç =](#op_eq)|Bellekte depolamada `i` = `x` ham depolama yineleyici ifadesini uygulamak için kullanılan atama işleci \*.|
|[işleç + +](#op_add_add)|Ham depolama yineleyiciler için preıncrement ve postıncrement işleçleri.|

### <a name="element_type"></a><a name="element_type"></a>element_type

Ham depolama yineleyici depolanacak bir öğeyi açıklayan bir tür sağlar.

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, `Type`raw_storage_iterator sınıf şablonu parametresinin bir eş anlamlısıdır.

### <a name="iter_type"></a><a name="iter_type"></a>iter_type

Ham depolama yineleyici içeren bir yineleyiciyi açıklayan bir tür sağlar.

```cpp
typedef ForwardIterator iter_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, `ForwardIterator`şablon parametresi için bir eş anlamlı.

### <a name="operator"></a><a name="op_star"></a>işleç\*

\* *ıı* = *x*ham depolama yineleyici ifadesini uygulamak için kullanılan bir başvuru kaldırma işleci.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

#### <a name="return-value"></a>Dönüş Değeri

Ham depolama yineleyici başvurusu

#### <a name="remarks"></a>Açıklamalar

Bir `ForwardIterator` için gereksinimler, ham depolama yineleyicisinin yalnızca Expression \* *ıı* = *t* 'nin geçerli olması ve **işleç** ya da kendi üzerinde `operator=` herhangi bir şey yazmadığını belirtir. Bu uygulamadaki üye işleçleri **\*** döndürür, böylece [operator =](#op_eq)(**constType**&), gerçek mağazayı \* *PTR* = `val`gibi bir ifadede gerçekleştirebilir.

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

Ham depolama yineleyici ifadesini uygulamak için kullanılan atama işleci, bellekte depolamak için *ı* = *x* \*.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

#### <a name="parameters"></a>Parametreler

*val*\
Belleğe eklenecek `Type` türündeki nesnenin değeri.

#### <a name="return-value"></a>Dönüş Değeri

İşleci belleğe `val` ekler ve sonra ham depolama yineleyici için bir başvuru döndürür.

#### <a name="remarks"></a>Açıklamalar

Ham depolama yineleyicisinin karşılaması gereken `ForwardIterator` bir durum için gereksinimler yalnızca Expression \* *ıı* = *t* 'nin geçerli olması ve **işleç** ya da kendi üzerinde `operator=` herhangi bir şey söymesini gerektirir. Bu üye işleçleri **\*** döndürür.

Atama işleci ilk olarak, **yeni ifade (** (`void` \*) &\* **ilk**) **türü**(`val`) olarak hesaplanarak, önce depolanan yineleyici değerini kullanarak çıkış dizisinde bir sonraki nesneyi oluşturur.

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

İlk operatör sonunda, ilişkili giriş akışından `CharType` türünde bir nesneyi ayıklamaya ve depolamaya çalışır. İkinci işleç nesnenin bir kopyasını yapar, nesneyi artırır ve sonra kopyayı döndürür.

İlk preıncrement işleci, depolanan çıkış yineleyici nesnesini artırır ve sonra **\*** döndürür.

İkinci postıncrement işleci **bunun\*** bir kopyasını yapar, depolanan çıkış yineleyici nesnesini artırır ve sonra kopyayı döndürür.

Oluşturucu, `first` çıkış yineleyici nesnesi olarak depolar.

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

*ilk*\
Oluşturulan `raw_storage_iterator` nesnesini yetersiz duruma getirmek için kullanılan ileri Yineleyici.

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
