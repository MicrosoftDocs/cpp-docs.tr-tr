---
title: "Derleyici Hatası C3040 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3040
dev_langs: C++
helpviewer_keywords: C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54b5d90dd3ee752e6cc76421b633afe588b81982
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3040"></a>Derleyici Hatası C3040
'var': 'azaltma' yan tümcesinde değişkeninin türü, azaltma işleci 'işleci' ile uyumlu değil  
  
 Bir değişkende bir [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi ile azaltma işleci kullanılamaz.  
  
 Aşağıdaki örnek C3040 oluşturur:  
  
```  
// C3040.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
  
int main() {  
   #pragma omp parallel reduction(&:d)   // C3040  
      ;  
  
   #pragma omp parallel reduction(-:d)  // OK  
      ;  
}  
```