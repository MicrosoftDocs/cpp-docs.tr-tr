---
title: Derleyici Hatası C2184 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2184
dev_langs:
- C++
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 068850ea37811cc68c070a968cc2ddc5aa0ce8a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171760"
---
# <a name="compiler-error-c2184"></a>Derleyici Hatası C2184
'type': ifade __except geçersiz türü için bir integral olması gerekir  
  
 Bir tür olarak kullanılan bir [__except](../../c-language/try-except-statement-c.md) deyimi, ancak türü izin verilmez.  
  
 Aşağıdaki örnek C2184 oluşturur:  
  
```  
// C2184.cpp  
void f() {  
   int * p;  
   __try{}  
   __except(p){};   // C2184  
}  
```  
  
 Olası çözüm:  
  
```  
// C2184b.cpp  
// compile with: /c  
void f() {  
   int i = 0;  
   __try{}  
   __except(i){};  
}  
```