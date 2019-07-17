---
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
ms.openlocfilehash: 1a0c8a04dda6c396b4f56d0939838fb6cb8e7455
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245934"
---
# <a name="allocator-class"></a>allocator Sınıfı

Şablon sınıfı türünde nesne dizileri için depolama ayırmayı ve boşaltmayı yöneten bir nesneyi tanımlayan `Type`. Sınıfın bir nesnesi `allocator` C++ Standart Kitaplığı'nda birkaç kapsayıcı şablon sınıflara yönelik oluşturucularda belirtilen varsayılan ayırıcı nesnesi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class allocator
```

### <a name="parameters"></a>Parametreler

*Tür*<br/>
Depolama kapatılıyor nesne türünü ayrılmış veya serbest bırakıldı.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak şablon parametresi tüm C++ Standart Kitaplığı kapsayıcıları sahip `allocator`. Özel bir ayırıcı ile bir kapsayıcı oluşturmak, ayırma ve serbest bu kapsayıcının öğeleri üzerinde denetim sağlayın.

Örneğin, bir ayırıcı nesnenin depolama özel yığının veya paylaşılan bellek ayırabilir veya küçük veya büyük nesne boyutları iyileştirebilir. Bu ayrıca, bu kaynakları, tür tanımlarını öğeleri paylaşılan bellek yönetmek ya da otomatik çöp toplama özel erişimci nesnelerde üzerinden belirtebilir. Bu nedenle, bir ayırıcı nesnesini kullanarak depolama ayıran bir sınıfı bu tür işaretçisi bildirmek için kullanın ve bu nesneleri C++ Standart Kitaplığı kapsayıcıları olarak başvuru gerekir.

<strong>(c ++ 98/03 yalnızca)</strong>  Ayırıcı sınıfından türer, sağlamanız gereken bir [rebind](#rebind) yapının, `_Other` typedef yeni türetilmiş sınıfınızın başvuruyor.

Bu nedenle, bir ayırıcı aşağıdaki türleri tanımlar:

- [İşaretçi](#pointer) bir işaretçi gibi davranır `Type`.

- [const_pointer](#const_pointer) const işaretçisi gibi davranır `Type`.

- [başvuru](#reference) başvurusu gibi davranır `Type`.

- [const_reference](#const_reference) const başvurusu gibi davranır `Type`.

Bunlar `Type`s işaretçileri ve başvuruları ayrılan öğeler için gerçekleştirmeniz gereken form belirtin. ( [allocator::pointer](#pointer) mutlaka aynı değil `Type*` tüm ayırıcı nesneleri için olsa bile, bu belirgin tanıma sahip sınıf için `allocator`.)

**C ++ 11 ve sonraki sürümleri:**  Taşıma işlemlerini, ayırıcı olarak etkinleştirmek için minimal ayırıcılar arabiriminin kullanın ve kopya Oluşturucu uygulamak, == ve! = işleçleri, ayırma ve serbest bırakın. Daha fazla bilgi ve örnek için bkz. [ayırıcılar](../standard-library/allocators.md)

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[allocator](#allocator)|Oluşturmak için kullanılan Oluşturucu `allocator` nesneleri.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|İşaretçiler ayırıcısı tarafından yönetilen nesne türü için değer arasındaki farkı temsil edebilen imzalı bir tamsayı türü.|
|[İşaretçi](#pointer)|Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|Ayırıcı tarafından yönetilen nesne türü bir başvuru sağlayan bir tür.|
|[size_type](#size_type)|Herhangi bir uzunluğunu temsil edebilen bir işaretsiz tamsayı türü dizisi şablon sınıfın bir nesnesi `allocator` ayırabilirsiniz.|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Adresi](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En azından bazı belirtilen sayıda öğeyi depolamak için büyük bir bellek bloğu ayırır.|
|[Yapısı](#construct)|Belirli türde bir nesne belirli bir değerle başlatılır, belirtilen bir adresteki oluşturur.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[yok](#destroy)|Bir nesne yok Edicisi belleğini olmadan nesne saklandığı çağırır.|
|[max_size](#max_size)|Tür öğelerin sayısını döndürür `Type` , ayrılan sınıfının bir nesnesiyle `allocator` boş bellek kullanılmadan önce.|
|[yeniden bağlayın](#rebind)|Başka bir türdeki nesneler için depolama alanı ayırmak için ayırıcı bir türden nesneler için sağlayan bir yapı.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator=](#op_eq)|Atar `allocator` başka bir nesneye `allocator` nesne.|

### <a name="address"></a> Adresi

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```

#### <a name="parameters"></a>Parametreler

*VAL*\
Const veya nonconst değeri nesnenin adresini aranır.

