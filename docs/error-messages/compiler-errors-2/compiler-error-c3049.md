---
title: Derleyici Hatası C3049 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3049
dev_langs:
- C++
helpviewer_keywords:
- C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc4300c73eea1b9bc14c535fe9cde960c51212d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248625"
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