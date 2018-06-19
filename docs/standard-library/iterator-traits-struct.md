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
ms.openlocfilehash: 57387af452ff4a127eec6b669cec6e02863b8fd3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856628"
---
# <a name="iteratortraits-struct"></a>iterator_traits Yapısı

Şablon yardımcı yapı yineleyici olması gereken tüm kritik tür tanımları belirtmek için kullanılır.

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

Şablon yapısı üye türleri tanımlar

- **iterator_category**: eşanlamlısı **Iterator::iterator_category**.

- `value_type`: eşanlamlısı **Iterator::value_type**.

- `difference_type`: eşanlamlısı **Iterator::difference_type**.

- `distance_type`: eşanlamlısı **Iterator::difference_type.**

- **İşaretçi**: eşanlamlısı **Iterator::pointer**.

- **başvuru**: eşanlamlısı **Iterator::reference**.

Kısmi özelleştirmeleri türü bir nesne işaretçisi ile ilişkilendirilmiş kritik türleri belirlemek **türü \***  veya const **türü \*** .

Aynı zamanda bu uygulamasında hale birkaç şablon işlevleri kısmi uzmanlığı kullanın:

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

hangi birkaç aynı türdeki daha dolaylı olarak belirleyin. Bu işlevler işlevi çağrısında bağımsız değişkenleri olarak kullanın. Çağrılan işlev için yararlı Şablon sınıfı parametresi sağlamak için bunların tek amacı olan.

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
