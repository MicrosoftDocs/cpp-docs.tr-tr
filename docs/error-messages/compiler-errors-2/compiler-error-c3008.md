---
title: "Derleyici Hatası C3008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3008
dev_langs: C++
helpviewer_keywords: C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 392725c883621490b6f9d748cf394e01af329606
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3008"></a>Derleyici Hatası C3008
'arg': bağımsız değişken kapanış eksik ')' üzerinde OpenMP 'yönergesi' yönergesi  
  
 Bir bağımsız değişken bir OpenMP yönergesi kapanış parantezi sahip değil.  
  
 Aşağıdaki örnek C3008 oluşturur:  
  
```  
// C3008.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x   // C3008  
   // Try the following line instead:  
   #pragma omp parallel shared(x)  
   {  
   }  
}  
```