---
title: indirect_array Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 5db5f2ce60038267b70ae8e77d9dd929d972af6a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456337"
---
# <a name="indirectarray-class"></a>indirect_array Sınıfı

Bir üst valarray dizinlerinin alt kümesini belirterek tanımlanan alt küme dizileri arasında işlemler sağlayarak, valarışın alt kümeleri olan nesneleri destekleyen iç, yardımcı şablon sınıfı.

## <a name="syntax"></a>Sözdizimi

## <a name="remarks"></a>Açıklamalar

Sınıfı, `va` [valarray](../standard-library/valarray-class.md) `xa` `valarray<size_t>` **>\<türündeki**bir nesneye başvuru depolayan bir nesneyi tanımlar, bir sınıfının bir nesnesi ile birlikte, içinden seçilecek öğelerin dizisini tanımlar `valarray<Type>` nesnesi.

Yalnızca formun `indirect_array<Type>` `va[xa]`bir ifadesini yazarak bir nesne oluşturursunuz. İndirect_array sınıfının üye işlevleri, için `valarray<Type>`tanımlanan karşılık gelen işlev imzaları gibi davranır, ancak yalnızca seçili öğelerin sırası etkilenir.

Sıra, XA 'ten oluşur **.** [](../standard-library/valarray-class.md#size) burada öğesi `I` , `I`içindeki  XA[]dizinihaline`va`gelir.

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
