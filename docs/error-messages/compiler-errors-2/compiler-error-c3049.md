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
ms.openlocfilehash: e2c81bf792be0340cd558ce3ad8efccd64d0d8a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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