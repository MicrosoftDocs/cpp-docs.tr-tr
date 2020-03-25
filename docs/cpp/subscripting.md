---
title: Alt Simge Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- subscript operator [C++], overloaded
- arrays [C++], subscripting
- subscripting [C++]
- operators [C++], overloading
- operator overloading [C++], examples
- subscript operator
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
ms.openlocfilehash: 8974f6619af462050fc8a02798fe44007ea928e4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160898"
---
# <a name="subscripting"></a>Alt Simge Oluşturma

İşlev çağrısı işleci gibi alt simge işleci ( **[]** ) bir ikili işleç olarak kabul edilir. Alt simge işleci, tek bir bağımsız değişken alan, statik olmayan bir üye işlevi olmalıdır. Bu bağımsız değişken herhangi bir türde olabilir ve istenen dizi alt indisi belirler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınır denetimi uygulayan **int** türünde bir Vector öğesinin nasıl oluşturulacağını gösterir:

```cpp
// subscripting.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class IntVector {
public:
   IntVector( int cElements );
   ~IntVector() { delete [] _iElements; }
   int& operator[](int nSubscript);
private:
   int *_iElements;
   int _iUpperBound;
};

// Construct an IntVector.
IntVector::IntVector( int cElements ) {
   _iElements = new int[cElements];
   _iUpperBound = cElements;
}

// Subscript operator for IntVector.
int& IntVector::operator[](int nSubscript) {
   static int iErr = -1;

   if( nSubscript >= 0 && nSubscript < _iUpperBound )
      return _iElements[nSubscript];
   else {
      clog << "Array bounds violation." << endl;
      return iErr;
   }
}

// Test the IntVector class.
int main() {
   IntVector v( 10 );
   int i;

   for( i = 0; i <= 10; ++i )
      v[i] = i;

   v[3] = v[9];

   for ( i = 0; i <= 10; ++i )
      cout << "Element: [" << i << "] = " << v[i] << endl;
}
```

```Output
Array bounds violation.
Element: [0] = 0
Element: [1] = 1
Element: [2] = 2
Element: [3] = 9
Element: [4] = 4
Element: [5] = 5
Element: [6] = 6
Element: [7] = 7
Element: [8] = 8
Element: [9] = 9
Array bounds violation.
Element: [10] = 10
```

## <a name="comments"></a>Yorumlar

`i` önceki programda 10 ' a ulaştığında, **operator []** sınırların dışı bir alt simge kullanıldığını algılar ve bir hata mesajı yayınlar.

**[] İşlev işlecinin** bir başvuru türü döndürdüğünü unutmayın. Bu, bir l değeri olmasına neden olur ve bu da atama işleçlerinin her tarafında alt simge olarak kullanılan ifadeleri kullanmanıza olanak sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
