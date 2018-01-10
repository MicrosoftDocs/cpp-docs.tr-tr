---
title: "Derleyici Hatası C3041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3041
dev_langs: C++
helpviewer_keywords: C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d46e0eabc609f453c9d70866e20550b0a9e7536
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3041"></a>Derleyici Hatası C3041
'var': 'copyprivate' yan tümcesinde değişkeni içeriği kapsayan özel olmalıdır  
  
 Bir değişkenin geçirilen [copyprivate](../../parallel/openmp/reference/copyprivate.md) kapsayan bağlamda paylaşılamaz.  
  
 Aşağıdaki örnek C3041 oluşturur:  
  
```  
// C3041.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
int main() {  
   #pragma omp parallel shared(d)  
   // try the following line instead  
   // #pragma omp parallel private(d)  
   {  
      // or don't make d copyprivate  
      #pragma omp single copyprivate(d)   // C3041  
      {  
      }  
   }  
}  
```