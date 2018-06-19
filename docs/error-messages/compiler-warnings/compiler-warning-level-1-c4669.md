---
title: Derleyici Uyarısı (düzey 1) C4669 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4669
dev_langs:
- C++
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baffb413a5c07acaeea7f4706ab9d6e951c65f04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280188"
---
# <a name="compiler-warning-level-1-c4669"></a>Derleyici Uyarısı (düzey 1) C4669
'cast': güvensiz dönüştürme: 'sınıfı', yönetilen veya WinRT tür nesnesi  
  
 Bir cast Windows çalışma zamanı veya yönetilen türü içerir. Derleyici diğer bir işaretçi temelinde bir kopyasını gerçekleştirerek cast tamamlanır, ancak hiçbir başka bir denetim sağlar. Bu uyarıyı çözmek için yönetilen üyeleri ya da Windows çalışma zamanı türleri içeren sınıfları cast değil.  
  
 Aşağıdaki örnek C4669 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C4669.cpp  
// compile with: /clr /W1  
ref struct A {  
   int i;  
   Object ^ pObj;   // remove the managed member to fix the warning  
};  
  
ref struct B {  
   int j;  
};  
  
int main() {  
   A ^ a = gcnew A;  
   B ^ b = reinterpret_cast<B ^>(a);   // C4669  
}  
```