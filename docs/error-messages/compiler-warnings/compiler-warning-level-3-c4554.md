---
title: Derleyici Uyarısı (Düzey 3) C4554 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4554
dev_langs:
- C++
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad427c9d8a9091a1eea37b10e1e49ed2d8613c18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4554"></a>Derleyici Uyarısı (Düzey 3) C4554
'işleci': olası hata; İşleç önceliği denetleyin öncelik açıklamak için ayraç kullanın  
  
 Aşağıdaki örnek C4554 oluşturur:  
  
```  
// C4554.cpp  
// compile with: /W3 /WX  
int main() {  
   int a = 0, b = 0, c = 0;  
   a = a << b + c;   // C4554  
   // probably intended (a << b) + c,  
   // but will get a << (b + c)  
}  
```