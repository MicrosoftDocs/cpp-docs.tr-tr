---
title: "Ara belleğe almanın etkileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4073397867eeec176b02ccd67eeb1ac9cdd0ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="effects-of-buffering"></a>Ara Belleğe Almanın Etkileri
Aşağıdaki örnek, ara belleğe almanın etkileri gösterir. Programın yazdırmasını bekleyebilirsiniz `please wait`, 5 saniye bekleyin ve sonra devam edin. Çıkışın arabelleğe alınıp olmadığından, mutlaka bu şekilde, ancak çalışmaz.  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 Mantıksal olarak, iş program yapmak için `cout` nesne gerekir boş kendisini ileti görünmesi olduğunda. Temizlemek için bir `ostream` nesne, göndermeden `flush` manipulator:  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 Bu adım, ileti önce bekleme yazdırır olduktan arabelleğini aktarır. Aynı zamanda `endl` manipulator, arabelleği temizler ve bir satır başı-satır besleme çıkarır veya kullanabileceğiniz `cin` nesnesi. Bu nesne (ile `cerr` veya `clog` nesneler) genellikle bağlı `cout` nesnesi. Bu nedenle, herhangi bir kullanımından `cin` (veya `cerr` veya `clog` nesneler) boşaltır `cout` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış Akışları](../standard-library/output-streams.md)

