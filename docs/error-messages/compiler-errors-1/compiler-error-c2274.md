---
title: "Derleyici Hatası C2274 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5466e242591ba2f8f161af198ea3ec912933a857
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2274"></a>Derleyici Hatası C2274
'type': sağ tarafındaki olarak geçersiz '.' işleci  
  
 Bir tür üye erişimi (.) işlecinin sağ işleneni olarak görünür.  
  
 Kullanıcı tanımlı tür dönüştürme erişmeye tarafından bu hataya neden. Anahtar sözcüğü kullanmak `operator` dönem arasında ve `type`.  
  
 Aşağıdaki örnek C2286 oluşturur:  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```