---
title: "Derleyici Hatası C3039 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35cf503199939b502840c840e55bb2e5579f116a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3039"></a>Derleyici Hatası C3039
'var': 'için' deyimi OpenMP dizin değişken azaltma değişkeni olamaz  
  
 Değişken kullanılamaz şekilde bir dizin değişkeni örtük olarak özel bir [azaltma](../../parallel/openmp/reference/reduction.md) kapsayan içinde yan tümcesi [paralel](../../parallel/openmp/reference/parallel.md) yönergesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3039 oluşturur:  
  
```  
// C3039.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: i)  
   {  
      #pragma omp for  
      for (i = 0; i < 10; ++i)   // C3039  
         g_i += i;  
   }  
}  
```