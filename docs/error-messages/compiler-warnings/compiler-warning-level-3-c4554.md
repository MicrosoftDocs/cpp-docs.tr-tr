---
title: "Derleyici Uyarısı (Düzey 3) C4554 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4554
dev_langs:
- C++
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d783663d463895143f1782649f9082b6f7b76581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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