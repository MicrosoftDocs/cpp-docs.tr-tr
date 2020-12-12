---
description: 'Hakkında daha fazla bilgi edinin: iterator_traits struct'
title: iterator_traits Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator_traits
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
ms.openlocfilehash: ac97b84ff7bcedc00f2b069ce05f734ac65618ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289692"
---
# <a name="iterator_traits-struct"></a>iterator_traits Yapısı

Bir yineleyicinin sahip olması gereken tüm kritik tür tanımlarını belirtmek için kullanılan bir şablon Yardımcısı yapısı.

## <a name="syntax"></a>Syntax

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

Şablon yapısı üye türlerini tanımlar

- `iterator_category`: için bir eş anlamlı `Iterator::iterator_category` .

- `value_type`: için bir eş anlamlı `Iterator::value_type` .

- `difference_type`: için bir eş anlamlı `Iterator::difference_type` .

- `distance_type`: için bir eş anlamlı `Iterator::difference_type.`

- `pointer`: için bir eş anlamlı `Iterator::pointer` .

- `reference`: için bir eş anlamlı `Iterator::reference` .

Kısmi uzmanlık **, tür** <strong>\*</strong> veya **const türünde** bir nesne işaretçiyle ilişkili kritik türleri tespit <strong>\*</strong> .

Bu uygulamada, kısmi özelleşmenin kullanıldığı çeşitli şablon işlevleri de kullanabilirsiniz:

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

aynı türden birkaçını daha dolaylı olarak belirleyen. Bu işlevleri bir işlev çağrısında bağımsız değişken olarak kullanırsınız. Tek amaçları, çağrılan işleve yararlı bir sınıf şablonu parametresi sağlamaktır.

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

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
