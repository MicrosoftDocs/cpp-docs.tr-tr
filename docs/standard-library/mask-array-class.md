---
title: mask_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 108c942bef33e44b515d46e953c9d99274e3ce8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475831"
---
# <a name="maskarray-class"></a>mask_array Sınıfı

Üst valarrays kümeleridir destekler nesnelerin alt diziler arasındaki işlemleri sağlayarak bir Boole ifadesi ile belirtilen bir iç, ikincil bir şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıfı bir nesneye bir başvuru depolayan nesneyi tanımlar `va` sınıfın [valarray](../standard-library/valarray-class.md)**\<türü >**, nesneyle birlikte `ba` sınıfın [ valarray\<bool >](../standard-library/valarray-bool-class.md), aralarından seçim yapabileceğiniz öğe dizisi açıklar `valarray<Type>` nesne.

Oluşturmak bir `mask_array<Type>` biçiminde bir ifade yazarak yalnızca nesne [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at). Mask_array sınıfı üye işlevleri sonra karşılık gelen işlev imzası için tanımlanan gibi davranmasını `valarray<Type>`dışında yalnızca seçilen öğelerin sırası etkilenmez.

Dizi en çok oluşan `ba.size` öğeleri. Bir öğe *J* yalnızca dahildir **ba**[ *J*] geçerlidir. Bu nedenle, doğru öğeleri olduğundan kadar dizideki vardır `ba`. Varsa `I` en düşük doğru öğenin dizinidir `ba`, ardından **va**[ `I`] seçili dizideki öğe sıfır.

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

**Başlık:** \<valarray >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
