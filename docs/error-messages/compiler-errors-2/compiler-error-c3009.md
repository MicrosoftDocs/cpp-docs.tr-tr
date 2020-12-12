---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3009'
title: Derleyici hatası C3009
ms.date: 11/04/2016
f1_keywords:
- C3009
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
ms.openlocfilehash: fd261901293fd002465f4767f2b4389e1c388614
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305331"
---
# <a name="compiler-error-c3009"></a>Derleyici hatası C3009

' Label ': OpenMP yapısal bloğunun içine geç izin verilmiyor

Kod bir OpenMP bloğunun içine veya dışına atlanamaz.

Aşağıdaki örnek C3009 oluşturur:

```c
// C3009.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
   lbl2:;
   }
   goto lbl2;   // C3009
}
```
