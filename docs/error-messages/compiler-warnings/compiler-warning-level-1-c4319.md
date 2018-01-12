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
ms.workload: cplusplus
ms.openlocfilehash: b7008b0f618048f5a4538a7aff55f03bab3d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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