---
title: "Derleyici Uyarısı (düzey 4) C4740 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4740
dev_langs:
- C++
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92a94e2f26a0781d736d7e8eeecd76ac62a81255
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4740"></a>Derleyici Uyarısı (düzey 4) C4740
Akış içinde veya dışında satır içi asm kod genel en iyi duruma getirme gizler  
  
 Olduğunda bir atlama içinde veya dışında bir `asm` bloğu, bu işlevi için genel iyileştirmeler devre dışı.  
  
 Aşağıdaki örnek C4740 oluşturur:  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```