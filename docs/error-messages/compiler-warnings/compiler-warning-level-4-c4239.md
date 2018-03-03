---
title: "Derleyici Uyarısı (düzey 4) C4239 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4239
dev_langs:
- C++
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18f1c6d700de0c621ebde02c7dcb2817091677cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4239"></a>Derleyici Uyarısı (düzey 4) C4239
kullanılan standart olmayan uzantısı: 'belirteci': 'type'-'type' dönüşümü  
  
 Bu tür dönüştürme tarafından C++ standart izin verilmez, ancak izin verilir burada bir uzantısı olarak. Bu uyarı her zaman en az bir ihlal dil kuralı açıklayan açıklama satırı tarafından izlenir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4239 oluşturur.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## <a name="example"></a>Örnek  
 Tam sayı türüne dönüştürme numaralandırma türü için kesinlikle izin verilmiyor.  
  
 Aşağıdaki örnek C4239 oluşturur.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```