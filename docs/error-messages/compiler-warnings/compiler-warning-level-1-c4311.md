---
title: "Derleyici Uyarısı (düzey 1) C4311 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4311
dev_langs:
- C++
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae2f4b7d7c9ac57f5bdc3fd219c7682e0ec639d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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