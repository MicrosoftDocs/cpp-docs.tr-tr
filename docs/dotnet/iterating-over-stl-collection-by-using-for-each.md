---
title: "Foreach kullanarak C++ Standart Kitaplığı koleksiyonu üzerinden yineleme yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f18b4bfdcb1c525e6e05b133e853d09b2dbd0a56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>Foreach kullanarak C++ Standart Kitaplığı koleksiyonu üzerinden yineleme yapma
`for each` Anahtar sözcüğü, C++ Standart Kitaplığı koleksiyon üzerinde döngüyle gezinmek için kullanılabilir.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 **Açıklamalar**  
  
 C++ Standart Kitaplığı olarak da bilinen koleksiyonudur bir *kapsayıcı*. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).  
  
## <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde `for each` üzerinden yinelemek için bir [ \<harita >](../standard-library/map.md).  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **Çıktı**  
  
```Output  
Months with 30 days = 4  
```  
  
 **Örnek**  
  
 Aşağıdaki kod örneğinde const başvuru kullanır (`const&`) bir yineleme değişkeni C++ Standart Kitaplığı kapsayıcılarla için. Bir başvuru kullanabilirsiniz (`&`) herhangi bir koleksiyon olarak bildirilen bir türde bir yineleme değişkeni olarak bir *T*`&`.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **Çıktı**  
  
```Output  
retval: 60  
```  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 Bu özellik hakkında hiçbir platforma özgü açıklamalar vardır.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
 Bu özellik hakkında hiçbir platforma özgü açıklamalar vardır.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [her biri için](../dotnet/for-each-in.md)   
 [Çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)