---
title: Derleyici Hatası C3040 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3040
dev_langs:
- C++
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f895626ac04afc776c279f5e2bf7a857ffbd432
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246241"
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