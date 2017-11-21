---
title: "Derleyici Hatası C2863 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2863
dev_langs: C++
helpviewer_keywords: C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 66f1b5ad8dc26cf09f31c8d996b1943e4a189e0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2863"></a>Derleyici Hatası C2863
'arabirimi': arabirim arkadaş sahip olamaz  
  
 Arkadaş arabirim üzerinde bildirme izin verilmiyor.  
  
 Aşağıdaki örnek C2863 oluşturur:  
  
```  
// C2863.cpp  
// compile with: /c  
#include <unknwn.h>  
  
class CMyClass {  
   void *f();  
};   
  
__interface IMyInterface {  
   void g();  
  
   friend int h();   // 2863  
   friend interface IMyInterface1;  // C2863  
   friend void *CMyClass::f();  // C2863  
};  
```