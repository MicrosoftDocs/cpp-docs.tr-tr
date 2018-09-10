---
title: pair yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::pair
dev_langs:
- C++
helpviewer_keywords:
- pair class
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f11fb76f4009f6497020c26f26184d2ddca4506b
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318277"
---
# <a name="pair-structure"></a>pair Yapısı

İki nesne tek bir nesne olarak değerlendir olanağı sağlayan bir yapı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct pair
{
    typedef T1 first_type;
    typedef T2 second_type;
    T1 first;
    T2 second;
    constexpr pair();
    constexpr pair(
        const T1& Val1,
        const T2& Val2);

    template <class Other1, class Other2>
    constexpr pair(const pair<Other1, Other2>& Right);

    template <class Other1, class Other2>
    constexpr pair(const pair <Other1 Val1, Other2 Val2>&& Right);

    template <class Other1, class Other2>
    constexpr pair(Other1&& Val1, Other2&& Val2);
};
```

### <a name="parameters"></a>Parametreler

*val1*<br/>
İlk öğesi başlatma değeri `pair`.

*Val2*<br/>
İkinci öğesini başlatma değeri `pair`.

*sağ*<br/>
Başka bir çifti öğelerini başlatmak için kullanılacak değerleri olan bir çifti.

## <a name="return-value"></a>Dönüş Değeri

İlk Oluşturucu (varsayılan) ilk öğe türünün varsayılan çiftinin başlatır `T1` ve ikinci öğe türünün varsayılan `T2`.

İkinci oluşturucu çifti için ilk öğesini başlatan *Val1* ve için ikinci *Val2.*

Üçüncü (şablon) Oluşturucu çifti için ilk öğesini başlatan `Right`. **İlk** ve için ikinci `Right`. **İkinci**.

Dördüncü Oluşturucu çifti için ilk öğesini başlatan *Val1* ve için ikinci *Val2* kullanarak [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="remarks"></a>Açıklamalar

Şablon yapı türündeki nesnelerin bir çift depolar `T1` ve `T2`sırasıyla. Türü `first_type` şablon parametresi ile aynı `T1` türü `second_type` şablon parametresi ile aynı `T2`. `T1` ve `T2` her yalnızca bir varsayılan oluşturucu, bir tek bağımsız değişkenli oluşturucu ve yıkıcı sağlamanız. Türün tüm üyeleri `pair` türü olarak bildirildiği için ortak olan bir `struct` yerine bir **sınıfı**. İki en yaygın kullanım için bir çift ilişkilendirilebilir bir kapsayıcı sınıfları için öğeleri olarak ve iki değer döndüren işlevleri için olarak dönüş türleri olan [map sınıfı](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md) hem bir anahtar olması ve Her bir öğeyle ilişkili değer türü. İkinci bir çift ilişkilendirilebilir kapsayıcıdır gereksinimlerini karşılayan ve biçiminde bir değer türünde `pair` <  **const**`key_type`, `mapped_type`>.

## <a name="example"></a>Örnek

```cpp
// utility_pair.cpp
// compile with: /EHsc
#include <utility>
#include <map>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;

   // Using the constructor to declare and initialize a pair
   pair <int, double> p1 ( 10, 1.1e-2 );

   // Compare using the helper function to declare and initialize a pair
   pair <int, double> p2;
   p2 = make_pair ( 10, 2.22e-1 );

   // Making a copy of a pair
   pair <int, double> p3 ( p1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;

   // Using a pair for a map element
   map <int, int> m1;
   map <int, int>::iterator m1_Iter;

   typedef pair <int, int> Map_Int_Pair;

   m1.insert ( Map_Int_Pair ( 1, 10 ) );
   m1.insert ( Map_Int_Pair ( 2, 20 ) );
   m1.insert ( Map_Int_Pair ( 3, 30 ) );

   cout << "The element pairs of the map m1 are:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " ( " << m1_Iter -> first << ", "
           << m1_Iter -> second << " )";
   cout   << "." << endl;

   // Using pair as a return type for a function
   pair< map<int,int>::iterator, bool > pr1, pr2;
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );

   if( pr1.second == true )
   {
      cout << "The element (4,40) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }

   if( pr2.second == true )
   {
      cout << "The element (1,10) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }
}
/* Output:
The pair p1 is: ( 10, 0.011 ).
The pair p2 is: ( 10, 0.222 ).
The pair p3 is: ( 10, 0.011 ).
The element pairs of the map m1 are: ( 1, 10 ) ( 2, 20 ) ( 3, 30 ).
The element (4,40) was inserted successfully in m1.
The element with a key value of
( (pr2.first) -> first ) = 1 is already in m1,
so the insertion failed.
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yardımcı programı >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
