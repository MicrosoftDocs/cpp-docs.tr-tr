---
description: 'Daha fazla bilgi edinin: ayırıcı sınıfı'
title: allocator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
helpviewer_keywords:
- std::allocator [C++]
- std::allocator [C++], const_pointer
- std::allocator [C++], const_reference
- std::allocator [C++], difference_type
- std::allocator [C++], pointer
- std::allocator [C++], reference
- std::allocator [C++], size_type
- std::allocator [C++], value_type
- std::allocator [C++], address
- std::allocator [C++], allocate
- std::allocator [C++], construct
- std::allocator [C++], deallocate
- std::allocator [C++], destroy
- std::allocator [C++], max_size
- std::allocator [C++], rebind
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
ms.openlocfilehash: f1f54aae3191d261d549e69e942974fc46a670f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163632"
---
# <a name="allocator-class"></a>allocator Sınıfı

Sınıf şablonu, türünde nesne dizileri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlar `Type` . Sınıfının bir nesnesi, `allocator` C++ standart kitaplığındaki çeşitli kapsayıcı sınıfı şablonlarının oluşturucuları 'nda belirtilen varsayılan ayırıcı nesnesidir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Depolamanın ayrıldığı veya serbest bırakıldığı nesnenin türü.

## <a name="remarks"></a>Açıklamalar

Tüm C++ standart kitaplığı kapsayıcıları için varsayılan olarak kullanılacak bir şablon parametresi vardır `allocator` . Özel ayırıcı içeren bir kapsayıcı oluşturmak, bu kapsayıcının öğelerinin ayrılması ve serbest bırakma üzerinde denetim sağlar.

Örneğin, bir ayırıcı nesne bir özel yığında veya paylaşılan bellekte depolama alanı ayırabilir veya küçük veya büyük nesne boyutları için iyileştirebilirler. Ayrıca, sağladığı tür tanımlarına, bu öğelere paylaşılan belleği yöneten özel erişimci nesneleri aracılığıyla erişildiğini veya otomatik çöp toplama işlemini de belirtebilir. Bu nedenle, bir ayırıcı nesnesi kullanarak depolamayı ayıran bir sınıf, C++ standart kitaplığı 'ndaki kapsayıcılar gibi işaretçi ve başvuru nesnelerini bildirmek için bu türleri kullanmalıdır.

