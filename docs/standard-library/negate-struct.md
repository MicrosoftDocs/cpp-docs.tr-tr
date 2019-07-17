---
title: negate Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::negate
helpviewer_keywords:
- negate struct
- negate class
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
ms.openlocfilehash: cb45f61323a407e90c2a455460a4d2cdd7b6720a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240562"
---
# <a name="negate-struct"></a>negate Yapısı

Aritmetik olumsuzlama işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi (birli `operator-`) bağımsız değişken üzerinde.

## <a name="syntax"></a>Sözdizimi

```
template <class Type = void>
struct negate : public unary_function<Type, Type>
{
    Type operator()(const Type& Left) const;
};

// specialized transparent functor for unary operator-
template <>
struct negate<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
    -> decltype(-std::forward<Type>(Left));
};
```

### <a name="parameters"></a>Parametreler

*Türü*\
Destekleyen herhangi bir türü bir `operator-` belirtilen veya çıkarsanan türünde bir işlenen alan.

*Sol*\
Negatif işlenen. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *türü*.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `-Left`. Özelleşmiş şablon birli tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator-`.

## <a name="example"></a>Örnek

```cpp
// functional_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2 ( 8 );
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = -2 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Finding the element-wise negatives of the vector v1
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );

   cout << "The negated elements of the vector = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( -10 -5 0 5 10 15 20 25 )
The negated elements of the vector = ( 10 5 0 -5 -10 -15 -20 -25 )
```
