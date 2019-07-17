---
title: less Yapısı
ms.date: 11/04/2016
f1_keywords:
- functional/std::less
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
ms.openlocfilehash: 13aef35856066f9c1897c3d8855c5ff537aa3567
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245346"
---
# <a name="less-struct"></a>less Yapısı

Daha az gerçekleştiren bir ikili koşula-işlemi daha (`operator<`) üzerinde bağımsız değişkenleri.

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
Destekleyen herhangi bir türü bir `operator<` , belirtilen veya çıkarsanan tür işlenen alır.

*Sol*\
Sol işleneni, daha az-işlemi daha. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *T*.

*sağ*\
Daha az sağ işleneninin-işlemi daha. Uzmanlaşmamış şablon türü bir lvalue başvuru bağımsız değişkeni alır *türü*. Özelleşmiş şablon lvalue iletilmesini mükemmel ve rvalue başvuru bağımsız değişkenleri tür çıkarımı yapılan *U*.

## <a name="return-value"></a>Dönüş Değeri

Sonucu `Left < Right`. Özelleşmiş şablon tarafından döndürülen türünde sonuç iletilmesini mükemmel `operator<`.

## <a name="remarks"></a>Açıklamalar

İkili koşul `less` < `Type`> katı bir zayıf türünün öğe değerlerini bir dizi sıralama sağlar *türü* denk sınıfların içinde bu tür standart matematiksel karşılar ve yalnızca, Bu nedenle sıralanan gereksinimleri. Farklı değerlerin tüm öğelerin birbirine göre sıralanır, toplam, öğelerin sıralaması uzmanlıkları herhangi bir işaretçi türü için yield.

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
