---
title: mask_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 9da5e3593288be02819330e11b60e306784054dc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460146"
---
# <a name="maskarray-class"></a>mask_array Sınıfı

Alt küme dizileri arasında işlemler sağlayarak bir Boolean ifadesiyle belirtilen üst valarışın alt kümeleri olan nesneleri destekleyen dahili, yardımcı şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıfı `va` , [valarray](../standard-library/valarray-class.md)**Type>\<** sınıfınınbirnesnesinebirbaşvurudepolayanbirnesneyitanımlar,bu,`ba` bir [valarray\<bool >](../standard-library/valarray-bool-class.md)sınıfının ve `valarray<Type>` nesneden seçilecek öğelerin sırası.

Yalnızca `mask_array<Type>` [VA&#91;ba&#93;](../standard-library/valarray-class.md#op_at)biçimindeki bir ifade yazarak bir nesne oluşturursunuz. Mask_array sınıfının üye işlevleri, için `valarray<Type>`tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Sıra, en çok `ba.size` öğeden oluşur. Yalnızca **ba**[ *J*] true olduğunda *J* öğesi dahil edilir. Bu nedenle, içinde `ba`doğru öğeler olduğundan, dizide birçok öğe vardır. ' De `ba`en düşük doğru öğenin dizinse, **VA**[ `I`] seçili dizideki öğe sıfırdır. `I`

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