#### <a name="return-value"></a>Dönüş Değeri

Const veya nonconst nesneye işaretçi, sırasıyla, const veya nonconst değeri bulundu.

#### <a name="remarks"></a>Açıklamalar

Üye işlevleri adresini döndürmek *val*, işaretçiler atmanız için formun ayrılan öğeler.

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

### <a name="allocate"></a> ayırma

En azından bazı belirtilen sayıda öğeyi depolamak için büyük bir bellek bloğu ayırır.

```cpp
pointer allocate(size_type count, const void* _Hint);
```

#### <a name="parameters"></a>Parametreler

*Sayısı*\
Yeterli depolama alanı ayrılacak olan öğe sayısı.

*_Hint*\
Ayırıcı nesnesini yardımcı olabilecek bir const işaretçisi, istek önce ayrılmış bir nesne adresi bularak depolama talebi karşılamak.

#### <a name="return-value"></a>Dönüş Değeri

Ayrılmış nesneyi veya bellek tahsis yoksa null bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi depolama türü sayısı öğeler için bir dizi ayırır `Type`, yeni arama işleci (*sayısı*). Bu ayrılan bir nesneye bir işaretçi döndürür. İpucu bağımsız değişken başvuru yeri geliştirme içinde bazı ayırıcılar yardımcı olur; daha önce aynı ayırıcı nesnesi tarafından ayrılmış ve henüz serbest bırakılmış bir nesnenin adresini buna geçerli bir seçimdir. Hiçbir ipucu sağlamak için bir null işaretçi bağımsız değişkeni kullanın.

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

### <a name="allocator"></a> Ayırıcı

Ayırıcı nesneleri oluşturmak için kullanılan Oluşturucu.

```cpp
allocator();
allocator(const allocator<Type>& right);
template <class Other>
    allocator(const allocator<Other>& right);
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Kopyalanacak ayırıcı nesne.

#### <a name="remarks"></a>Açıklamalar

Oluşturucu hiçbir şey yapmaz. Genel olarak, ancak başka bir ayırıcı nesnesinden oluşturulan bir ayırıcı nesnenin ona eşit karşılaştırın ve nesne ayırma intermixing ve iki ayırıcı nesneleri boşaltma izin.

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

### <a name="const_pointer"></a> const_pointer

Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const value_type *const_pointer;
```

#### <a name="remarks"></a>Açıklamalar

İşaretçi türü bir nesneyi tanımlayan `ptr` , belirleyebilirler, ifade yoluyla `*ptr`, şablon sınıf ayırıcı nesnenin ayırabilirsiniz herhangi bir const nesnesi.

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

### <a name="const_reference"></a> const_reference

Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlayan bir tür.

```cpp
typedef const value_type& const_reference;
```

#### <a name="remarks"></a>Açıklamalar

Başvuru türü, şablon sınıf ayırıcı nesnenin ayırabilirsiniz herhangi bir const nesnesi belirleyebileceğiniz bir nesneyi tanımlar.

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

### <a name="construct"></a> Yapısı

Belirli türde bir nesne belirli bir değerle başlatılır, belirtilen bir adresteki oluşturur.

```cpp
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>
    void construct(pointer ptr, _Other&&... val);
```

#### <a name="parameters"></a>Parametreler

*PTR*\
Nesnenin oluşturulması olduğu yere bir işaretçi.

*VAL*\
Yapılandırılan nesnesinin başlatılacak olduğu değeri.

#### <a name="remarks"></a>Açıklamalar

İlk üye işlevi eşdeğerdir **yeni** ((`void` \*) `ptr`) **türü** (`val`).

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

### <a name="deallocate"></a> Serbest Bırak

Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.

```cpp
void deallocate(pointer ptr, size_type count);
```

#### <a name="parameters"></a>Parametreler

*PTR*\
Depolama alanından serbest bırakılması ilk nesneye bir işaretçi.

*Sayısı*\
Depolama alanından serbest bırakılması nesne sayısı.

#### <a name="remarks"></a>Açıklamalar

