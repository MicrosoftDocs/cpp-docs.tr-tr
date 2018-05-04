---
title: Diziler (C++) kullanarak | Microsoft Docs
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
ms.openlocfilehash: 0c2140dbe786a5d2a2a1b86eca17912e5e06b922
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="using-arrays-c"></a>Dizileri Kullanma (C++)
Dizi alt simge işleci kullanarak bir dizinin ayrı ayrı öğeler erişebilirsiniz (`[ ]`). Deyimde hiçbir alt simge olan tek boyutlu dizi kullandıysanız, dizi adı dizinin ilk öğe için bir işaretçi olarak değerlendirilir.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Çok boyutlu diziler kullandığınızda ifadelerinde çeşitli bileşimlerini kullanabilirsiniz.  
  
```  
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
  
 Önceki kod `multi` üç boyutlu bir dizi türü `double`. `p2multi` İşaretçinin işaret türünde bir dizi `double` üç boyutunun. Bu örnekte, dizi bir, iki ya da üç alt simgeler ile kullanılır. Tüm alt simgeler olarak belirtmek için daha yaygın olmasına rağmen `cout` deyimi, onu bazen faydalıdır dizi öğelerini, belirli bir alt seçmek aşağıdaki tablolarda gösterildiği gibi `cout`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diziler](../cpp/arrays-cpp.md)