---
title: "Derleyici Hatası C3049 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3049
dev_langs: C++
helpviewer_keywords: C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0fd2d0cdff1c23a1a13f933d8366869858f978c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3049"></a>Derleyici Hatası C3049
'arg': OpenMP 'default' yan tümcesinde geçersiz bağımsız değişken  
  
 Yanlış bir değer geçildi bir [varsayılan](../../parallel/openmp/reference/default-openmp.md) yan tümcesi.  
  
 Aşağıdaki örnek C3049 oluşturur:  
  
```  
// C3049.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(private)   // C3049   
   // try the following line instead  
   // #pragma omp parallel default(shared)  
   {  
      ++n1;  
   }  
}  
```