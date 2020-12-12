---
description: 'Hakkında daha fazla bilgi edinin: indirect_array sınıfı'
title: indirect_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 47c9a0e604fd9873d7705f70624e67d9b3a22a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324047"
---
# <a name="indirect_array-class"></a>indirect_array Sınıfı

Bir üst valarray dizinlerinin alt kümesini belirterek tanımlanan alt küme dizileri arasında işlemler sağlayarak, valarışın alt kümeleri olan nesneleri destekleyen iç, yardımcı sınıf şablonu.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Açıklamalar

Sınıfı, valarray sınıfının bir nesnesine bir başvuru depolayan bir nesne tanımlar `va` . bu [](../standard-library/valarray-class.md), **\<Type>** `xa` `valarray<size_t>` nesnesinden seçilecek öğelerin dizisini açıklayan bir sınıf nesnesiyle birlikte `valarray<Type>` .

`indirect_array<Type>`Yalnızca formun bir ifadesini yazarak bir nesne oluşturursunuz `va[xa]` . İndirect_array sınıfının üye işlevleri, için tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak `valarray<Type>` yalnızca seçili öğelerin sırası etkilenir.

Sıra, XA 'ten oluşur **.** Burada [öğesi,](../standard-library/valarray-class.md#size) `I` içindeki **XA**[] dizini haline gelir `I` `va` .

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

### <a name="output"></a>Çıktı

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<valarray>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
