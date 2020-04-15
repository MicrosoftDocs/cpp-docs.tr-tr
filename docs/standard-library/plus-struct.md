---
title: plus Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::plus
helpviewer_keywords:
- plus class
- plus struct
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
ms.openlocfilehash: 628823a7fc3c176f83bbb1dca59ec194b5d3db97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372077"
---
# <a name="plus-struct"></a>plus Yapısı

Bağımsız değişkenlerinde ekleme işlemini (ikili) `operator+`gerçekleştiren önceden tanımlanmış bir işlev nesnesi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type = void>
struct plus : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator+
template <>
struct plus<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) + std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Türü*, *T*, *U*\
Belirtilen veya çıkarılan `operator+` türlerin operands alan bir ikili destekleyen bir tür.

*Sol*\
Ekleme işleminin sol operand'ı. Özelleştirilmemiş *şablon, türünden*bir lvalue başvuru bağımsız değişkeni alır. Özelleştirilmiş şablon, çıkarılan *t*tipinin lvalue ve rvalue referans bağımsız değişkenlerinin mükemmel iletilmesi yapar.

*Doğru*\
Ekleme işleminin sağ operand'ı. Özelleştirilmemiş *şablon, türünden*bir lvalue başvuru bağımsız değişkeni alır. Özelleştirilmiş şablon, çıkarılan *u*türündeki lvalue ve rvalue referans bağımsız değişkenlerinin mükemmel iletilmesi yapar.

## <a name="return-value"></a>Dönüş Değeri

Bunun `Left + Right`sonucu. Özelleştirilmiş şablon, ikili olarak döndürülen türe sahip sonucun mükemmel `operator+`iletilmesi yapar.

## <a name="example"></a>Örnek

```cpp
// functional_plus.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
      v1.push_back( 4 * i );

   int j;
   for ( j = 0 ; j <= 5 ; j++ )
      v2.push_back( -2.0 * j - 4 );

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise sums of the elements of v1 & v2
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );

   cout << "The element-wise sums are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 4 8 12 16 20 )
The vector v2 = ( -4 -6 -8 -10 -12 -14 )
The element-wise sums are: ( -4 -2 0 2 4 6 )
```
