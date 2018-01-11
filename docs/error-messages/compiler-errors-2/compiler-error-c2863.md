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
ms.workload: cplusplus
ms.openlocfilehash: 78a56c9cd58bc4ef06727e6c927108138dc328b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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