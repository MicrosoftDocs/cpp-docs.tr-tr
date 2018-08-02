---
title: Dizileri kullanma (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ff0716359c715431f9887f50be06e592d57787e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463918"
---
# <a name="using-arrays-c"></a>Dizileri Kullanma (C++)
Dizi indisi işlecini kullanarak bir dizinin tek tek öğelerine erişebilirsiniz (`[ ]`). Alt indisi olmayan bir ifadede tek boyutlu bir dizi kullanılıyorsa, dizi adı dizideki ilk öğe işaretçisi için değerlendirir.  
  
```cpp 
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Çok boyutlu diziler kullandığınızda, ifadelerde çeşitli birleşimler kullanabilirsiniz.  
  
```cpp 
// using_arrays_2.cpp  
// compile with: /EHsc /W1  
#include <iostream>  
using namespace std;  
int main() {  
   double multi[4][4][3];   // Declare the array.  
   double (*p2multi)[3];  
   double (*p1multi);  
  
   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.  
   p2multi = multi[3];               // Make p2multi point to  
                                     // fourth "plane" of multi.  
   p1multi = multi[3][2];            // Make p1multi point to  
                                     // fourth plane, third row  
                                     // of multi.  
}  
```  
  
 Önceki kodda, `multi` üç boyutlu bir dizi türü **çift**. `p2multi` İşaretçinin, bir dizi türüne işaret **çift** boyut olarak üç olan. Bu örnekte, dizi bir, iki ve üç alt simgeyle birlikte kullanılır. Tüm alt simgeler olarak belirtmek için daha yaygın olsa `cout` deyiminde olduğu bazen belirli bir alt dizi öğeleri kümesini seçmek adına kullanışlı olabilir izleyen gösterildiği `cout`.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Diziler](../cpp/arrays-cpp.md)