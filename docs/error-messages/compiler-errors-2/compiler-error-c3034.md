---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3034'
title: Derleyici hatası C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: 379fedfe3af65b2def83d737daeccac670838c2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270179"
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
