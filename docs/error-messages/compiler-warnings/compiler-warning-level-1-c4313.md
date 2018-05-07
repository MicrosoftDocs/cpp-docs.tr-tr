---
title: Derleyici Uyarısı (düzey 1) C4313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4313
dev_langs:
- C++
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e42bd8f19ac9a70f93a26265af6e310fb51e7229
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4313"></a>Derleyici Uyarısı (düzey 1) C4313
'function': 'tanımlayıcısı biçiminde Biçimlendir', 'type' tür bağımsız değişkeni sayısı ile çakışıyor dize  
  
 Belirtilen biçim ve geçirme değer arasında bir çakışma var. Örneğin, bir 32 bit tamsayı parametre bekler bir nitelenmemiş %d biçim belirticisi için 64-bit parametresi geçirildi. Bu uyarı için 64-bit hedefleri derlenmiş kod yalnızca etkin olduğunda.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için 64-bit hedef derlendiğinde C4313 oluşturur.  
  
```  
// C4313.cpp  
// Compile by using: cl /W1 C4313.cpp  
#include <stdio.h>  
int main() {  
   int * pI = 0;  
   printf("%d", pI);   // C4313 on 64-bit platform code  
   // Try one of the following lines instead:  
   // printf("%p\n", pI);  
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information  
}  
```