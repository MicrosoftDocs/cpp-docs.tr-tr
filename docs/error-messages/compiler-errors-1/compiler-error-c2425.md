---
title: Derleyici Hatası C2425 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2425
dev_langs:
- C++
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce9984273ba689bdabe6d1ad6c3c4eb96e151227
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196863"
---
# <a name="compiler-error-c2425"></a>Derleyici Hatası C2425
'belirteci': 'context' sabit olmayan ifade  
  
 Bir sabit olmayan ifadesi bu bağlamda belirteci forms bölümü.  
  
 Bu sorunu gidermek için belirteci bir hesaplama veya bir sabit değişmez değer ile değiştirin.  
  
 Aşağıdaki örnek C2425 oluşturur:  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```