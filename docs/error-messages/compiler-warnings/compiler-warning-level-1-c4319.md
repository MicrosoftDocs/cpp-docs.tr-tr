---
title: "Derleyici Uyarısı (düzey 1) C4319 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4319
dev_langs: C++
helpviewer_keywords: C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dded592ef5b82329725937c40584d889d5aeb249
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319
'işleci': 'büyük boyutunu 'type' type' genişletme sıfır  
  
 Sonucu ~ (bit düzeyinde tamamlama) işleci, imzasız ve ardından sıfır genişletilmiş daha büyük bir türe dönüştürüldüğünde.  
  
 Aşağıdaki örnekte, ~(a-1) 32-bit bir imzasız uzun ifade olarak değerlendirilir ve 64 bit sıfır uzantısı tarafından sonra dönüştürülür. Bu, beklenmeyen işlem sonuçlara neden.  
  
```  
// C4319.cpp  
// compile with: cl /W4 C4319.cpp  
int main() {  
   unsigned long a = 0;  
   unsigned long long q = 42;  
   q = q & ~(a - 1);    // C4319 expected  
}  
```