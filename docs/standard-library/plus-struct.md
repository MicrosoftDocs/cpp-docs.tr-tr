---
description: 'Daha fazla bilgi edinin: Plus struct'
title: plus Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::plus
helpviewer_keywords:
- plus class
- plus struct
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
ms.openlocfilehash: 9f4b821da3f31255b71730d0f8c800450141d7c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340729"
---
# <a name="plus-struct"></a>plus Yapısı

Bağımsız değişkenlerinde ekleme işlemini (ikili) gerçekleştiren önceden tanımlanmış bir işlev nesnesi `operator+` .

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

*Tür*, *T*, *U*\
`operator+`Belirtilen veya çıkartılan türlerin işlenenlerini alan ikiliyi destekleyen bir tür.

*Tarafta*\
Toplama işleminin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
Toplama işleminin sağ işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left + Right` . Özel şablon, ikili tarafından döndürülen türe sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator+` .

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
