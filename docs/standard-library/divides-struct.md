---
title: divides yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::divides
dev_langs:
- C++
helpviewer_keywords:
- divides struct
- divides class
ms.assetid: b9cf8e9c-6981-43a6-a6a3-8f761987dd7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0580d6e2128a75f7457541cc82caf2fece958b81
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="divides-struct"></a>divides Yapısı

Bölme işlemi gerçekleştiren bir önceden tanımlı işlev nesnesi ( `operator/`) bağımsız değişkenlerini üzerinde.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type = void>
struct divides : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator/
template <>
struct divides<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left)*/ std::forward<U>(Right));
 };
```

### <a name="parameters"></a>Parametreler

`Type`, `T`, `U` Destekleyen bir türü bir `operator/` türündeki işlenenler belirtilen veya çıkarsanan alır.

`Left` Bölme işlemi sol işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `T`.

`Right` Bölme işlemi sağ işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `U`.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left / Right`. Özel şablonu tarafından döndürülen türüne sahip sonuç iletilmesini mükemmel `operator/`.

## <a name="example"></a>Örnek

```cpp
// functional_divides.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 (6);
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 7.0 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 2.0 * j);
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise quotients of the elements of v1 & v2
   transform ( v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ),
      divides<double>( ) );

   cout << "The element-wise quotients are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}

/* Output:
The vector v1 = ( 0 7 14 21 28 35 )
The vector v2 = ( 2 4 6 8 10 12 )
The element-wise quotients are: ( 0 1.75 2.33333 2.625 2.8 2.91667 )
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlevsel >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
