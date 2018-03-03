---
title: "Derleyici Uyarısı (düzey 4) C4242 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bee4a165ae59bd21491fdecfc8c25d18477d7c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4242"></a>Derleyici Uyarısı (düzey 4) C4242
'tanımlayıcısı': 'type1' öğesinden 'type2', olası veri kaybını dönüştürme  
  
 Farklı türleridir. Tür dönüştürme veri kaybına neden olabilir. Derleyici tür dönüştürme yapar.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 C4242 hakkında ek bilgi için bkz: [Genel derleyici hataları](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 Aşağıdaki örnek C4242 oluşturur:  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```