<strong>(Yalnızca C++ 98/03)</strong> Ayırıcı sınıfından türettiğinizde, [](#rebind) `_Other` typedef yeni türetilmiş sınıfınıza başvuran bir yeniden bağlama yapısı sağlamanız gerekir.

Bu nedenle, bir ayırıcı aşağıdaki türleri tanımlar:

- [işaretçi](#pointer) , için bir işaretçi gibi davranır `Type` .

- [const_pointer](#const_pointer) , için bir const işaretçisi gibi davranır `Type` .

- [başvuru](#reference) , öğesine başvuru gibi davranır `Type` .

- [const_reference](#const_reference) , öğesine bir const başvurusu gibi davranır `Type` .

Bu `Type` s, işaretçiler ve başvuruların ayrılan öğeler için uygulanması gereken formu belirler. ( [ayırıcı:](#pointer) `Type*` sınıf için bu açık tanımına sahip olsa bile,:p oınter 'in tüm ayırıcı nesneleri ile aynı olması gerekmez `allocator` .)

**C++ 11 ve üzeri:**  Ayıramanız içindeki taşıma işlemlerini etkinleştirmek için, en az ayırıcı arabirimini kullanın ve kopya oluşturucuyu, = = ve! = işleçlerini uygulayın, ayırır ve serbest bırakın. Daha fazla bilgi ve bir örnek için bkz. [ayırıcılar](allocators.md)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[allocator](#allocator)|Nesneleri oluşturmak için kullanılan oluşturucular `allocator` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.|
|[pointer](#pointer)|Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.|
|[size_type](#size_type)|Türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü `allocator` .|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[adrestir](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En az bazı sayıda öğe depolamak için yeterince büyük bir bellek bloğu ayırır.|
|[oluşturma](#construct)|Belirtilen bir değer ile başlatılan belirli bir adreste belirli bir nesne türü oluşturur.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[kaldırılır](#destroy)|Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.|
|[max_size](#max_size)|`Type`Boş bellek kullanılmadan önce sınıfının bir nesnesi tarafından ayrılabilecek türdeki öğe sayısını döndürür `allocator` .|
|[Rebind](#rebind)|Bir tür nesneler için bir ayırıcı, başka bir türdeki nesneler için depolama alanı ayırmasına olanak tanıyan bir yapı.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir `allocator` nesneyi başka bir `allocator` nesneye atar.|

### <a name="address"></a><a name="address"></a> adrestir

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```

#### <a name="parameters"></a>Parametreler

*Acil*\
Adresi aranmakta olan nesnenin const veya nonconst değeri.

#### <a name="return-value"></a>Dönüş Değeri

, Sırasıyla const veya nonconst değeri bulunan nesnenin const veya nonconst bir işaretçisi.

#### <a name="remarks"></a>Açıklamalar

Üye işlevleri, ayrılan öğeler için işaretçiler olması gereken biçimde *Val* adresini döndürür.

#### <a name="example"></a>Örnek

```cpp
// allocator_address.cpp
// compile with: /EHsc
#include <memory>
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 8;
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );
   // v1Ptr = v1Alloc.address( k );
   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.
```

### <a name="allocate"></a><a name="allocate"></a> allocate

En az bazı sayıda öğe depolamak için yeterince büyük bir bellek bloğu ayırır.

```cpp
pointer allocate(size_type count, const void* _Hint);
```

#### <a name="parameters"></a>Parametreler

*biriktirme*\
Yeterli depolamanın ayrılabileceği öğe sayısı.

*_Hint*\
, İstekten önce ayrılan bir nesnenin adresini bularak, ayırıcı nesnesine yardımcı olabilecek bir const işaretçisi.

#### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi veya bellek ayrıldıysa null.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi `Type` , New işleci (*Count*) çağırarak türünde bir Count öğeleri dizisi için depolama ayırır. Ayrılan nesneye bir işaretçi döndürür. İpucu bağımsız değişkeni, başvuru yerinin gelişmesinin bazı ayırıcılarına yardımcı olur; geçerli bir seçenek, aynı ayırıcı nesne tarafından daha önce ayrılan ve henüz serbest bırakılmayan bir nesnenin adresidir. İpucu sağlamak için, bunun yerine null işaretçi bağımsız değişkenini kullanın.

#### <a name="example"></a>Örnek

```cpp
// allocator_allocate.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<int> v1Alloc;
   allocator<int>::pointer v1aPtr;
   v1aPtr = v1Alloc.allocate ( 10 );

   int i;
   for ( i = 0 ; i < 10 ; i++ )
   {
      v1aPtr[ i ] = i;
   }

   for ( i = 0 ; i < 10 ; i++ )
   {
      cout << v1aPtr[ i ] << " ";
   }
   cout << endl;
   v1Alloc.deallocate( v1aPtr, 10 );
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

### <a name="allocator"></a><a name="allocator"></a> öğe

Ayırıcı nesneleri oluşturmak için kullanılan oluşturucular.

```cpp
allocator();
allocator(const allocator<Type>& right);
template <class Other>
    allocator(const allocator<Other>& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
Kopyalanacak ayırıcı nesne.

#### <a name="remarks"></a>Açıklamalar

Oluşturucu hiçbir şey yapmaz. Ancak, genel olarak, başka bir ayırıcı nesnesinden oluşturulan bir ayırıcı nesne buna eşit olarak karşılaştırmalı ve iki ayırıcı nesne arasında nesne ayırmayı ve serbest bırakma işlemine izin verir.

#### <a name="example"></a>Örnek

```cpp
// allocator_allocator.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int( int i )
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<double> Alloc;
   vector <Int>:: allocator_type v1Alloc;

   allocator<double> cAlloc(Alloc);
   allocator<Int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="const_pointer"></a><a name="const_pointer"></a> const_pointer

Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const value_type *const_pointer;
```

#### <a name="remarks"></a>Açıklamalar

İşaretçi türü, `ptr` ifadesi `*ptr` , türü bir nesnenin ayıraşabolduğu herhangi bir const nesnesi aracılığıyla belirleyebilecek bir nesneyi tanımlar `allocator` .

#### <a name="example"></a>Örnek

```cpp
// allocator_const_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 10;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer's address found has a value of: "
        << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The integer's address found has a value of: 10.
```

### <a name="const_reference"></a><a name="const_reference"></a> const_reference

Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.

```cpp
typedef const value_type& const_reference;
```

#### <a name="remarks"></a>Açıklamalar

Başvuru türü, türü bir nesnenin ayıraşabolduğu herhangi bir const nesnesini belirleyebilecek bir nesneyi tanımlar `allocator` .

#### <a name="example"></a>Örnek

```cpp
// allocator_const_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::const_reference vcref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vcref << ",\n the first element in the vector." << endl;

   // const references can have their elements modified,
   // so the following would generate an error:
   // vcref = 150;
   // but the value of the first element could be modified through
   // its nonconst iterator and the const reference would remain valid
*vfIter = 175;
   cout << "The value of the element referred to by vcref,"
        <<"\n after nofication through its nonconst iterator, is: "
        << vcref << "." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
the first element in the vector.
The value of the element referred to by vcref,
after nofication through its nonconst iterator, is: 175.
```

### <a name="construct"></a><a name="construct"></a> oluşturma

Belirtilen bir değer ile başlatılan belirli bir adreste belirli bir nesne türü oluşturur.

```cpp
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>
    void construct(pointer ptr, _Other&&... val);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Nesnenin oluşturulması gereken konuma yönelik bir işaretçi.

*Acil*\
Oluşturulan nesnenin başlatılacağı değer.

#### <a name="remarks"></a>Açıklamalar

İlk üye işlevi değerine eşdeğerdir `new ((void *) ptr) Type(val)` .

#### <a name="example"></a>Örnek

```cpp
// allocator_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 6, kB = 7;
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 3 6 9 12 15 18 21 ).
The modified vector v1 is:
( 3 7 9 12 15 18 21 ).
```

### <a name="deallocate"></a><a name="deallocate"></a> kaldırmak

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(pointer ptr, size_type count);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.

*biriktirme*\
Depolamadan serbest bırakmak için nesne sayısı.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi, `Type` ' ı çağırarak, *PTR* ile başlayan türdeki Count nesnelerinin dizisi için depolamayı boşaltır `operator delete(ptr)` . İşaretçi *PTR* , aynı boyut ve türden bir dizi nesnesi ayırarak, **\* Bu** değere eşit olarak karşılaştırıldığı bir ayırıcı nesnesini [ayırmak](#allocate) için bir çağrı tarafından daha önce döndürüldü. `deallocate` hiçbir koşulda özel durum oluşturmaz.

#### <a name="example"></a>Örnek

Üye işlevini kullanan bir örnek için bkz. [ayırıcı:: allocate](#allocate).

### <a name="destroy"></a><a name="destroy"></a> kaldırılır

Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.

```cpp
void destroy(pointer ptr);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Yok edilecek nesnenin adresini atayarak bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi, yıkıcıyı çağırarak *PTR* tarafından atanan nesneyi yok eder `ptr->Type::~Type` .

#### <a name="example"></a>Örnek

```cpp
// allocator_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 12, kB = -99;
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 2 4 6 8 10 12 14 ).
The modified vector v1 is:
( 2 4 6 8 10 -99 14 ).
```

### <a name="difference_type"></a><a name="difference_type"></a> difference_type

Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.

```cpp
typedef ptrdiff_t difference_type;
```

#### <a name="remarks"></a>Açıklamalar

İmzalanan tamsayı türü, bir nesnenin bir nesne tarafından ayıraşabecağı bir dizideki iki öğenin adresleri arasındaki farkı temsil eden bir nesneyi tanımlar `allocator` .

#### <a name="example"></a>Örnek

```cpp
// allocator_diff_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 0 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1PtrA, v1PtrB;
   const int kA = 4, kB =12;
   v1PtrA = v1Alloc.address( kA );
   v1PtrB = v1Alloc.address( kB );
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;

   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;
   cout << "The difference between the integer's addresses is: "
        << v1diff << "." << endl;
}
```

```Output
The original vector v1 is:
( 0 2 4 6 8 10 12 14 ).
Pointer v1PtrA addresses 4.
Pointer v1PtrB addresses 12.
The difference between the integer's addresses is: 8.
```

### <a name="max_size"></a><a name="max_size"></a> max_size

`Type`Boş bellek kullanılmadan önce sınıf ayırıcı nesnesi tarafından ayrılabilecek türdeki öğe sayısını döndürür.

```cpp
size_type max_size() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen öğe sayısı.

#### <a name="example"></a>Örnek

```cpp
// allocator_max_size.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   vector <double> v2;
   vector <double> ::iterator v2Iter;
   vector <double> :: allocator_type v2Alloc;
   allocator<int>::size_type v1size;
   v1size = v1Alloc.max_size( );

   cout << "The number of integers that can be allocated before\n"
        << " the free memory in the vector v1 is used up is: "
        << v1size << "." << endl;

   int ii;
   for ( ii = 1 ; ii <= 7 ; ii++ )
   {
      v2.push_back( ii * 10.0 );
   }

   cout << "The original vector v2 is:\n ( " ;
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )
      cout << *v2Iter << " ";
   cout << ")." << endl;
   allocator<double>::size_type v2size;
   v2size = v2Alloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v2 is used up is: "
        << v2size << "." << endl;
}
```

### <a name="operator"></a><a name="op_eq"></a> işleç =

Başka bir ayırıcı nesnesine bir ayırıcı nesnesi atar.

```cpp
template <class Other>
    allocator<Type>& operator=(const allocator<Other>& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
Bu tür bir nesneye atanacak ayırıcı nesne.

#### <a name="return-value"></a>Dönüş Değeri

Ayırıcı nesnesine bir başvuru

#### <a name="remarks"></a>Açıklamalar

Şablon atama işleci hiçbir şey yapmaz. Bununla birlikte, genel olarak, başka bir ayırıcı nesnesine atanan bir ayırıcı nesnesi ona eşit olarak karşılaştırmalı ve iki ayırıcı nesne arasında nesne ayırmayı ve serbest bırakma işlemine izin verir.

#### <a name="example"></a>Örnek

```cpp
// allocator_op_assign.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( ) {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<Int> Alloc;
   allocator<Int> cAlloc ;
   cAlloc = Alloc;
}
```

### <a name="pointer"></a><a name="pointer"></a> çağrısı

Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.

```cpp
typedef value_type *pointer;
```

#### <a name="remarks"></a>Açıklamalar

İşaretçi türü, `ptr` **\* PTR** ifadesi ve türü bir nesne ayırabilecek herhangi bir nesne tarafından belirleyebilecek bir nesneyi tanımlar `allocator` .

#### <a name="example"></a>Örnek

```cpp
// allocator_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 12;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
( 3 6 9 12 15 18 21 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.
```

### <a name="rebind"></a><a name="rebind"></a> Rebind

Bir tür nesneler için bir ayırıcı, başka bir türdeki nesneler için depolama alanı ayırmasına olanak tanıyan bir yapı.

```cpp
struct rebind { typedef allocator<_Other> other; };
```

#### <a name="parameters"></a>Parametreler

*farklı*\
Belleğin ayrıldığı öğenin türü.

#### <a name="remarks"></a>Açıklamalar

Bu yapı, uygulanan kapsayıcının öğe türünden farklı tür için bellek ayırmak için yararlıdır.

Üye sınıfı şablonu diğer türü tanımlar. Tek amacı, tür adı verilen tür adını sağlamaktır `allocator<_Other>` `allocator<Type>` .

Örneğin, türünde bir ayırıcı nesnesi verildiğinde `al` `A` , ifadesi ile türünde bir nesne ayırabilirsiniz `_Other` :

```cpp
A::rebind<Other>::other(al).allocate(1, (Other *)0)
```

Ya da tür yazarak işaretçi türünü de yazabilirsiniz:

```cpp
A::rebind<Other>::other::pointer
```

#### <a name="example"></a>Örnek

```cpp
// allocator_rebind.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

typedef vector<int>::allocator_type IntAlloc;
int main( )
{
   IntAlloc v1Iter;
   vector<int> v1;

   IntAlloc::rebind<char>::other::pointer pszC =
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);

   int * pInt = v1Iter.allocate(10);
}
```

### <a name="reference"></a><a name="reference"></a> başvurunun

Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.

```cpp
typedef value_type& reference;
```

#### <a name="remarks"></a>Açıklamalar

Başvuru türü, bir nesnenin türü bir nesne ayırabilecek herhangi bir nesneyi belirleyebilecek bir nesneyi tanımlar `allocator` .

#### <a name="example"></a>Örnek

```cpp
// allocator_reference.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::reference vref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vref << ",\n the first element in the vector." << endl;

   // nonconst references can have their elements modified
   vref = 150;
   cout << "The element referred to by vref after being modified is: "
        << vref << "." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
the first element in the vector.
The element referred to by vref after being modified is: 150.
```

### <a name="size_type"></a><a name="size_type"></a> size_type

Türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü `allocator` .

```cpp
typedef size_t size_type;
```

#### <a name="example"></a>Örnek

```cpp
// allocator_size_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   allocator<double>::size_type vsize;
   vsize = vAlloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v is used up is: "
        << vsize << "." << endl;
}
```

### <a name="value_type"></a><a name="value_type"></a> value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Type` .

#### <a name="example"></a>Örnek

```cpp
// allocator_value_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::value_type vecVal = 150.0;
*vfIter = vecVal;
   cout << "The value of the element addressed by vfIter is: "
        << *vfIter << ",\n the first element in the vector." << endl;

   cout << "The modified vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v is:
( 100 200 300 400 500 600 700 ).
The value of the element addressed by vfIter is: 150,
the first element in the vector.
The modified vector v is:
( 150 200 300 400 500 600 700 ).
```

## <a name="helpers"></a>Yardımcı

### <a name="allocator_arg_t"></a><a name="allocator_arg_t"></a> allocator_arg_t

```cpp
struct allocator_arg_t { explicit allocator_arg_t() = default; };
inline constexpr allocator_arg_t allocator_arg{};
```

### <a name="uses_allocator"></a><a name="uses_allocator"></a> uses_allocator

```cpp
template <class T, class Alloc> struct uses_allocator;
```
