---
title: Derleyici Hatası C3037 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3037
dev_langs:
- C++
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64571676a5728e4598613702df8f312d98ed1cb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244904"
---
# <a name="compiler-error-c3037"></a>Derleyici Hatası C3037
'var': 'azaltma' yan tümcesinde değişkeni içeriği kapsayan paylaşılabilecek gerekir  
  
 Belirtilen değişken bir [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi bağlamında her bir iş parçacığı için özel olmayabilir.  
  
 Aşağıdaki örnek C3037 oluşturur:  
  
```  
// C3037.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel private(g_i)  
   // try the following line instead  
   // #pragma omp parallel   
   {  
      #pragma omp for reduction(+:g_i)   // C3037  
      for (i = 0 ; i < 10 ; ++i) {  
         g_i += i;  
      }  
   }  
}  
```