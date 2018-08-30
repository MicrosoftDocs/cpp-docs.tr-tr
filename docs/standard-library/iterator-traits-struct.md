---
title: iterator_traits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator_traits
dev_langs:
- C++
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4188c099e676ba58b0194953110fc2e62e8aced8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204925"
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
\* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*\
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
