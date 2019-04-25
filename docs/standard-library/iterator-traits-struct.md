---
title: iterator_traits Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator_traits
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
ms.openlocfilehash: 6fe9e2d576afcacc7d014d4f5c920ecab3a83fc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224046"
---
# <a name="iteratortraits-struct"></a>iterator_traits Yapısı

Bir yineleyici olması gereken tüm kritik tür tanımlarını belirtmek için kullanılan bir şablon Yardımcısı yapı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct iterator_traits {
   typedef typename Iterator::iterator_category iterator_category;
   typedef typename Iterator::value_type value_type;
   typedef typename Iterator::difference_type difference_type;
   typedef difference_type distance_type;
   typedef typename Iterator::pointer pointer;
   typedef typename Iterator::reference reference;
   };
```

## <a name="remarks"></a>Açıklamalar

Şablon yapı üye türleri tanımlar.

- `iterator_category`: bir eşanlamlısı `Iterator::iterator_category`.

- `value_type`: bir eşanlamlısı `Iterator::value_type`.

- `difference_type`: bir eşanlamlısı `Iterator::difference_type`.

- `distance_type`: bir eşanlamlısı `Iterator::difference_type.`

- `pointer`: bir eşanlamlısı `Iterator::pointer`.

- `reference`: bir eşanlamlısı `Iterator::reference`.

Bir nesne işaretçisi türü ile ilişkili kritik türler kısmi uzmanlıklar belirlemek **türü** <strong>\*</strong> veya **const türünde**  <strong>\*</strong>.

Ayrıca bu uygulamada, kısmi alt uzmanlaşması haline getirmez birkaç şablon işlevleri kullanın:

```cpp
template <class Category, class Type, class Diff>
C _Iter_cat(const iterator<Category, Ty, Diff>&);

template <class Ty>
random_access_iterator_tag _Iter_cat(const Ty *);

template <class Category, class Ty, class Diff>
Ty *val_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
Ty *val_type(const Ty *);

template <class Category, class Ty, class Diff>
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
ptrdiff_t *_Dist_type(const Ty *);
```

hangi birkaç aynı tür daha dolaylı olarak belirleyin. Bu işlevler bir işlev çağrısında bağımsız değişkenleri olarak kullanın. Kullanıcıların tek amacı çağrılan işlev için kullanışlı bir şablon sınıfı parametresi sağlayın sağlamaktır.

## <a name="example"></a>Örnek

```cpp
// iterator_traits.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <vector>
#include <list>

using namespace std;

template< class it >
void
function( it i1, it i2 )
{
   iterator_traits<it>::iterator_category cat;
   cout << typeid( cat ).name( ) << endl;
   while ( i1 != i2 )
   {
      iterator_traits<it>::value_type x;
      x = *i1;
      cout << x << " ";
      i1++;
   };
   cout << endl;
};

int main( )
{
   vector<char> vc( 10,'a' );
   list<int> li( 10 );
   function( vc.begin( ), vc.end( ) );
   function( li.begin( ), li.end( ) );
}
/* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
