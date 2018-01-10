---
title: "Derleyici Hatası C3020 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3020
dev_langs: C++
helpviewer_keywords: C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51275874ff28c41704d8a8daa8c2e0f1f6058c49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3020"></a>Derleyici Hatası C3020
'var': OpenMP dizin değişkeni 'için' döngü döngü gövdesine değiştirilemez  
  
 Bir OpenMP `for` döngü gövdesine dizin (döngü sayacı) değiştiremez `for` döngü.  
  
 Aşağıdaki örnek C3020 oluşturur:  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 İle bildirilen bir değişken [lastprivate](../../parallel/openmp/reference/lastprivate.md) parallelized döngü içinde dizin olarak kullanılamaz.  
  
 Bu lastprivate en dıştaki içinde idx_a için yazma döngünün tetikleyecek çünkü aşağıdaki örnek C3020 için ikinci lastprivate verin. Bu lastprivate idx_a en dıştaki dışında bir yazma (teknik olarak, en son yineleme sonuna) döngünün tetikler çünkü ilk lastprivate hata vermez. Aşağıdaki örnek C3020 oluşturur.  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 Aşağıdaki örnek, olası bir çözüm gösterilmektedir:  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```