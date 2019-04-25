---
title: Derleyici Hatası C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: d0a5da87feeabc5d3d5b558ce0dd6bdfe3869d53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165573"
---
# <a name="compiler-error-c3034"></a>Derleyici Hatası C3034

OpenMP 'directive1' yönergesi doğrudan 'directive2' yönergesi içinde iç içe olamaz

Yönergelerden bazıları iç içe olamaz. Bu hatayı düzeltmek için bir yönergesi bloğuna hem yönergeleri ifadeleri birleştirebilirsiniz ya da art arda yönergeleri oluşturabilirsiniz.

Aşağıdaki örnek, C3034 oluşturur:

```
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