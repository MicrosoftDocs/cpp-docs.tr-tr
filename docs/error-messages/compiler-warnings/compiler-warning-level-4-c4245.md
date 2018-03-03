---
title: "Derleyici Uyarısı (düzey 4) C4245 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4245
dev_langs:
- C++
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94308b2b19878c3c25a91bfd27658209b7635cb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4245"></a>Derleyici Uyarısı (düzey 4) C4245
'dönüştürme': 'type1' dönüştürme 'type2', imzalı ve imzasız uyuşmazlığı  
  
 İşaretli dönüştürmeye çalıştığınız **const** negatif bir değere sahip bir `unsigned`.  
  
 Aşağıdaki örnek C4245 oluşturur:  
  
```  
// C4245.cpp  
// compile with: /W4 /c  
const int i = -1;  
unsigned int j = i; // C4245  
  
const int k = 1;  
unsigned int l = k; // okay  
  
int m = -1;  
unsigned int n = m; // okay  
  
void Test(size_t i) {}  
  
int main() {  
   Test( -19 );   // C4245  
}  
```