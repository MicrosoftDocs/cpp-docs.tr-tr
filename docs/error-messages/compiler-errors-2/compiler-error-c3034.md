---
title: Derleyici hatası C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: 56ae2ddf35148fe263e406f48526cd68c4f91352
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748300"
---
# <a name="compiler-error-c3034"></a>Derleyici hatası C3034

OpenMP ' directive1 ' yönergesi ' directive2 ' yönergesi içinde doğrudan iç içe geçirilemez

Bazı yönergeler iç içe geçirilemez. Bu hatayı onarmak için her iki yönergedeki deyimlerini tek bir yönerge bloğu içinde birleştirebilir veya birbirini izleyen yönergeler oluşturabilirsiniz.

Aşağıdaki örnek C3034 oluşturur:

```cpp
// C3034.cpp
// compile with: /openmp /link vcomps.lib
int main() {

   #pragma omp single
   {
      #pragma omp single   // C3034
      {
      ;
      }
   }

   // Two consecutive single clauses are OK.
   #pragma omp single
   {
   }

   #pragma omp single
   {
   }
}
```
