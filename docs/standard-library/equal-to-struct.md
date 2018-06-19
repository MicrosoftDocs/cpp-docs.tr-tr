---
title: equal_to yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e1ef431fdba40ef9e8fd46b8c0e5d9cf7b32eda
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844009"
---
# <a name="equalto-struct"></a>equal_to Yapısı

Eşitlik işlemi gerçekleştiren bir ikili karşılaştırma ( `operator==`) bağımsız değişkenlerini üzerinde.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type = void>
struct equal_to : public binary_function<Type, Type, bool>
 {
    bool operator()(const Type& Left, const Type& Right) const;
 };

// specialized transparent functor for operator==
template <>
struct equal_to<void>
 {
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
 };
```

### <a name="parameters"></a>Parametreler

`Type`, `T`, `U` Destekleyen herhangi bir türü bir `operator==` türündeki işlenenler belirtilen veya çıkarsanan alır.

`Left` Eşitlik işlemi sol işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `T`.

`Right` Eşitlik işlemi sağ işleneni. Lvalue başvuru bağımsız değişken türü unspecialized şablonu alır `Type`. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız çıkarımı yapılan tür `U`.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left == Right`. Özel şablonu tarafından döndürülen türüne sahip sonuç iletilmesini mükemmel `operator==`.

## <a name="remarks"></a>Açıklamalar

Nesne türü `Type` eşitlik bakımından karşılaştırılabilir olmalıdır. Bu gerektiren `operator==` üzerinde tanımlı bir eşdeğer ilişkisi matematiksel özelliklerini nesne kümesini karşılar. Yerleşik sayısal ve işaretçi türlerinin tümü bu gereksinimi karşılamak.

## <a name="example"></a>Örnek

```cpp
// functional_equal_to.cpp
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
   for ( i = 0 ; i <= 5 ; i+=2 )
   {
      v1.push_back( 2.0 *i );
      v1.push_back( 2.0 * i + 1.0 );
   }

   int j;
   for ( j = 0 ; j <= 5 ; j+=2 )
   {
      v2.push_back( - 2.0 * j );
      v2.push_back( 2.0 * j + 1.0 );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Testing for the element-wise equality between v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      equal_to<double>( ) );

   cout << "The result of the element-wise equal_to comparison\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise equal_to comparison
between v1 & v2 is: ( 1 1 0 1 0 1 )
```