Üye işlev sayısı türü nesnelerin dizisi için depolama boşaltır `Type` konumunda başlayan *ptr*, çağırarak `operator delete(ptr)`. İşaretçi *ptr* önceki bir çağrı tarafından iade edilmiş gerekir [tahsis](#allocate) eşit karşılaştıran bir ayırıcı nesnesinin  **\*bu**, bir dizi ayırma aynı büyüklük ve türdeki nesne. `deallocate` hiçbir zaman bir özel durum oluşturur.

#### <a name="example"></a>Örnek

Üye işlevini kullanarak bir örnek için bkz [allocator::allocate](#allocate).

### <a name="destroy"></a> yok

Bir nesne yok Edicisi belleğini olmadan nesne saklandığı çağırır.

```cpp
void destroy(pointer ptr);
```

#### <a name="parameters"></a>Parametreler

*PTR*\
Yok edilecek nesnenin adresini gösteren bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından belirlenen nesnede yok eder *ptr*, yok edici çağırarak `ptr->` **türü**:: **~ türü**.

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

### <a name="difference_type"></a> difference_type

İşaretçiler ayırıcısı tarafından yönetilen nesne türü için değer arasındaki farkı temsil edebilen imzalı bir tamsayı türü.

```cpp
typedef ptrdiff_t difference_type;
```

#### <a name="remarks"></a>Açıklamalar

İmzalı bir tamsayı türü adreslerini şablon sınıf ayırıcı nesnenin ayırabilirsiniz bir dizideki herhangi iki öğe arasındaki farkı temsil edebilen bir nesneyi tanımlar.

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

### <a name="max_size"></a> max_size

Tür öğelerin sayısını döndürür `Type` , ayrılan bir nesnenin sınıf ayırıcısı tarafından boş bellek kullanılmadan önce.

```cpp
size_type max_size() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Ayrılamadı öğe sayısı.

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

### <a name="op_eq"></a> işleç =

Bir ayırıcı nesnesinin, başka bir ayırıcı nesnesine atar.

```cpp
template <class Other>
    allocator<Type>& operator=(const allocator<Other>& right);
```

#### <a name="parameters"></a>Parametreler

*sağ*\
Böyle bir nesne başka bir atanmış olan bir ayırıcı nesne.

#### <a name="return-value"></a>Dönüş Değeri

Allocator nesnesine bir başvuru

#### <a name="remarks"></a>Açıklamalar

Şablon atama işleci, hiçbir şey yapmaz. Genel olarak, ancak başka bir ayırıcı nesnesine atanmış bir ayırıcı nesnenin ona eşit karşılaştırın ve intermixing nesne ayırma ve serbest bırakma iki ayırıcı nesneleri izin.

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

### <a name="pointer"></a> İşaretçi

Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan bir tür.

```cpp
typedef value_type *pointer;
```

#### <a name="remarks"></a>Açıklamalar

İşaretçi türü bir nesneyi tanımlayan `ptr` , belirleyebilirler, ifade yoluyla  **\*ptr**, şablon sınıf ayırıcı nesnenin ayırabilirsiniz herhangi bir nesne.

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

### <a name="rebind"></a> yeniden bağlayın

Başka bir türdeki nesneler için depolama alanı ayırmak için ayırıcı bir türden nesneler için sağlayan bir yapı.

```cpp
struct rebind { typedef allocator<_Other> other; };
```

#### <a name="parameters"></a>Parametreler

*Diğer*\
Kendisi için bellek ayrılan öğe türü.

#### <a name="remarks"></a>Açıklamalar

Bu yapı, uygulanmakta olan bir kapsayıcı öğenin türünden farklı bir tür için bellek ayırma için kullanışlıdır.

Üye Şablon sınıfı, başka türü tanımlar. Tek amacı, tür adı sağlamaktır **ayırıcı**\<_ **diğer**>, tür adı verilen **ayırıcı** \< **türü** >.

Örneğin, bir ayırıcı nesnenin verilen `al` türü `A`, türünde bir nesne ayırabilirsiniz `_Other` ifadesiyle:

```cpp
A::rebind<Other>::other(al).allocate(1, (Other *)0)
```

Veya işaretçi türü türü yazarak ad verebilirsiniz:

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

### <a name="reference"></a> Başvuru

Ayırıcı tarafından yönetilen nesne türü bir başvuru sağlayan bir tür.

```cpp
typedef value_type& reference;
```

#### <a name="remarks"></a>Açıklamalar

Başvuru türü, bir şablon sınıf ayırıcı nesnenin ayırabilirsiniz herhangi bir nesne belirleyebileceğiniz bir nesneyi tanımlar.

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

### <a name="size_type"></a> size_type

Şablon sınıf ayırıcı nesnenin ayırabilirsiniz hiçbir sırası uzunluğu temsil edebilen bir işaretsiz tamsayı türü.

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

### <a name="value_type"></a> value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

#### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Type`.

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

## <a name="helpers"></a>Yardımcıları

### <a name="allocator_arg_t"></a> allocator_arg_t

```cpp
struct allocator_arg_t { explicit allocator_arg_t() = default; };
inline constexpr allocator_arg_t allocator_arg{};
```

### <a name="uses_allocator"></a> uses_allocator

```cpp
template <class T, class Alloc> struct uses_allocator;
```
