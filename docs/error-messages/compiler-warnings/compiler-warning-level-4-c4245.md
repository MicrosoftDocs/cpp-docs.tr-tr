---
title: Derleyici Uyarısı (düzey 4) C4245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4245
dev_langs:
- C++
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d9521cb7360f038c4648d37f93fe462eb8763c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296240"
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