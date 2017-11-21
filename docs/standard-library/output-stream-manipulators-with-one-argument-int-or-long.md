---
title: "Çıkış akışı Manipülatörleri (int veya long) tek bağımsız değişkenli | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 418b9e1f982e1bb37559ee35b6953d7d3f198b61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Bir Bağımsız Değişkenli Çıkış Akışı Manipülatörleri (int veya long)
İostream sınıf kitaplığı parametreli manipülatörleri oluşturmak için makroları kümesi sağlar. Tek bir manipülatörleri `int` veya `long` bağımsız değişkeni olan bir özel durum. Tek bir kabul eden bir çıkış akışı manipulator oluşturmak için `int` veya `long` bağımsız değişkeni (gibi `setw`), tanımlanan _Smanip makrosu kullanmalısınız \<iomanip >. Bu örnek tanımlayan bir `fillblank` boşlukları belirtilen sayıda akışa ekler manipulator:  
  
## <a name="example"></a>Örnek  
  
```cpp  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişkenlerle birlikte özel Manipülatörleri](../standard-library/custom-manipulators-with-arguments.md)

