---
title: Derleyici Hatası C3045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3045
dev_langs:
- C++
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f485d87c8e6d433380cb1a9080b6ac20766463b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048246"
---
# <a name="compiler-error-c3045"></a>Derleyici Hatası C3045

Bir bileşik deyim bekleniyordu OpenMP 'sections' yönergesinden sonra. Eksik ' {'

Ayraç içinde virgülle ayrılmış bir kod bloğu izlemeniz gereken bir [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi.

Aşağıdaki örnek, C3045 oluşturur:

```
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```