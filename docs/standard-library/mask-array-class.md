---
title: mask_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 12398203d61f2c3ea155b5f6e6e7b118d4a13c75
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689399"
---
# <a name="mask_array-class"></a>mask_array Sınıfı

Alt küme dizileri arasında işlem sağlayarak bir Boolean ifadesiyle belirtilen üst valarışın alt kümeleri olan nesneleri destekleyen dahili, yardımcı sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıfı, [valarray](../standard-library/valarray-class.md)  **\<Type >** sınıfının bir nesne `va` bir başvurusunu depolayan bir nesneyi tanımlar ve bu sınıf [valarray \<bool >](../standard-library/valarray-bool-class.md)sınıfının bir nesne `ba` ve seçilecek öğelerin dizisini açıklar `valarray<Type>` nesnesinden.

Yalnızca [VA&#91;ba&#93;](../standard-library/valarray-class.md#op_at)biçimindeki bir ifade yazarak bir `mask_array<Type>` nesnesi oluşturursunuz. Mask_array sınıfının üye işlevleri, `valarray<Type>` için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Dizi `ba.size` öğelerinden oluşur. Yalnızca **ba**[ *J*] true olduğunda *J* öğesi dahil edilir. Bu nedenle, `ba` öğesinde gerçek öğeler olduğundan, dizide birçok öğe vardır. @No__t_0, `ba` en düşük doğru öğenin dizini ise, **VA**[`I`] seçili dizideki öğe sıfırdır.

## <a name="example"></a>Örnek

```cpp
// mask_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Çıkış

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<valarray >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
