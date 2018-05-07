---
title: Derleyici Uyarısı (düzey 4) C4239 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4239
dev_langs:
- C++
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d756bba65100d3e5c2987527d7a0dd4cc3fdc050
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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