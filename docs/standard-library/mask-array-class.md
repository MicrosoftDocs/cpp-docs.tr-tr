---
description: 'Hakkında daha fazla bilgi edinin: mask_array sınıfı'
title: mask_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: d3eb105c7779ff54ddbec3d68a518dc74d089903
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149363"
---
# <a name="mask_array-class"></a>mask_array Sınıfı

Alt küme dizileri arasında işlem sağlayarak bir Boolean ifadesiyle belirtilen üst valarışın alt kümeleri olan nesneleri destekleyen dahili, yardımcı sınıf şablonu.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Açıklamalar

Sınıfı, valarray sınıfının bir nesnesine başvuru depolayan bir nesneyi tanımlar, bu, `va` [](../standard-library/valarray-class.md) **\<Type>** `ba` nesnesinden seçilecek öğelerin dizisini açıklayan [valarray \<bool>](../standard-library/valarray-bool-class.md)sınıfının bir nesnesi ile birlikte `valarray<Type>` .

`mask_array<Type>`Yalnızca [VA&#91;BA&#93;](../standard-library/valarray-class.md#op_at)bir ifade yazarak bir nesne oluşturursunuz. Mask_array sınıfının üye işlevleri, için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak `valarray<Type>` yalnızca seçili öğelerin sırası etkilenir.

Sıra, en çok öğeden oluşur `ba.size` . Yalnızca **ba**[ *J*] true olduğunda *J* öğesi dahil edilir. Bu nedenle, içinde doğru öğeler olduğundan, dizide birçok öğe vardır `ba` . ' `I` De en düşük doğru öğenin dizinse `ba` , **VA**[ `I` ] seçili dizideki öğe sıfırdır.

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

### <a name="output"></a>Çıktı

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<valarray>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
