---
description: 'Daha fazla bilgi edinin: less yapısı'
title: less Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::less
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
ms.openlocfilehash: b80789f2d2f2c8d1267450a39c39317af1da9244
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312884"
---
# <a name="less-struct"></a>less Yapısı

Bağımsız değişkenlerinde küçüktür işlemi () gerçekleştiren bir ikili koşul `operator<` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type = void>
struct less : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<
template <>
struct less<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) <std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametreler

*Tür*, *T*, *U*\
`operator<`Belirtilen veya çıkartılan türlerin işlenenlerini destekleyen bir tür.

*Tarafta*\
Küçüktür işleminin sol işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *T*'nin lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

*Right*\
Küçüktür işleminin doğru işleneni. Özelleştirilmemiş şablon *tür türünde bir* lvalue başvuru bağımsız değişkeni alır. Özel şablon, çıkarılan tür *U* için lvalue ve rvalue başvurusu bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini yapar.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left < Right` . Özel şablon, tarafından döndürülen türüne sahip olan sonucun kusursuz bir şekilde iletilmesini yapar `operator<` .

## <a name="remarks"></a>Açıklamalar

İkili koşul `less` < `Type`>,, ve yalnızca bu tür için standart matematik gereksinimlerini karşılıyorsa, bir dizi  öğe değerlerini denklik sınıflarında katı bir şekilde bir şekilde bir, ancak bu türü Herhangi bir işaretçi türü için özelleştirilmiş bir öğe sıralaması, farklı değerlerin tüm öğelerinin birbirleriyle ilgili olarak sıralanmasından oluşur.

## <a name="example"></a>Örnek

```cpp
// functional_less.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

struct MyStruct {
   MyStruct(int i) : m_i(i){}

   bool operator < (const MyStruct & rhs) const {
      return m_i < rhs.m_i;
   }

   int m_i;
};

int main() {
   using namespace std;
   vector <MyStruct> v1;
   vector <MyStruct>::iterator Iter1;
   vector <MyStruct>::reverse_iterator rIter1;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
       v1.push_back( MyStruct(rand()));

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   sort( v1.begin( ), v1.end( ), less<MyStruct>());

   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (41 18467 6334 26500 19169 15724 11478)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500)
```
