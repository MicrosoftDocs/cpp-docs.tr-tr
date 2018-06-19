---
title: Yapı eksi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::minus
dev_langs:
- C++
helpviewer_keywords:
- minus struct
- minus class
ms.assetid: 7bce784e-2be6-413a-b516-004e9ecb2a39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10145e52931fc9ef993108c2373bf3d0fbf0519e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858087"
---
# <a name="minus-struct"></a>minus Yapısı

Çıkarma işlemi gerçekleştiren bir önceden tanımlı işlev nesnesi (ikili `operator-`) bağımsız değişkenlerini üzerinde.

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

`Type`, `T`, `U` Bir ikili destekleyen bir türü `operator-` türündeki işlenenler belirtilen veya çıkarsanan alır.

`Left` İşlemi sol işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `T`.

`Right` İşlemi sağ işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `U`.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left - Right`. Özel şablonu tarafından döndürülen türüne sahip sonuç iletilmesini mükemmel `operator-`.

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
\* Output:
The vector v1 = ( 1 5 9 13 17 21 )
The vector v2 = ( -1 2 5 8 11 14 )
The element-wise differences between v1 and v2 are: ( 2 3 4 5 6 7 )
*\
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
