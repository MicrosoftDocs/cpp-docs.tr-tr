---
title: Derleyici Uyarısı (düzey 4) C4389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4389
dev_langs:
- C++
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44a51ad6c6cf01744a99402c4db9c7cbd8f82339
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4389"></a>Derleyici Uyarısı (düzey 4) C4389
'işleci': İmzalı ve imzasız uyuşmazlığı  
  
 Bir işlem imzalı ve imzasız değişkenleri dahil. Bu, veri kaybına neden olabilir.  
  
 Aşağıdaki örnek C4389 oluşturur:  
  
```  
// C4389.cpp  
// compile with: /W4  
#pragma warning(default: 4389)  
  
int main()  
{  
   int a = 9;  
   unsigned int b = 10;  
   if (a == b)   // C4389  
      return 0;  
   else  
      return 0;  
};  
```