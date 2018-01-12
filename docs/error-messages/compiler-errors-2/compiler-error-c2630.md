---
title: "Derleyici Hatası C2630 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2630
dev_langs: C++
helpviewer_keywords: C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2e2f839992a6ff1a6e3389d53d3b58e750daaa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2630"></a>Derleyici Hatası C2630
'ne bulunan simge' virgülle ayrılmış bir liste olması gerekir  
  
 Simgenin virgül gerektiren bir bağlamında görüntülenir.  
  
 Aşağıdaki örnek C2630 oluşturur:  
  
```  
// C2630.cpp  
// compile with: /c  
struct D {  
   D(int);  
};  
  
struct E {  
   E(int);  
};  
  
class C : public D, public E {  
   C();  
};  
  
C::C() : D(0) ; E(0) { }   // C2630  
C::C() : D(0), E(0) {}   // OK  
```