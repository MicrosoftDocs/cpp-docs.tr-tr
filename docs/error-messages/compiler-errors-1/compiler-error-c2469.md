---
title: Derleyici Hatası C2469 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2469
dev_langs:
- C++
helpviewer_keywords:
- C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37decb55a2f24f7f29d28519e2f87eba90ff56bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2469"></a>Derleyici Hatası C2469
'işleci': 'type' nesnesi ayrılamıyor  
  
 Bir işleç geçersiz bir tür geçirildi.  
  
 Aşağıdaki örnek C2469 oluşturur:  
  
```  
// C2469.cpp  
int main() {  
   int *i = new void;   // C2469  
   int *i = new int;   // OK  
}  
```