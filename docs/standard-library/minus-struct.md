---
description: 'Daha fazla bilgi edinin: eksi struct'
title: minus Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::minus
helpviewer_keywords:
- minus struct
- minus class
ms.assetid: 7bce784e-2be6-413a-b516-004e9ecb2a39
ms.openlocfilehash: fe9fb343a49fb8097322b687326d3c986ba25ee5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230503"
---
# <a name="minus-struct"></a>minus Yapısı

Bağımsız değişkenlerinde çıkarma işlemini (ikili) gerçekleştiren önceden tanımlanmış bir işlev nesnesi `operator-` .

## <a name="syntax"></a>Sözdizimi

```
template <class Type = void>
struct minus : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator-
template <>
struct minus<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) - std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U*\
`operator-`Belirtilen veya çıkartılan türlerin işlenenlerini alan ikiliyi destekleyen bir tür.

*Tarafta*\
İşlemin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
İşlemin sağ işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left - Right` . Özel şablon, sonucu tarafından döndürülen türü içeren kusursuz bir iletme işlemi yapar `operator-` .

## <a name="example"></a>Örnek

```cpp
// functional_minus.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 4 * i + 1);
   }

   int j;
   for ( j = 0 ; j <= 5 ; j++ )
   {
      v2.push_back( 3 * j - 1);
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise diference of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      minus<int>( ) );

   cout << "The element-wise differences between v1 and v2 are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 1 5 9 13 17 21 )
The vector v2 = ( -1 2 5 8 11 14 )
The element-wise differences between v1 and v2 are: ( 2 3 4 5 6 7 )
```
