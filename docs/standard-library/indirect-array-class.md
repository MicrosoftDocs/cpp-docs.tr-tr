---
title: indirect_array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f1d24fb90b99d7b757f628be4b39d42f0c0051f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845771"
---
# <a name="indirectarray-class"></a>indirect_array Sınıfı

Bir alt kümesini üst valarray dizinlerini belirterek alt diziler arasındaki işlemleri sağlayarak valarrays kümeleridir destekler nesneleri tanımlanmış bir yardımcı, iç Şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıf bir nesneye başvuru depolayan bir nesne tanımlar **va** sınıfının [valarray](../standard-library/valarray-class.md)**\<türü >**, bir nesne ile birlikte **xa**  sınıfının **valarray < size_t >**, aralarından seçim yapabileceğiniz öğe dizisi açıklayan **valarray\<türü >** nesnesi.

Oluşturmak bir **indirect_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne **va [xa]**. Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı indirect_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında.

Sıra oluşan **xa.** [boyutu](../standard-library/valarray-class.md#size) öğeleri, burada öğesi `I` dizin haline **xa**[ `I`] içinde **va**.

## <a name="example"></a>Örnek:

```cpp
// indirect_array.cpp
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

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Çıkış

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
