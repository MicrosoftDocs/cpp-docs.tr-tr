---
title: "Derleyici Uyarısı (düzey 4) C4938 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4938
dev_langs: C++
helpviewer_keywords: C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 102e0eeb7b682afed595be2be08c2ee8a69487f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4938"></a>Derleyici Uyarısı (düzey 4) C4938
'var': kayan nokta azaltma değişkeni /fp altında tutarsız sonuçlara neden olabilir: katı veya #pragma fenv_access  
  
 Kullanılamaz [/fp: katı](../../build/reference/fp-specify-floating-point-behavior.md) veya [fenv_access](../../preprocessor/fenv-access.md) OpenMP kayan nokta azaltması ile toplamı farklı bir sırada hesaplandığından. Bu nedenle, sonuçları/OpenMP olmadan sonuçlarından farklı olabilir.  
  
 Aşağıdaki örnek C4938 oluşturur:  
  
```  
// C4938.cpp  
// compile with: /openmp /W4 /fp:strict /c  
// #pragma fenv_access(on)  
extern double *a;   
  
double test(int first, int last) {   
   double sum = 0.0;   
   #pragma omp parallel for reduction(+: sum)   // C4938  
   for (int i = first ; i <= last ; ++i)   
      sum += a[i];   
   return sum;   
}  
```  
  
 Açık paralelleştirme toplamı aşağıdaki gibi hesaplanır:  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 Açık paralelleştirme (ve iki iş parçacığı) ile toplam aşağıdaki gibi hesaplanır:  
  
```  
sum1 = a[first] + ... a[first + last / 2];   
sum2 = a[(first + last / 2) + 1] + ... a[last];   
sum = sum1 + sum2;  
```