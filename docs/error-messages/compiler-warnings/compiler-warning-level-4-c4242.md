---
title: "Derleyici Uyarısı (düzey 4) C4242 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4242
dev_langs: C++
helpviewer_keywords: C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b0e51952a615037b4df3a43fb37cd4f3dc3e717e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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