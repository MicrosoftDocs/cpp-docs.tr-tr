---
title: "Alt simge oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- subscript operator [C++], overloaded
- arrays [C++], subscripting
- subscripting [C++]
- operators [C++], overloading
- operator overloading [C++], examples
- subscript operator
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80173fd16bc13f4951cd85930e742947079f14fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="subscripting"></a>Alt Simge Oluşturma
Alt simge işleci (**[]**) gibi işlev çağırma işleci ikili işleç olarak kabul edilir. Alt simge işleci tek bir bağımsız değişken bir statik olmayan üye işlevi olması gerekir. Bu bağımsız değişken herhangi bir türde olabilir ve istenen dizi alt simge atar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir vektör türü oluşturmak gösterilmiştir `int` denetimi sınırları uygular:  
  
```  
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
  
## <a name="comments"></a>Açıklamalar  
 Zaman `i` önceki programında 10 ulaştığında `operator[]` bir out-of-bounds alt simge kullanılıyor bir hata iletisi sorunlar olduğunu algılar.  
  
 Unutmayın işlevi `operator[]` bir başvuru türü döndürür. Bu, bir l-alt ifadeler atama işleçleri iki tarafında kullanmanıza olanak sağlayan değeri olması neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç aşırı yüklemesi](../cpp/operator-overloading.md)