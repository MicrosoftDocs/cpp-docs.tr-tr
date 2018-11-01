---
title: greater_equal Yapısı
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::greater_equal
helpviewer_keywords:
- greater_equal struct
- greater_equal function
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
ms.openlocfilehash: 89591fbcb2b520a83b6e49bd8e7450784258cf3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594200"
---
# <a name="greaterequal-struct"></a>greater_equal Yapısı

Büyük daha-veya-eşittir-yeri işlemi gerçekleştiren bir ikili koşula (`operator>=`) üzerinde bağımsız değişkenleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type = void>
struct greater_equal : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator>=
template <>
struct greater_equal<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left)>= std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U* destekleyen herhangi bir türü bir `operator>=` , belirtilen veya çıkarsanan tür işlenen alır.

*Sol*<br/>
Büyük-veya-eşittir-yeri işleminin sol işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *T*.

*sağ*<br/>
Büyük--veya-eşittir-işlemin sağ işleneni. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *U*.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left >= Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator>=`.

## <a name="remarks"></a>Açıklamalar

İkili koşul `greater_equal` <  `Type`> katı bir zayıf türünün öğe değerlerini bir dizi sıralama sağlar *türü* denk sınıfların içinde bu tür standart matematiksel karşılar ve yalnızca, Bu nedenle sıralanan gereksinimleri. Farklı değerlerin tüm öğelerin birbirine göre sıralanır, toplam, öğelerin sıralaması uzmanlıkları herhangi bir işaretçi türü için yield.

## <a name="example"></a>Örnek

```cpp
// functional_greater_equal.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // specify binary predicate greater_equal<int>( )
   sort( v1.begin( ), v1.end( ), greater_equal<int>( ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (6262 6262 41 18467 6334 26500 19169)
Sorted vector v1 = (41 6262 6262 6334 18467 19169 26500)
Resorted vector v1 = (26500 19169 18467 6334 6262 6262 41)
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<işlev >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
