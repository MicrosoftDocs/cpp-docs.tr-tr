---
title: "Derleyici Hatası C3058 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3058
dev_langs: C++
helpviewer_keywords: C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0e8d665e473877ac78612ccaeb9e2e917ee4094c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3058"></a>Derleyici Hatası C3058
'simgesi': 'copyin' yan tümcesinde kullanılmadan önce 'threadprivate' bildirilmemiş simgesi  
  
 Bir simge ilk bildirilmelidir [threadprivate](../../parallel/openmp/reference/threadprivate.md) , kullanılmadan önce bir [copyin](../../parallel/openmp/reference/copyin.md) yan tümcesi.  
  
 Aşağıdaki örnek C3058 oluşturur:  
  
```  
// C3058.cpp  
// compile with: /openmp  
int x, y, z;  
#pragma omp threadprivate(x, z)  
  
void test() {  
   #pragma omp parallel copyin(x, y)   // C3058  
   {  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C3058b.cpp  
// compile with: /openmp /LD  
int x, y, z;  
#pragma omp threadprivate(x, y)  
  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
   }  
}  
```