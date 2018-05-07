---
title: Derleyici Hatası C2319 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2319
dev_langs:
- C++
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fa9d2c0aeae56ea678a9f2aa2cbfabfc43e71c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2319"></a>Derleyici Hatası C2319
Bileşik deyim tarafından ' try/catch' gelmelidir. Eksik ' {'  
  
 A `try` veya `catch` blok bulunamadı aşağıdaki `try` veya `catch` deyimi. Blok kaşlı ayraç içine alınması gerekir.  
  
 Aşağıdaki örnek C2319 oluşturur:  
  
```  
// C2319.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( C ) ;    // C2319  
   // try the following line instead  
   // catch( C ) {}  
}  
```