---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3033'
title: Derleyici hatası C3033
ms.date: 11/04/2016
f1_keywords:
- C3033
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
ms.openlocfilehash: 999cedd270470bde27a57be0159eedda61297092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270244"
---
# <a name="compiler-error-c3033"></a>Derleyici hatası C3033

' var ': ' Clause ' yan tümcesindeki değişken const nitelenmiş türde olamaz

Belirli bir yan tümceciklere geçirilen değerler **`const`** değişken olamaz.

Aşağıdaki örnek C3033 oluşturur:

```cpp
// C3033.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   const int val = 1;
   int val2 = 1;

   #pragma omp parallel reduction(+ : val)   // C3033
   ;

   #pragma omp parallel reduction(+ : val2)   // OK
   ;
}
```
