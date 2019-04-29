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
ms.openlocfilehash: 8e13d03e577df4c64e85704993cfc0ff81af5f8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369769"
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator Sınıfı

Algoritmaların başlatılmamış belleğe sonuçları depolamasını sağlamak üzere oluşturulmuş bağdaştırıcı sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class OutputIterator, class Type>
class raw_storage_iterator
```

### <a name="parameters"></a>Parametreler

*Outputıterator*<br/>
Çıkış yineleyici depolanmakta olan nesne için belirtir.

*Tür*<br/>
Kendisi için ayrılan depolama nesnenin türü.

## <a name="remarks"></a>Açıklamalar

Sınıf türü nesneleri oluşturan bir çıkış yineleyiciyi açıklayan `Type` sırada bu oluşturur. Sınıfın bir nesnesi `raw_storage_iterator` \< **ForwardIterator**, **türü**> sınıfın bir ileriye doğru yineleyici nesnesi, depolama alanına erişen `ForwardIterator`, ne zaman belirtin, nesnesi oluşturun. Bir nesne için birinci sınıf `ForwardIterator`, ifade  **& \*ilk** sonraki nesne için unconstructed depolama belirlemeniz gerekir (tür `Type`) oluşturulan sıralı.

Bellek ayırma ve nesne oluşturmayı ayırmak gerekli olduğunda bu bağdaştırıcı sınıf kullanılır. `raw_storage_iterator` Nesneleri kullanılarak ayrılmış bellek gibi başlatılmamış depolamaya kopyalamak için kullanılan `malloc` işlevi.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|Belirtilen temel alınan bir çıkış yineleyici ile bir ham depolama yineleyici oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[element_type](#element_type)|Ham depolama yineleyici olarak bir öğeyi tanımlayan tür depolanan sağlar.|
|[iter_type](#iter_type)|Ham depolama yineleyici altını çizen bir yineleyiciyi açıklayan tür sağlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Çıkış yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* `ii`  =  `x`.|
|[operator=](#op_eq)|Ham depolama yineleyici ifadesini uygulamak için kullanılan bir atama işleci \* `i`  =  `x` bellekte depolamak için.|
|[operator ++](#op_add_add)|Ham depolama yineleyiciler preincrement ve postincrement işleçler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="element_type"></a>  raw_storage_iterator::element_type

Ham depolama yineleyici olarak bir öğeyi tanımlayan tür depolanan sağlar.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>Açıklamalar

Raw_storage_iterator sınıfı şablon parametresi için bir eşanlamlı türüdür `Type`.

## <a name="iter_type"></a>  raw_storage_iterator::iter_type

Ham depolama yineleyici altını çizen bir yineleyiciyi açıklayan tür sağlar.

```cpp
typedef ForwardIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `ForwardIterator`.

## <a name="op_star"></a>  raw_storage_iterator::operator\*

Ham depolama yineleyici ifadesini uygulamak için kullanılan işleci başvurusunu kaldırma \* *II* = *x*.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Ham depolama yineleyici başvurusu

### <a name="remarks"></a>Açıklamalar

Gereksinimleri bir `ForwardIterator` ham olan depolama yineleyici gerektiren yalnızca ifade karşılaması gerekir \* *II* = *t* geçerli olması ve hiçbir şey hakkında söylüyor **işleci** veya `operator=` kendi. Bu uygulamada üye işleçleri döndürür  **\*bu**, böylece [işleç =](#op_eq)(**constType**&) gerçek deponun bir ifadede gerçekleştirebilirsiniz. gibi \* *ptr* = `val`.

### <a name="example"></a>Örnek

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
/* Output:
Not constructed.
Copying 5
Constructing 5
*/
```

## <a name="op_eq"></a>  raw_storage_iterator::operator=

Ham depolama yineleyici ifadesini uygulamak için kullanılan atama işleci \* *miyim* = *x* bellekte depolamak için.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Nesne türü değeri `Type` belleğe eklenecek.

### <a name="return-value"></a>Dönüş Değeri

İşleç ekler `val` belleğe ve ardından ham depolama yineleyici için bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Gereksinimleri bir `ForwardIterator` ham depolama yineleyici karşılamalıdır durumu yalnızca ifade gerektiren \* *II* = *t* geçerli olması ve hiçbir şey hakkında söylüyor **işleci** veya `operator=` kendi. Bu üye işleçleri dönüş  **\*bu**.

Atama işleci depolanmış yineleyiciyi değerini, ilk olarak, yerleştirme yeni ifadesinin değerlendirilmesi kullanarak çıkış dizisinde sonraki nesne oluşturan **yeni** (( `void` \*) &\* **ilk**) **türü**( `val`).

### <a name="example"></a>Örnek

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
/* Output:
Not constructed.
Copying 5
Constructing 5
*/
```

## <a name="op_add_add"></a>  raw_storage_iterator::operator++

Ham depolama yineleyiciler preincrement ve postincrement işleçler.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Ham depolama yineleyici veya ham depolama yineleyici başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk işleç sonunda ayıklayın ve türünde bir nesne depolamayı dener `CharType` ilişkili giriş akışından. İkinci işleç, nesnenin bir kopyasını oluşturur, nesne artırır ve kopyayı döndürür.

İlk preincrement işleci depolanan çıkış yineleyici nesnesini artırır ve döndürür  **\*bu**.

İkinci postincrement işleci bir kopyasını oluşturur  **\*bu**, depolanan çıkış yineleyici nesnesini artırır ve kopyayı döndürür.

Oluşturucu depoları `first` çıkış yineleyici nesnesi olarak.

### <a name="example"></a>Örnek

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
/* Output:
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
*/
```

## <a name="raw_storage_iterator"></a>  raw_storage_iterator::raw_storage_iterator

Belirtilen temel alınan bir çıkış yineleyici ile bir ham depolama yineleyici oluşturur.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Temelini oluşturan için ileriye doğru yineleyici `raw_storage_iterator` yapılandırılan bir nesne.

### <a name="example"></a>Örnek

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
/* Output:
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
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
