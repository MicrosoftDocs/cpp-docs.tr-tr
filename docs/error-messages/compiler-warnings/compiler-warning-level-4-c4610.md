---
title: "Derleyici Uyarısı (düzey 4) C4610 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4610
dev_langs:
- C++
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49c894789aa64510a7f65e7e3693c94a88f36f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4610"></a>Derleyici Uyarısı (düzey 4) C4610
'class' nesnesi hiçbir zaman - kullanıcı tanımlı oluşturucusu gerekli oluşturulabilir  
  
 Sınıfı, kullanıcı tanımlı hiçbir veya oluşturucular varsayılan. Hiçbir örnek oluşturma gerçekleştirilir. Aşağıdaki örnek C4610 oluşturur:  
  
```  
// C4610.cpp  
// compile with: /W4  
struct A {  
   int &j;  
  
   A& A::operator=( const A& );  
};   // C4610  
  
/* use this structure definition to resolve the warning  
struct B {  
   int &k;  
  
   B(int i = 0) : k(i) {  
   }  
  
   B& B::operator=( const B& );  
} b;  
*/  
  
int main() {  
}  
```