---
title: "Derleyici Hatası C3736 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3736
dev_langs: C++
helpviewer_keywords: C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28fdb1422a00561a4630155c52bed3dc904d2d5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3736"></a>Derleyici Hatası C3736
'event': bir yöntem olmalıdır veya durumunda olayları, isteğe bağlı olarak yönetilen bir veri üyesi  
  
 Yerel ve COM olayları yöntemleri olmalıdır. .NET olaylar ayrıca veri üyesi olabilir.  
  
 Aşağıdaki örnek C3736 oluşturur:  
  
```  
// C3736.cpp  
struct A {  
   __event int e();  
};  
  
struct B {  
   int f;   // C3736  
   // The following line resolves the error.  
   // int f();  
   B(A* a) {  
      __hook(&A::e, a, &B::f);  
   }  
};  
  
int main() {  
}  
```