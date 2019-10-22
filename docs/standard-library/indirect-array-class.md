---
title: indirect_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 6be0c5153cbc94d09b414fc9e14fa498c7a4cfa7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687915"
---
# <a name="indirect_array-class"></a>indirect_array Sınıfı

Bir üst valarray dizinlerinin alt kümesini belirterek tanımlanan alt küme dizileri arasında işlemler sağlayarak, valarışın alt kümeleri olan nesneleri destekleyen iç, yardımcı sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıfı, `valarray<size_t>` nesnesinden seçilecek öğelerin dizisini açıklayan > sınıfının bir nesne `xa` birlikte, [valarray](../standard-library/valarray-class.md)  **\<Type**sınıfının bir nesne `va` bir başvurusunu depolayan bir nesneyi tanımlar.

Bir `indirect_array<Type>` nesnesini yalnızca form `va[xa]` bir ifadesi yazarak oluşturursunuz. İndirect_array sınıfının üye işlevleri, `valarray<Type>` için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Sıra, XA 'ten oluşur **.** [öğe `I`](../standard-library/valarray-class.md#size) , `va` içinde **XA**[`I`] Dizin haline gelir.

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

**Üst bilgi:** \<valarray >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
