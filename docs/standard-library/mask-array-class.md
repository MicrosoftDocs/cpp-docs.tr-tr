---
title: mask_array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::mask_array
dev_langs:
- C++
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b19ac68f1d1db9ac73e0519b566f68443775db11
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852210"
---
# <a name="maskarray-class"></a>mask_array Sınıfı

Üst valarrays kümeleridir destekler nesneleri alt diziler arasındaki işlemleri sağlayarak bir Boolean ifadesiyle belirtilen bir yardımcı, iç Şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıf bir nesneye başvuru depolayan bir nesne tanımlar **va** sınıfının [valarray](../standard-library/valarray-class.md)**\<türü >**, bir nesne ile birlikte **ba**  sınıfının [valarray\<bool >](../standard-library/valarray-bool-class.md), aralarından seçim yapabileceğiniz öğe dizisi açıklayan **valarray\<türü >** nesnesi.

Oluşturmak bir **mask_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at). Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı mask_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında.

Dizi en çok oluşur **ba.size** öğeleri. Bir öğenin *J* yalnızca eklenmiştir **ba**[ *J*] doğrudur. Bu nedenle, öğe daha vardır true öğeleri olarak kadar sırada **ba**. Varsa `I` en düşük doğru öğe dizini **ba**, ardından **va**[ `I`] sıfır seçilen sırası öğedir.

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
