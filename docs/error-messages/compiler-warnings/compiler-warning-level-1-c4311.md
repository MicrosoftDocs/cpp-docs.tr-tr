---
title: Derleyici Uyarısı (düzey 1) C4311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4311
dev_langs:
- C++
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba06488ed41e7e296f9f6c16f34af827274acfd4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4311"></a>Derleyici Uyarısı (düzey 1) C4311
'variable' : 'type' öğesinden 'type' öğesine işaretçi kesilmesi  
  
 Bu uyarı, 64-bit işaretçi kesilmesi sorunları algılar. 64-bitlik bir mimari için derlenmiş kod, atandığı, örneğin, bir işaretçi (64 bit) değerini kesilecek bir `int` (32 bit). Daha fazla bilgi için bkz: [kullanarak işaretçileri için kuralları](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 Uyarı C4311 ortak nedenleri hakkında ek bilgi için bkz: [Genel derleyici hataları](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Aşağıdaki kod örneği için 64-bit hedef derlendiğinde C4311 oluşturur ve ardından sorunu gidermek gösterilmiştir:  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```